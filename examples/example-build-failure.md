# Example: Build Failure Issue

**Title:** Build fails with "no space left on device" despite 200GB free space - RockPi 4B image

## Device Information
**Board/Device:** RockPi 4B
**openFyde Version:** Building from main branch (commit: abc123def)
**Build Date:** 2024-03-15

## Issue Category
- [x] Building openFyde from source

## Environment Setup

### For Build Issues:
**Host OS:** Ubuntu 22.04.3 LTS
**CPU:** AMD Ryzen 9 5900X
**RAM:** 64GB DDR4
**Storage:** 500GB available on /home partition (ext4 on NVMe)
**Build Command Used:** 
```bash
cros build-packages --board=rockpi-4b
```

## Problem Description

### Expected Behaviour
Build should complete successfully as I have sufficient disk space.

### Actual Behaviour
Build fails after about 2 hours with "No space left on device" error, but `df -h` shows 200GB+ free.

### Steps to Reproduce
1. Fresh checkout of openFyde repository
2. Run `cros_sdk --enter`
3. Setup board with `setup_board --board=rockpi-4b`
4. Start build with `cros build-packages --board=rockpi-4b`
5. Error occurs during chromeos-base/chromeos-chrome compilation

### Error Messages/Logs
```
* ERROR: chromeos-base/chromeos-chrome-120.0.6099.109_rc-r1::chromiumos failed (compile phase):
*   (no error message)
* Call stack:
*     ebuild.sh, line 124: Called src_compile
*   OSError: [Errno 28] No space left on device: '/tmp/portage/chromeos-base/chromeos-chrome-120.0.6099.109_rc-r1/temp/build.log'
```

## Additional Information

### What I've Tried
- Increased /tmp to 32GB (was 16GB)
- Set PORTAGE_TMPDIR to a location with more space
- Cleared ccache with `ccache -C`
- Verified no quota limits with `quota -s`

### Related Issues/Links
- Similar issue in Chromium OS tracker: crbug.com/123456

### Possible Solution
I suspect this might be inode exhaustion rather than disk space. Running `df -i` shows /tmp is at 98% inode usage.