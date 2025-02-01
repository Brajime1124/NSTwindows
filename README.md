<header style="background-color: #333; color: white; padding: 20px; text-align: center;">
    <h1>Network Setup & Troubleshooting: Building a Reliable IT Infrastructure</h1>
    <p style="font-size: 1.2em;">A properly configured network is the backbone of any IT environment. This guide walks through setting up a functional network, assigning IP addresses, configuring VLANs, implementing firewall security, and troubleshooting common issues using essential networking tools. Mastering these skills is crucial for diagnosing and resolving connectivity problems in any IT setting. </p>
</header>

<ul>
    <li>A computer with enough resources (at least 16GB RAM, SSD recommended)</li>
    <li><strong>Virtualization software</strong> (VMware Workstation, VirtualBox, or Hyper-V)</li>
    <li><strong>Windows Server ISO</strong> (2019 or 2022) – available from Microsoft’s evaluation site</li>
    <li><strong>Windows 10/11 ISO</strong> (for client machines)</li>
</ul>

<h2>Step 1: Set Up the Virtualization Environment</h2>
<ol>
    <li>Install your preferred virtualization software.</li>
    <li>Create a new <strong>Virtual Machine (VM)</strong> for Windows Server:
        <ul>
            <li>Allocate at least <strong>4GB RAM, 2 CPU cores</strong></li>
            <li>Set the virtual disk to <strong>50GB</strong> or more</li>
            <li>Mount the <strong>Windows Server ISO</strong> and begin installation</li>
        </ul>
    </li>
    <li>Create additional VMs for Windows 10/11 clients following similar steps.</li>
</ol>

<h1>Network Setup & Troubleshooting</h1>
<h2>Step 1: Setting Up a Basic Network</h2>
<ol>
    <li>Ensure you have a router or virtual network setup if using virtualization.</li>
    <li>Assign static IP addresses where needed:
        <ul>
            <li>For the server: Use a fixed IP like <code>192.168.1.10</code>.</li>
            <li>For client machines: Use DHCP or assign static addresses.</li>
        </ul>
    </li>
    <li>Test network connectivity using <code>ping</code> commands.</li>
</ol>

<h2>Step 2: Configuring VLANs (If Applicable)</h2>
<ol>
    <li>Access your router or managed switch settings.</li>
    <li>Create VLANs for different departments (e.g., IT, HR, Guests).</li>
    <li>Assign VLANs to appropriate devices.</li>
</ol>

<h2>Step 3: Setting Up a Firewall & Security Rules</h2>
<ol>
    <li>Enable basic firewall protection on the router.</li>
    <li>Block unnecessary ports and allow only required ones (e.g., RDP, SMB).</li>
    <li>Set up internal access rules for better security.</li>
</ol>

<h2>Step 4: Troubleshooting Network Issues</h2>
<ul>
    <li>Use <code>ipconfig /all</code> to check network configurations.</li>
    <li>Test DNS resolution using <code>nslookup</code>.</li>
    <li>Check firewall logs for blocked connections.</li>
    <li>Use <code>tracert</code> to diagnose network path issues.</li>
</ul>

<h2>Conclusion</h2>
<p>With this setup, you have a working network that allows device communication while maintaining security and performance. Proper network troubleshooting skills will help in diagnosing and resolving IT infrastructure issues effectively.</p>
