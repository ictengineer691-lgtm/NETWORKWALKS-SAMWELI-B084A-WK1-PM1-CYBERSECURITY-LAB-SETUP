# NETWORKWALKS-SAMWELI-B084A-WK1-PM1-CYBERSECURITY-LAB-SETUP
Cybersecurity Lab Environment Setup

Setting up a virtual lab for cybersecurity learning and ethical hacking practice.

Project Overview

This project is about setting up a cybersecurity lab using VirtualBox and Kali Linux.

The lab provides a safe environment where I can learn and practise cybersecurity skills. It will help me understand how networks work and how to use security tools for testing.

I created a private virtual network using the "10.0.0.0/24" subnet. The network can be used to connect Kali Linux with other virtual machines for future security testing.

Objectives

The main objectives of this project are to:

a.Install VirtualBox on my computer.
b.Set up Kali Linux as my testing machine.
c.Create a NAT Network using "10.0.0.0/24".
d.Configure the Kali Linux network adapter.
c.Set up and test network connectivity.
d.Check IP addressing and DNS resolution.
e.Create a snapshot for system recovery.
f.Take screenshots and document the setup process.

  Purpose of the Lab

The purpose of this lab is to help me learn cybersecurity through practical work.

I plan to use it for:

- Network scanning
- Port scanning
- Learning Nmap
- Network traffic analysis
- Vulnerability testing
- Web security testing
- Practising ethical hacking

Important: I will only test systems that I own or have permission to test.

Lab Architecture

The lab uses VirtualBox to run Kali Linux on my computer.

The Kali Linux machine connects to a NAT Network with the address range "10.0.0.0/24".

Other virtual machines can be added to the same network later to practise security testing between machines.

  ##Network Design


          My Computer
          Windows Host
                ||
             VirtualBox
                ||
            NAT Network
           10.0.0.0/24
                ||
           Kali Linux
          10.0.0.2/24
                ||
       Future Target Machines
         10.0.0.3 onwards


Lab Configuration

| Component | Configuration |
|---|---|
| Host Operating System | Windows |
| Virtualization Software | Oracle VirtualBox |
| Testing Machine | Kali Linux |
| Network Type | NAT Network |
| Network Address | "10.0.0.0/24" |
| Kali IP Address | "10.0.0.2/24" |
| Default Gateway | "10.0.0.1" |
| DNS Server | "8.8.8.8" |
| Future Target Machines | "10.0.0.3" onwards |



Lab Setup Procedure

Step 1: Install 7-Zip

I used 7-Zip to extract the Kali Linux virtual machine files when needed.

Download: https://www.7-zip.org/download.html

Step 2: Install VirtualBox

I installed Oracle VirtualBox to create and manage virtual machines on my computer.

VirtualBox allows me to run Kali Linux without replacing my main operating system.

Download: https://www.virtualbox.org/wiki/Downloads

Step 3: Create a NAT Network

I created a NAT Network in VirtualBox for the cybersecurity lab.

The network was planned with the following settings:

- Network name: `NatNetwork"
- IPv4 network: "10.0.0.0/24"
- DHCP: Enabled
- IPv6: Disabled

The NAT Network allows connected virtual machines to communicate with one another and can provide internet access through network address translation.

screenshot of My NAT Network settings.
<img width="949" height="479" alt="nat-network png" src="https://github.com/user-attachments/assets/f2245886-d6a5-4ac3-adc6-654669610d89" />


Step 4: Set Up Kali Linux

I downloaded Kali Linux from its official website and imported the virtual machine into VirtualBox.

I configured the virtual machine's network adapter to use the lab's NAT Network.

The main settings were:

- Network adapter: Adapter 1
- Network type: NAT Network
- Network name: "NatNetwork"
- Memory: 2048 MB

I also configured a shared folder if needed to transfer files between Windows and Kali Linux.

Download: https://www.kali.org/get-kali/

screenshot showing Kali Linux running in My VirtualBox.
<img width="959" height="463" alt="kali-linux png" src="https://github.com/user-attachments/assets/d9d1a136-1535-45b9-af56-63c466fd594c" />


Step 5: Configure the Network

I checked the Kali Linux network settings to make sure the machine was using the correct IP address and network.

The planned configuration was:

- IP address: "10.0.0.2"
- Subnet mask: "255.255.255.0"
- Gateway: "10.0.0.1"
- DNS server: "8.8.8.8"

A consistent IP address makes it easier to identify the Kali machine during future lab exercises.

screenshot of the network settings or the output of the "ip a" command.

<img width="953" height="467" alt="Screenshot 2026-10-26 190722" src="https://github.com/user-attachments/assets/f161ab4c-1ba9-4ac0-83d3-6c7ffa8f40e9" />

Step 6: Create a Virtual Machine Snapshot

After setting up Kali Linux, I created a snapshot to save a clean copy of the virtual machine's current state.

"Clean Kali"

The snapshot below can help me return to the saved state if a future experiment causes problems.

<img width="950" height="476" alt="image" src="https://github.com/user-attachments/assets/205d9e22-9b6a-4873-b322-aa9150c29018" />



Lab Verification

I used basic commands to check the network and security tools.

| Test | Command | Purpose |
|---|---|---|
| Check IP address | `ip a` | Check the IP address assigned to Kali |
| Check routes | `ip route` | View the gateway and routing information |
| Test gateway | `ping 10.0.0.1` | Check communication with the gateway |
| Test internet | `ping 8.8.8.8` | Check external network connectivity |
| Test DNS | `nslookup networkwalks.com` | Check whether DNS can resolve a domain |
| Check Nmap | `nmap --version` | Confirm that Nmap is installed |
| Check snapshot | Restore the saved snapshot | Confirm that the saved state can be restored |

The tests should be run and their actual results recorded. A successful ping to an IP address does not always mean DNS is working, so both should be tested separately.

### Example Results

Record your actual results below after completing the tests.

- Kali IP address: `10.0.0.2/24`
- Default gateway: `10.0.0.1`
- DNS server: `8.8.8.8`
- Internet connection: Record the actual result
- Nmap installation: Record the actual result
- Snapshot: Record whether restoration was successful

## 🐞 Problems Encountered and Solutions

### Problem: Loss of Internet Connection

After configuring the virtual network in VirtualBox, I experienced a loss of internet connectivity in Kali Linux.

**Solution:** I used the `nmcli` command to inspect and manage the network connection in Kali Linux. I checked the network connection settings and worked on restoring internet access.

**Lesson Learned:** I learned how to use `nmcli` to troubleshoot network connectivity and how important it is to verify internet access after configuring a virtual network.

<img width="957" height="482" alt="internet problem" src="https://github.com/user-attachments/assets/a6119940-d96a-42b3-a4ff-e1c3dbb3599c" />



## 💡 What I Learned

Through this project, I learned the importance of preparing a proper environment before starting cybersecurity testing.

### 1. Virtual Machines

I learned how to use VirtualBox to run Kali Linux on my computer without replacing Windows.

### 2. Network Configuration

I learned about IP addresses, subnet masks, gateways, DNS servers, and virtual network adapters.

### 3. NAT Network

I learned that a NAT Network can connect multiple virtual machines and provide external network access.

### 4. Network Testing

I learned how to use commands such as `ip a`, `ping`, and `nslookup` to check network settings and connectivity.

### 5. Snapshots

I learned that snapshots are useful for saving a working state before performing experiments.

### 6. Documentation

I learned that screenshots, commands, test results, and clear documentation help make a technical project easier to understand.

## 🔐 Security and Ethical Use

This lab is for educational purposes and authorized security testing only.

I will use it to improve my practical cybersecurity skills and will not test systems without permission.

## 🔗 Tools and Resources

- [7-Zip](https://www.7-zip.org/download.html)
- [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Kali Linux](https://www.kali.org/get-kali/)
- [Nmap](https://nmap.org/)

 Author

Name:Samweli Kinanda

Field: Information Technology and Cybersecurity

GitHub: https://github.com/ictengineer691-lgtm/NETWORKWALKS-SAMWELI-B084A-WK1-PM1-CYBERSECURITY-LAB-SETUP/tree/main.

LinkedIn: Add your LinkedIn profile link here.

Project Information

- Project: Cybersecurity Lab Environment Setup
- Tools: VirtualBox and Kali Linux
- Network: NAT Network
- Subnet: `10.0.0.0/24`
- Purpose: Cybersecurity learning and ethical hacking practice
- Repository: Cybersecurity Lab Setup

