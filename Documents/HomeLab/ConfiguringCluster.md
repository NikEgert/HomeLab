# Creating a Proxmox Cluster Using the Web Interface

This guide explains how to create a Proxmox cluster through the web interface.

---

## Benefits of Creating a Proxmox Cluster

Setting up a Proxmox cluster provides several advantages:

1. **High Availability**: Ensures virtual machines and containers remain operational even if one node fails.
2. **Resource Sharing**: Enables efficient use of resources by distributing workloads across multiple nodes.
3. **Centralised Management**: Manage all nodes from a single interface for simplified administration.
4. **Live Migration**: Move VMs between nodes without downtime for maintenance or load balancing.
5. **Scalability**: Easily add more nodes to the cluster as your infrastructure grows.

---

## Prerequisites

1. At least **three nodes** with Proxmox VE installed. A cluster relies on quorum for decision making, which ensures stability and prevents data corruption. Quorum requires a majority of nodes to agree on changes. Having at least three nodes allows the cluster to maintain functionality even if one node fails.
2. **Network connectivity** between nodes. Seamless communication is vital for cluster operations, enabling essential features like high availability and live migration of virtual machines.
3. **Unique hostnames** for each node. Unique identifiers are crucial to avoid conflicts and ensure accurate communication within the cluster.
4. **NTP configuration** on all nodes. Synchronised time across nodes is essential for consistent scheduling and reliable replication, which underpin the cluster's performance and integrity.

---

## Step 1: Access the Proxmox Web Interface

1. Open a browser and navigate to the web interface of your Proxmox nodes.  
   Example: `https://<node-ip>:8006`.

2. Log in as the `root` user.

---

## Step 2: Create the Cluster on the First Node

1. Navigate to **Datacenter** in the left-hand menu.
2. Click on the **Cluster** tab.
3. Click **Create Cluster**.
4. Enter a name for your cluster.
5. Click **Create**.

---

## Step 3: Join Additional Nodes to the Cluster

1. On the first node (where the cluster was created), go to the **Cluster** tab.
2. Copy the **Join Information** from the displayed cluster settings.
3. On the additional nodes, open their web interface.
4. Navigate to **Datacenter > Cluster**.
5. Click **Join Cluster**.
6. Paste the join information copied from the first node.
7. Enter the `root` password for the first node.
8. Click **Join**.

---

## Step 4: Verify the Cluster

1. On any node, go to **Datacenter > Cluster** in the web interface.
2. All nodes should now be listed in the cluster.

---

## Step 5: Test the Cluster

1. From the web interface, navigate to **Datacenter > Cluster**.
2. Test live migration:
   - Right-click a virtual machine.
   - Select **Migrate**.
   - Choose the destination node.
   - Click **Start Migration**.

---

## Troubleshooting

- If a node doesn’t appear in the cluster, ensure it has:
  - Network connectivity with the master node.
  - The correct join information.
- Use the **Logs** tab in the web interface to troubleshoot errors.

---
