<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

Sharing out resources over the network by
creating sample file shares with various permissions.

Set the following permissions (share the folder) for the “Domain Users” group:

Folder: “read-access”, Group: “Domain Users”, Permission: “Read”

Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”

Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write


Normal domain users are granted permission to only read from the "read-access" group, read and write in the "write-acces" group, and not access the "no-access" group at all. 
Admin only are allowed permission to access the "no access" group.


<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/HRc9yfM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
On DC-1 (domain controller), on the C:\ drive, create 3 folders: “read-access”, “write-access”, “no-access”,
</p>
<br />

<p>
<img src="https://i.imgur.com/yy6bmz8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set the following permissions (share the folder) for the “Domain Users” group: Folder: 
  
  “read-access”, Group: “Domain Users”, Permission: “Read”
  
  Normal domain users are granted permission to only read from the "read-access" group.
</p>
<br />

<p>
<img src="https://i.imgur.com/KqbRUVr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set the following permissions (share the folder) for the “Domain Users” group: Folder:
  
 Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write” 
  
  Normal domain users are granted permission to  read and write in the "write-acces" group.
</p>
<br />

<p>
<img src="https://i.imgur.com/vamyV36.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set the following permissions (share the folder) for the “Domain Users” group:
  
 Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write 
  
  Normal domain users are not granted permission to access the "no-access" group at all.
  
  Only Domain Admin are allowed permission to access the "no access" group.
   
</p>
<br />
