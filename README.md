# Dual-Boot-System-Deployment-Cross-Platform-Network-Driver-Recovery
Design and deploy a dual-boot environment on legacy enterprise hardware to support cybersecurity lab work (Linux) and Windows-based enterprise tooling, while maintaining system stability, proper partitioning, and recoverability.

System Preparation

Performed complete disk wipe to remove previous OS and partitions

Configured BIOS:

Boot Mode: UEFI

SATA Mode: AHCI

Secure Boot temporarily disabled for installation

Created bootable installation media:

Windows 10 via Microsoft Media Creation Tool

Ubuntu 22.04 via Balena Etcher

Windows Deployment

Installed Windows 10 Pro using GPT partitioning

Manually allocated ~120GB primary partition

Preserved remaining disk space as unallocated for Linux deployment

Verified successful boot and system stability

Confirmed correct Windows Boot Manager configuration in UEFI

Ubuntu Deployment

Installed Ubuntu 22.04 LTS alongside Windows Boot Manager

Utilized automatic partitioning within unallocated space

GRUB bootloader configured for dual-boot environment

Verified OS selection at startup

Confirmed successful Linux network initialization

Post-Installation Issue: Network Adapter Not Detected (Windows)
Problem

After installation, Windows did not detect the onboard Ethernet controller. Ubuntu confirmed full network functionality, isolating the issue to a missing Windows driver.

Diagnosis

Verified hardware functionality in Ubuntu

Identified network controller via:

lspci | grep -i ethernet


Confirmed driver absence in Windows Device Manager

Resolution

Downloaded appropriate Windows 10 x64 network driver from Dell Support

Transferred driver from Ubuntu to Windows partition

Installed manually in Windows

Restored full network connectivity

Technical Skills Demonstrated

UEFI/GPT configuration

Manual partition planning

GRUB bootloader implementation

Cross-platform troubleshooting

Driver-level issue resolution

BIOS configuration and firmware management

Legacy enterprise hardware deployment

OS recovery methodology

Outcome

Fully operational dual-boot system capable of:

Linux-based cybersecurity labs

Bash scripting and tool development

Windows enterprise simulation

Cross-OS troubleshooting and recovery operations

This system now serves as a dedicated cybersecurity learning and testing environment.
