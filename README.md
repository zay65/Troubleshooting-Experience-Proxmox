# Troubleshooting-Experience-Proxmox
<h3> My experience troublshooting issues within Proxmox </h3>

<h2>Internet connectivity</h2>
Issue
- <b2> Failure logging in to Azure portal from Proxmox Windows Server VM (Domain Controller) <b2>

Environment:
- <b2> Proxmox Virtual Environment <b2>

Troubleshooting Steps:
1. Verified network connectivity (tried accessing other websites)
2. Performed nslookup of domain
3. Tested port 443 connectivity to portal.azure.com
4. In "Hardware" section of VM, I changed the virtual ethernet adapter "Model" (from "Intel" to "VirtIO (paravirtualized))"

Root Cause:

- <b2> Connectivity issues caused by incompatible "hardware" <b2>

Resolution:

- <b2> Changed "hardware" to most compatible with vm <b2> 

Prevention:

- <b2> Document instruction in ticketing system to always set Windows VM "Hardware" model to VirtIO <b2>


                                   nslookup & port 443 connectivity tested

 <p align="center">
    <img src="https://github.com/zay65/Troubleshooting-Experience-Proxmox/blob/1812448be7ddd9de7bb02e8dcd186b220b0b8804/Port%20443%20Outbound%20Test.png" alt="Sample Image"/>
  </p>

                                                 Hardware change

<p align="center">
    <img src="https://github.com/zay65/Troubleshooting-Experience-Proxmox/blob/1812448be7ddd9de7bb02e8dcd186b220b0b8804/Ethernet%20Adapter%20change.png" alt="Sample Image"/>
  </p>

                                      Internet connectivity within vm enabled

<p align="center">
    <img src="https://github.com/zay65/Troubleshooting-Experience-Proxmox/blob/731778bd5ee194d10711da65248c18d3097fc890/Portal.azure.com%20accessed.png" alt="Sample Image"/>
  </p>
