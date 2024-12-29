# Nik's HomeLab

## Project Overview

### 🚀 Project Status: **IN DEVELOPMENT**

This project is a personal exploration aimed at deepening my understanding of networking, servers and related technologies. It’s a hands on learning experience to help me grow my skills and gain practical knowledge by experimenting with different concepts and tools. While it is still in the early stages, my goal is to learn by creating and implementing projects within the [HomeLab](https://en.wikipedia.org/wiki/Home_server).

---

### 🖥️ Hardware Overview

#### Servers

- **1 × Dell G3 15 3590 laptop**

  - **CPU:** Intel(R) Core(TM) i5-9300H CPU @ 2.40GHz
  - **RAM:** 8GB
  - **SSD:** 512GB

- **1 × HP EliteBook Folio 1040 G3 laptop**

  - **CPU:** Intel(R) Core(TM) i5-6200U CPU @ 2.30GHz
  - **RAM:** 8GB
  - **SSD:** 256GB

- **1 × HP Pavilion x360 Convertible laptop**
  - **CPU:** Intel(R) Core(TM) i5-8250U CPU @ 1.60GHz
  - **RAM:** 8GB
  - **SSD:** 256GB

#### Networking

- **D-Link DGS-1100-08 switch**

  - **Ports:** 8
  - **Speed:** 1000Mbps

- **D-Link DGS-1100-08V2 switch**

  - **Ports:** 8
  - **Speed:** 1000Mbps

- **2x Type-C3.1/USB 1000Mbps Ethernet Adapters**

---

### ✨ Features

The system includes the following features:

- **Minecraft server:** The system hosts a Minecraft server within a Docker container running on a Debian-12 virtual machine.
- **VPN server:** The system uses a WireGuard VPN server running in a Proxmox container to provide secure, fast, and encrypted VPN access.
- **Python Backup Script:** The system hosts a CRON job with a python script that backups up data periodically.

---

### ⚙️ Tech Stack

| Logo                                                                    | Name      | Description                                              |
| ----------------------------------------------------------------------- | --------- | -------------------------------------------------------- |
| <img src="Images/proxmox_logo.png" alt="Proxmox Logo" width="40" />     | Proxmox   | Open-source virtualiation platform.                      |
| <img src="Images/docker_logo.png" alt="Docker Logo" width="40" />       | Docker    | Containerisation platform for creating and running apps. |
| <img src="Images/wireguard_logo.png" alt="WireGuard Logo" width="40" /> | WireGuard | Fast, modern VPN technology with strong encryption.      |

---

### 🛠️ Tools

| Logo                                                            | Name  | Description                                                            |
| --------------------------------------------------------------- | ----- | ---------------------------------------------------------------------- |
| <img src="Images/rufus_logo.png" alt="Rufus Logo" width="40" /> | Rufus | A utility to create bootable USBs for installing OS or system recovery |

---

## 🎓 Personal Guides

- [VLAN Configuration](./Documents/Guides/VLAN_Config.md)

- [Configuring WireGuard VPN](./Documents/Guides/Wireguard_Config.md)

## 📈 HomeLab Development

- [Adapter Configuration](./Documents/HomeLab/Eth-USB_Config.md)

- [Disable Laptop Sleep](./Documents/HomeLab/Laptop_Sleep.md)

  <!---
  TODO
  --->

- [Configuring Proxmox Cluster](./Documents/HomeLab/CondfiguringCluster.md)

## 💻 Scripting

- [Docker data backup](./Documents/Scripting/Backup_Script.md)

---

## 🚀 Future developments

- Jenkins
- Malware zoo
- NFS/NAS (for storing VM backup data)

## Pictures

<div align="center">
  <img src="Images/Homelab_pic.jpg" alt="HomeLab" width="500" height="600" />
  <p>My HomeLab setup!</p>
</div>
