# **Network Setup & Troubleshooting: Building a Reliable IT Infrastructure**  

A properly configured network is the foundation of any IT environment. Whether you're setting up a home lab, a small business network, or preparing for an IT role, understanding how to configure and troubleshoot networks is an essential skill.  

In this guide, I will walk you through the process of setting up a functional network, including assigning IP addresses, configuring VLANs, implementing firewall security, and diagnosing common connectivity issues using essential networking tools. By the end of this project, you will have a fully operational network environment and the troubleshooting skills needed to resolve common networking problems.  

---

## **Prerequisites**  
Before we begin, ensure you have the following:  

✅ A computer with sufficient resources (at least **16GB RAM** and **SSD recommended**)  
✅ Virtualization software (**VMware Workstation, VirtualBox, or Hyper-V**)  
✅ Windows Server ISO (**2019 or 2022**) – Available from Microsoft's evaluation site  
✅ Windows 10/11 ISO (**for client machines**)  
✅ A router or virtual network setup (if using virtualization)  

---

## **Step 1: Setting Up Your Virtualized Environment**  

To create a functional network, we first need a virtual environment that simulates a real-world IT setup. This includes setting up a **Windows Server** and **client machines** for testing.  

1️⃣ **Install your virtualization software** (VMware Workstation, VirtualBox, or Hyper-V).  
2️⃣ **Create a new Virtual Machine (VM) for Windows Server**:  
   - Allocate at least **4GB RAM** and **2 CPU cores**  
   - Set the virtual disk size to **50GB or more**  
   - Mount the **Windows Server ISO** and begin installation  
3️⃣ **Create additional VMs for Windows 10/11 clients** following similar steps.  
4️⃣ **Ensure your virtual machines are connected to the same virtual network** to enable communication between them.  

---

## **Step 2: Configuring Your Network**  

Now that our virtual machines are set up, we need to configure basic network settings.  

### **Assigning IP Addresses**  
We need to ensure that our devices can communicate with each other by properly configuring IP addresses.  

1️⃣ **Assign a static IP address to the Windows Server**:  
   - Open **Network and Sharing Center** → **Change adapter settings**  
   - Right-click on your network adapter → **Properties**  
   - Select **Internet Protocol Version 4 (TCP/IPv4)** → Click **Properties**  
   - Enter a static IP (e.g., **192.168.1.10**)  
   - Set the **Subnet Mask** (e.g., **255.255.255.0**)  
   - Set the **Default Gateway** (e.g., **192.168.1.1**, which is your router’s IP)  

2️⃣ **Assign IP addresses to client machines**:  
   - If using **DHCP**, they will receive an IP address automatically.  
   - If using **static IPs**, manually assign each client an IP within the same subnet (e.g., **192.168.1.100, 192.168.1.101, etc.**).  

3️⃣ **Test network connectivity using the** `ping` **command**:  
   - Open **Command Prompt** on a client machine  
   - Type `ping 192.168.1.10` (your server’s IP) and check if it responds  

A successful ping confirms that the devices can communicate over the network.  

---

## **Step 3: Configuring VLANs (If Applicable)**  

If you're working with a managed switch or a virtualized network that supports VLANs, you can segment your network for better security and efficiency.  

1️⃣ **Access your router or switch's management interface** (usually via a web browser).  
2️⃣ **Create VLANs** for different departments or purposes (e.g., **IT, HR, Guest Network**).  
3️⃣ **Assign VLANs to devices** based on their role:  
   - Example: The IT department may use VLAN **10**, HR may use VLAN **20**, and guests may use VLAN **30**.  
4️⃣ **Ensure that routing is correctly set up** so devices on different VLANs can communicate when needed.  

---

## **Step 4: Setting Up Firewall & Security Rules**  

To protect your network, it’s crucial to configure firewall rules that allow only necessary traffic while blocking potential threats.  

1️⃣ **Enable the built-in firewall on your router or server**.  
2️⃣ **Allow only required ports**:  
   - **RDP (Remote Desktop Protocol)** – Port **3389** (if needed)  
   - **SMB (File Sharing)** – Port **445**  
   - **DNS** – Port **53**  
   - **HTTP/HTTPS** – Ports **80/443**  
3️⃣ **Block unnecessary ports** that could be exploited by attackers.  
4️⃣ **Set up internal access rules** to restrict who can access what resources.  

---

## **Step 5: Troubleshooting Network Issues**  

Now that our network is set up, let’s go over some **common networking issues** and how to troubleshoot them.  

### **1️⃣ Checking IP Configurations**  
- Open **Command Prompt** and run:  
  ```sh
  ipconfig /all
  ```
- Verify that the assigned IP, subnet mask, default gateway, and DNS settings are correct.  

### **2️⃣ Testing DNS Resolution**  
- If clients cannot reach the internet or internal resources, test DNS resolution:  
  ```sh
  nslookup google.com
  ```
- If it fails, check that the correct DNS server (e.g., your AD/DNS server or a public one like **8.8.8.8**) is set.  

### **3️⃣ Checking Firewall Logs**  
- If a device cannot access a resource, the firewall may be blocking it.  
- Open Windows Firewall **Advanced Settings** → **Monitor Logs** to check for blocked connections.  

### **4️⃣ Diagnosing Network Path Issues**  
- If network latency or connectivity issues arise, use:  
  ```sh
  tracert google.com
  ```
- This will show the path taken to reach a website and highlight any problematic hops.  

---

## **Conclusion**  

By following this guide, you have successfully set up a working network with essential security measures and troubleshooting techniques. You now have a functional IT environment where devices can communicate securely, and you can diagnose and resolve network issues efficiently.  

Understanding network fundamentals like **IP addressing, VLANs, firewalls, and troubleshooting** is critical in any IT role. With this lab, I now showcase hands-on experience configuring and maintaining a network, which is a valuable skill for IT professionals.
