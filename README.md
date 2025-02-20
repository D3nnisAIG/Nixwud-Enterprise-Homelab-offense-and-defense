# Malware Analysis

Malware Analysis Project Setup
## Project Overview
In this project, I aim to perform detailed malware analysis in a controlled and isolated environment. The entire setup is emulated using VirtualBox, featuring Windows 10 and specialized virtual machines (VMs) to ensure the safety of my host device.
## Lab Environment
### VirtualBox
I am using VirtualBox to simulate the malware analysis lab. VirtualBox is a powerful x86 and AMD64/Intel64 virtualization product for enterprise as well as home use. It is freely available as Open Source Software under the terms of the GNU General Public License (GPL) version 2.
### Operating Systems and Tools
- **Windows 10**: The primary OS for malware analysis.
- **FlareVM**: A fully customizable Windows-based security distribution for malware analysis, incident response, penetration testing, etc.
- **REMnux**: A Linux distribution for reverse-engineering and analyzing malicious software, primarily installed for specific analysis tools not available on Windows.
### Network Setup
The lab environment has its dedicated network setup to isolate the VMs from the host device. This ensures that any malicious software executed within the lab does not affect the host machine.
## Steps for Setting Up the Lab
### Step 1: Install VirtualBox
1. Download and install VirtualBox from [VirtualBox Downloads][https://www.virtualbox.org/wiki/Downloads].
2. Follow the installation instructions for your specific operating system.
### Step 2: Setting Up Windows 10 VM
1. Create a new VM in VirtualBox and select Windows 10 as the operating system.
2. Configure the VM settings with appropriate resources (RAM, CPU, etc.).
3. Install Windows 10 on the VM.
4. After installation, install FlareVM by following the instructions provided [here]([URL]).
### Step 3: Setting Up REMnux VM
1. Download the REMnux OVA file from [REMnux Downloads]([URL]).
2. Import the OVA file into VirtualBox.
3. Configure the VM settings according to your needs.
### Step 4: Network Configuration
1. Set both VMs to use a Host-Only Adapter.
2. Create an internal network within VirtualBox to ensure that the VMs can communicate with each other but remain isolated from the host network.
## Safety Precautions
- Always ensure that the VMs are isolated from the host network to prevent any potential spread of malware.
- Take regular snapshots of your VMs to revert to a clean state if needed.
- Do not share files between the host and the VMs unless necessary.
## Conclusion
With this setup, I can safely analyze malware without the risk of infecting my host device. VirtualBox, Windows 10 with FlareVM, and REMnux provide a robust environment for thorough malware analysis.
Feel free to check out the repository for detailed analysis and findings: [GitHub Repository]([URL])


