# NAS Setup and Configuration

## Overview
I built a NAS using salvaged parts and some budget-friendly purchases. This document details the setup process, including hardware installation, initial network configuration, and instructions on configuring my NAS using TrueNAS SCALE.

## Hardware Setup
- Found a case and other components for free.
- Purchased:
  - **5x 500GB HDDs** (cheap deal).
  - **5x HDD chassis** for installation.
  - **256GB SSD** (installed TrueNAS Scale on this).
  - **5x SATA power connector extensions** (bought for cheap/laying around).
  - **SATA data cable extension** (bought for cheap).
- Installed the HDDs into the chassis and mounted everything inside the case.

## Software Installation
- Installed **TrueNAS Scale**, which was flashed onto a USB using Rufus, onto the **256GB SSD**.

## Network Configuration
- Connected the NAS to the local network and verified connectivity using `ping`.
- Could **ping the default gateway** but not the NAS from other devices.
- Found the issue: **Network type was set to Public instead of Private**.
- Changed the setting to **Private**, and connectivity was restored.

## RAIDZ2 and Pool Configuration

### What is RAIDZ2?
RAIDZ2 is a **ZFS RAID level** that provides **double parity**, allowing the system to tolerate up to **two drive failures** without data loss. This offers better protection than RAIDZ1, which can only tolerate one failure.

### Creating a Pool
1. **Log into TrueNAS SCALE** via the web interface.
2. **Navigate to Storage > Pools > Create Pool**.
3. **Select all five 500GB HDDs** and choose **RAIDZ2** as the layout.
4. **Confirm and create the pool**, naming it `important`.

## Creating a Dataset

### What is a Dataset?
A dataset in TrueNAS SCALE is like a **logical volume** within a pool that can have different permissions, compression settings, and quotas. It helps organize and manage files efficiently.

### Steps to Create a Dataset:
1. **Go to Storage > Pools** and select `important`.
2. Click **Add Dataset**, name it `Share`.
3. Set permissions as required (default settings work for most cases).

## Setting Permissions for Proxmox Cluster
To allow Proxmox to access the dataset, we need to modify its permissions:

1. **Go to Storage > Pools > important > Share > Edit Permissions**.
2. Set **Group and Other permissions** to `rwx` (Read, Write, Execute).
3. Apply changes.

## Network Path
The dataset is available at:
`/mnt/important/Share`

<!--> include section of configuring on proxmox (also images) <-->

## Next Steps
- include images of the process
- Set up **snapshot schedules** for data protection.

**Status: IN PROGRESS**


