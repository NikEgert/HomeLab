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
| <img src="Images/python_logo.png" alt="Python Logo" width="40" />       | Python    | A high level programming language for scripting and general purpose. |

---

### 🛠️ Tools

| Logo                                                            | Name  | Description                                                            |
| --------------------------------------------------------------- | ----- | ---------------------------------------------------------------------- |
| <img src="Images/rufus_logo.png" alt="Rufus Logo" width="40" /> | Rufus | A utility to create bootable USBs for installing OS or system recovery |
| <img src="Images/cron_image.png" alt="Cron" width="40" /> | Cron | A time based job scheduler for automating tasks in Unix operating systems. |

---

## 🎓 Personal Guides

- [VLAN Configuration](./Documents/Guides/VLAN_Config.md) - Guide on how I configured VLANs in my home network using a managed switch.

- [Configuring WireGuard VPN](./Documents/Guides/Wireguard_Config.md) - Guide on how I created a WireGuard VPN server to be able to connect to your personal network remotely.

## 📈 HomeLab Development

- [Adapter Configuration](./Documents/HomeLab/Eth-USB_Config.md) - How I configured a NIC bridge to a USB port in order to allow a device without an ethernet port to connect to the internet.

- [Disable Laptop Sleep](./Documents/HomeLab/Laptop_Sleep.md) - How I managed to disable the laptop sleep config on lid shutting in a linux based system.

- [Configuring Proxmox Cluster](./Documents/HomeLab/ConfiguringCluster.md) - Guide on how to create a server cluster within Proxmox.

## 💻 Scripting

- [Docker data backup](./Documents/Scripting/Backup_Script.md) - An overview on how I utilised Docker, Cron and a personalised python script to back up docker data.

- [Automatic VM reboot](./Documents/Scripting/Reboot.md) - How I automated the process of rebooting virtual machines - keeping extensibility in mind.

---

## 🚀 Future developments

- Jenkins
- Malware zoo
- NFS/NAS (for storing VM backup data)

## Pictures

<div align="center">
  <img src="Images/Homelab_pic.jpg" alt="HomeLab" width="500" height="600" />
  <p>My HomeLab setup after creating a 3 node cluster.</p>
</div>
