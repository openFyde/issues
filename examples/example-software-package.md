# Example: Software/Package Issue

**Title:** Chrome fails to sync Google Drive offline files - "Quota exceeded" on devices with >50GB free space

## Device Information
**Board/Device:** Generic x86_64 (Dell Latitude 7420)
**openFyde Version:** r119-14.2
**Build Date:** Pre-built image

## Issue Category
- [x] Software/Package issue

## Environment Setup

### For Runtime Issues:
**Installation Media:** Internal NVMe (dual boot with Windows 11)
**Display:** Internal 14" 1920x1080
**Power Supply:** 65W USB-C Dell adapter
**Connected Peripherals:** USB-C dock with ethernet

## Problem Description

### Expected Behaviour
Google Drive files marked for offline access should sync successfully when there's adequate storage space.

### Actual Behaviour
Sync fails with "Quota exceeded" error despite having 50GB+ free space. Only affects Google Drive offline sync - local downloads and other Chrome features work fine.

### Steps to Reproduce
1. Sign into Google account
2. Open Files app
3. Navigate to Google Drive
4. Right-click any file/folder and select "Available offline"
5. Wait for sync to start
6. After ~30 seconds, red error icon appears with "Quota exceeded"

### Error Messages/Logs
```
From chrome://drive-internals:
2024-03-15 14:23:45.123 ERROR: Sync failed for doc-id-12345
2024-03-15 14:23:45.124 ERROR: QUOTA_EXCEEDED: User quota exceeded
2024-03-15 14:23:45.125 INFO: Available space: 53,687,091,200 bytes

From /var/log/chrome/chrome_debug.log:
[3456:3456:0315/142345.234567:ERROR:drive_fs_host.cc(890)] DriveFS failed: QUOTA_BYTES_EXCEEDED

Output of df -h:
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p5   120G   65G   50G  57% /
/dev/nvme0n1p1   200M   50M  150M  25% /boot/efi
```

## Additional Information

### What I've Tried
- Cleared Chrome cache and data
- Signed out and back into Google account
- Ran `sudo quota --edit` (no quotas set)
- Created new user profile - same issue
- Tested on another Google account - same issue
- Verified Google Drive storage (using 5GB of 15GB)

### Related Issues/Links
- Found similar report on r/ChromeOS: https://reddit.com/r/chromeos

### Possible Solution
Based on the logs, it seems Chrome is checking quota against wrong partition or there's a hardcoded limit somewhere in the Drive FS implementation that doesn't account for openFyde's partition layout.