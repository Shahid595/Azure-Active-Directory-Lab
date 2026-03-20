# Lab 5: Group Policy Objects & Advanced Troubleshooting

## Project Objective
The objective of this lab is to automate resource mapping for domain users using Group Policy Objects (GPO). This lab also documents the real-world troubleshooting steps taken to resolve RDP credential errors, network path blocks, and firewall configurations.

## Technologies Used
* **Windows Server 2022** (Domain Controller)
* **Windows 11 Pro** (Client Workstation)
* **Active Directory Domain Services (AD DS)**
* **Group Policy Management**
* **Windows Defender Firewall**

---

## Technical Steps & Proof of Work

### Step 1: GPO Configuration
I created a GPO to map a network drive (Z:) to `\\dc-1\Shares`. I used the **Replace** action to ensure the drive maps reliably every time the user logs in.

![GPO Settings](lab5-02-drive-map-settings.jpg)
*Caption: Configuring Group Policy Preferences for Drive Mapping.*

### Step 2: Troubleshooting RDP & Credentials
Initially, the domain user `john.it` could not RDP into the client machine. I diagnosed this as a permissions issue and resolved it by adding the account to the **Remote Desktop Users** group.

![RDP Error](image_ab1160.png)
![RDP Fix](lab5-06-domain-user-added-to-rdp.jpg)
*Caption: Identifying and fixing the Remote Desktop 'Credentials did not work' error.*

### Step 3: Resolving Network Path Access
The client could not reach the file share due to the Windows Firewall on the DC. I enabled **File and Printer Sharing (SMB-In)** to allow traffic on Port 445.

![Firewall Fix](image_b58a40.jpg)
*Caption: Enabling SMB-In rules in Windows Defender Firewall.*

### Step 4: Verification
After running `gpupdate /force`, I verified that the policy was successfully applied and the Z: drive was visible in 'This PC'.

![GPResult](lab5-08-gpresult-user-policy.jpg)
![Success](mapped-drive-visible.jpg)
*Caption: Final verification of the mapped Z: drive.*
