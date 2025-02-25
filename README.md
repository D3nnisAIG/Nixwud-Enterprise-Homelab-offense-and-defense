# Malware Analysis

Malware Analysis Project Setup
## Project Overview
In this project, I aim to perform detailed malware analysis in a controlled and isolated environment. The entire setup is emulated using VirtualBox, featuring Windows 10, Remnux and a specialized virtual machines network to ensure the safety of my host device.

![Image](https://github.com/user-attachments/assets/60ec9f78-d0f7-4f6d-a578-f8020c469f9f)

## Lab Environment
### VirtualBox
I am using VirtualBox to simulate the malware analysis lab. VirtualBox is a powerful x86 and AMD64/Intel64 virtualization product for enterprise as well as home use. It is freely available as Open-Source Software under the terms of the GNU General Public License (GPL) version 2.
### Operating Systems and Tools
- **Windows 10**: The primary OS for malware analysis.
- **FlareVM**: A fully customizable Windows-based security distribution for malware analysis, incident response, penetration testing, etc.
- **REMnux**: A Linux distribution for reverse-engineering and analyzing malicious software, primarily installed for specific analysis tools not available on Windows.
### Network Setup
The lab environment has a dedicated network setup that isolates the VMs from the host device. This ensures that any malicious software executed within the lab does not affect the host machine.
## Steps for Setting Up the Lab
### Step 1: Install VirtualBox
1. Download and install VirtualBox from [VirtualBox Downloads. https://www.virtualbox.org/wiki/Downloads].
2. Follow the installation instructions for your specific operating system.
### Step 2: Setting Up Windows 10 VM
1. Create a new VM in VirtualBox and select Windows 10 as the operating system.
2. Configure the VM settings with appropriate resources (RAM, CPU, etc.).
3. Install Windows 10 on the VM.
4. After installation, install FlareVM by following the instructions provided [here][https://github.com/mandiant/flare-vm].
### Step 3: Setting Up REMnux VM
1. Download the REMnux OVA file from [REMnux Downloads][https://remnux.org/].
2. Import the OVA file into VirtualBox.
3. Configure the VM settings according to your needs.

### Step 4: Virtual Machine Network Setup Guide
## 1. Open VirtualBox and Select Tools
- Launch VirtualBox.
- Navigate to the `Tools` section.
## 2. Create a New Network
- Click on the three vertical bars and select `Network` from the drop-down menu.
- Click on the `Create` icon.
- Confirm by clicking `Yes` to allow VM make changes.
## 3. Configure the New Network
- Left-click the newly created network and select `Properties`.
- Type an IP address. For example, use `10.0.0.1` (easy to recognize).
- Leave the default subnet mask as it is.
## 4. Configure DHCP Server
- Next, click `DHCP Server` and enable the server option.
- Change the following settings:
- **Server Address**: `10.0.0.2`
- **Lower Address Bound**: `10.0.0.3`
- **Upper Address Bound**: `10.0.0.254`
- **Click** `Apply`.  
## Step 5: Setting Up Connectivity Between REMnux and FlareVM
To ensure successful connectivity between our REMnux box and FlareVM box, follow these steps:
1. **Configure Network Settings in VirtualBox**:
- Open VirtualBox and go to your FlareVM machine.
- Click on `Machine` and select `Settings`.
- Navigate to the `Network` tab.
- Attach to `NAT` and then select `Host-Only Adapter`.
- Choose the VirtualBox host-only adapter from the list.
- Click `OK`.
- You should see that the internet connection is disabled on the bottom right, which is a good sign.
2. **Repeat for REMnux**:
- Go to your REMnux machine.
- Click on `Machine` and select `Settings`.
- Navigate to the `Network` tab.
- Attach to `Host-Only Adapter`.
- Click `OK`.
3. **Configure Network Adapter in FlareVM**:
- Go to the search bar in FlareVM and type in `Ethernet settings`.
- Click on `Change adapter options`.
- Find the Ethernet connection, right-click and select `Properties`.
- Select `Internet Protocol Version 4 (TCP/IPv4)` and click on `Properties`.
- Set the DNS server to the REMnux IP address, e.g., `10.0.0.4`.
- Click `OK`.
4. **Confirm Connectivity**:
- Open PowerShell in FlareVM.
- Confirm the IP address by typing `ipconfig`. For example, it might be `10.0.0.3`.
- Ping the REMnux IP address: `ping 10.0.0.4`. You should receive a reply.
- Switch to REMnux and ping the FlareVM IP address: `ping 10.0.0.3`. You should also receive a reply.
By following these steps, you ensure that both virtual machines can communicate with each other while being isolated from the host's primary network.

## Safety Precautions
- Always ensure that the VMs are isolated from the host network to prevent any potential spread of malware.
- Take regular snapshots of your VMs to revert to a clean state if needed.
- Do not share files between the host and the VMs unless necessary.

## Conclusion
With this setup, I can safely analyze malware without the risk of infecting my host device. VirtualBox, Windows 10 with FlareVM, and REMnux provide a robust environment for thorough malware analysis.

