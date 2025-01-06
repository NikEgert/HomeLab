# Proxmox VM Scheduled Reboot for Minecraft Server  

This tutorial provides a setup for automating the reboot of a Proxmox VM, In my case, I utilised this to manage RAM bloat for my Minecraft server VM. A cron job runs a bash script at 5:00 AM (when my friends are most likely not playing I hope 💀) every 3 days to reboot the VM, ensuring stable performance.  

---

## Prerequisites  

- Proxmox VE installed and configured.  
- A Proxmox VM.  
- Sudo/root access to the Proxmox host.  

---

## Setup Instructions  

### Step 1: Create the Bash Script  

1. Log in to your Proxmox host.  
2. Create a directory for scripts if it doesn’t already exist (assuming you are root user):  
    ```bash  
    mkdir /root/scripts  
    ```
3. Create `reboot.sh` script:
    ```bash
    touch /root/scripts/reboot.sh
    ```
4. Add the follow code to the script:
    ```bash
    #!/bin/bash
    qm reboot $1 # takes the first argument as the VM number
    ```

### Step 2: Test the Script

Before setting up the cron job, test the script manually:
```bash
bash /root/scripts/reboot.sh <VM Number>
```
This will reboot the specified VM.

### Step 3: Set Up the Cron Job

1. Open the crontab editor:
    ```bash
    crontab -e  
    ```
2. Add the following line to schedule the job at 5:00 AM every 3 days:
    ```bash
    0 5 */3 * * bash /root/scripts/reboot.sh <VM Number>
    ```
--- 
### Notes
- The `qm reboot` command is specific to Proxmox and can be found in the documentation
- Ensure the cron job has sufficient permission to execute the file path
- if issues arise, system logs can be checked with:
    ```bash
    journalctl -t CRON
    ```


