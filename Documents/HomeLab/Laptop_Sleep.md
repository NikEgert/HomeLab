# Disable Laptop Sleep on Proxmox

To prevent your Proxmox host (running on a laptop) from entering sleep mode, you need to adjust the power management settings.

## Steps to Disable Sleep:

#### 1. **Edit the `logind.conf` file:**
   
Open the `logind.conf` file with a text editor like `nano`:

```bash
nano /etc/systemd/logind.conf
```

#### 2. **Modify the following settings:**

In the `logind.conf` file, find and uncomment the following line:

```bash
#HandleLidSwitch=suspend
```

and change it to:

```bash
HandleLidSwitch=ignore
```

Save and close the file.

#### 3. **Restart the systemd-logind service:**

Apply the changes by restarting the `systemd-logind` service:

```bash
systemctl restart systemd-logind
```

