# openFyde Issues - Centralised Issue Collector 🎯

Welcome to the centralised issue tracking repository for all openFyde-related projects.

## Why This Repository Exists

The openFyde organisation contains approximately **60 individual repositories**, and GitHub's flat organisational structure doesn't support hierarchical folders or sub-folders. This creates several challenges:

- **Discovery Problem**: Finding the correct repository to submit an issue can be overwhelming for users
- **Fragmentation**: Related issues are scattered across dozens of repositories
- **Search Difficulty**: Searching for existing solutions requires checking multiple repositories individually
- **Missed Context**: Issues in specialised repos might lack visibility from the broader community

This centralised issue repository solves these problems by providing:
- ✅ A single entry point for all openFyde-related issues
- ✅ Unified search across all project issues
- ✅ Better visibility for common problems and solutions
- ✅ Streamlined triage and routing to appropriate maintainers

## Guidelines for Creating Effective Issues

A well-crafted issue helps everyone - it gets you faster assistance and helps us improve openFyde more effectively. Here's how to create issues that matter:

### 1. **Be Respectful and Constructive**
- Remember there are real people on the other side working hard on this project
- Avoid demanding language; we're all here to help each other
- If frustrated, take a break before writing your issue

### 2. **Search First, Ask Second**
- Check existing issues (both open and closed) for similar problems
- Review the documentation and FAQ before submitting
- Reference any related issues you find, even if they don't fully solve your problem

### 3. **Be Specific and Detailed**
- Use clear, descriptive titles (Bad: "Doesn't work" | Good: "WiFi fails to connect on RockPi 4B with WPA3 networks")
- Include exact error messages, not paraphrases
- Specify version numbers, build dates, and hardware revisions

### 4. **Provide Context and Reproducibility**
- Describe what you were trying to achieve
- List the exact steps to reproduce the issue
- Note if the issue is consistent or intermittent

### 5. **Share Your Attempts**
- Document what you've already tried
- Include any workarounds you've discovered
- Link to relevant forum discussions or documentation you've consulted

### 6. **Be Patient and Responsive**
- Allow time for maintainers to respond (we're often volunteers)
- Respond to follow-up questions promptly
- Update the issue if you find additional information or a solution

## Issue Template

Please use this template when submitting a new issue:

> ### Device Information
> **Board/Device:** [e.g., RockPi 4B, Surface Go 2, Generic x86_64]  
> **openFyde Version:** [e.g., r120-15.1, check with `cat /etc/lsb-release`]  
> **Build Date:** [if building from source]
> 
> ### Issue Category
> - [ ] Building openFyde from source
> - [ ] Running pre-built image on supported device
> - [ ] Hardware compatibility
> - [ ] Software/Package issue
> - [ ] Documentation
> - [ ] Other (please specify)
> 
> ### Environment Setup
> 
> #### For Build Issues:
> **Host OS:** [e.g., Ubuntu 22.04, Debian 12]  
> **CPU:** [e.g., Intel i7-12700K]  
> **RAM:** [e.g., 32GB]  
> **Storage:** [e.g., 500GB available on NVMe SSD]  
> **Build Command Used:**
> ```bash
> # Paste your exact build command here
> ```
> 
> #### For Runtime Issues:
> **Installation Media:** [e.g., USB 3.0 SanDisk 32GB, SD Card Class 10]  
> **Display:** [e.g., HDMI 1080p, eDP internal display]  
> **Power Supply:** [e.g., Official 65W USB-C PD, 12V 3A barrel jack]  
> **Connected Peripherals:** [e.g., USB keyboard, Bluetooth mouse, Ethernet adapter]  
> 
> **Setup Photo/Diagram:**  
> [Consider including a photo showing your hardware setup, especially for connection issues]
> 
> ### Problem Description
> 
> #### Expected Behaviour
> [Describe what you expected to happen]
> 
> #### Actual Behaviour
> [Describe what actually happened]
> 
> #### Steps to Reproduce
> 1. [First step]
> 2. [Second step]
> 3. [Continue...]
> 
> #### Error Messages/Logs
> ```
> [Paste any relevant error messages, kernel logs, or system logs here]
> [Use `dmesg`, `journalctl`, or relevant log files]
> ```
> 
> ### Additional Information
> 
> #### What I've Tried
> - [Solution attempt 1]
> - [Solution attempt 2]
> 
> #### Related Issues/Links
> - [Any related issues or forum posts]
> 
> #### Possible Solution
> [If you have ideas about what might be causing this or how to fix it]

## Examples of Excellent Issues

We've prepared several examples demonstrating how to create effective issue reports:

- [Example 1: Build Failure Issue](./examples/example-build-failure.md) - Demonstrates reporting a build space error with thorough investigation
- [Example 2: Hardware Compatibility Issue](./examples/example-hardware-compatibility.md) - Shows how to document touchscreen driver problems on Surface Go 2
- [Example 3: Software/Package Issue](./examples/example-software-package.md) - Illustrates reporting a Google Drive sync quota issue

These examples showcase:
- Proper use of the issue template
- Appropriate level of technical detail
- Clear problem description and reproduction steps
- Evidence of troubleshooting attempts
- Helpful logs and error messages

---

## Contributing

We appreciate your contributions to making openFyde better! Remember that clear communication and mutual respect make our community stronger. Thank you for taking the time to report issues properly - it helps us help you! 🚀
