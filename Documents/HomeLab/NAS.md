# NAS Setup and Configuration  

## Overview  
I built a NAS using salvaged parts and some budget-friendly purchases. This document details the setup process, including hardware installation and initial network configuration.  

## Hardware Setup  
- Found a case and other components for free.  
- Purchased:
  - **5x 500GB HDDs** (cheap deal).  
  - **5x HDD chassis** for installation.  
  - **256GB SSD** (installed TrueNAS Scale on this).  
  - **5x SATA power connector extension** (bought for cheap/laying around). 
  - **SATA data cable extension** (bought for cheap).  
- Installed the HDDs into the chassis and mounted everything inside the case.  

## Software Installation  
- Installed **TrueNAS Scale**, which was flashed onto a USB using Rufus, onto the **256GB SSD**.  

## Network Configuration  
- Connected the NAS to the local network and verified connectivity using `ping`.  
- Could **ping the default gateway** but not the NAS from other devices.  
- Found the issue: **Network type was set to Public instead of Private**.  
- Changed the setting to **Private**, and connectivity was restored.  

## Next Steps  
- Configure RAID for the **5x 500GB HDDs**.  

**Status: IN PROGRESS**  