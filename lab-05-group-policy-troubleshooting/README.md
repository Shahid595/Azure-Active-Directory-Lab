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

<img width="1687" height="943" alt="lab5-02-drive-map-settings" src="https://github.com/user-attachments/assets/c19b9c93-c70d-462b-b7aa-b5fd0256fed6" />
*Caption: Configuring Group Policy Preferences for Drive Mapping.*

### Step 2: Troubleshooting RDP & Credentials
Initially, the domain user `john.it` could not RDP into the client machine. I diagnosed this as a permissions issue and resolved it by adding the account to the **Remote Desktop Users** group.

<img width="557" height="612" alt="image_ab116" src="https://github.com/user-attachments/assets/2d2d723b-e711-4bbf-885f-c72e4a878281" />
<img width="1632" height="970" alt="lab5-06-domain-user-added-to-rdp" src="https://github.com/user-attachments/assets/dda1085d-43d2-4797-8438-254e2f1faca4" />

*Caption: Identifying and fixing the Remote Desktop 'Credentials did not work' error.*

### Step 3: Resolving Network Path Access
The client could not reach the file share due to the Windows Firewall on the DC. I enabled 

**File and Printer Sharing (SMB-In)** to allow traffic on Port 445.

![image_b58a40](https://github.com/user-attachments/assets/78366298-30a1-47ec-8df7-dd1ac3bf94fa)
*Caption: Enabling SMB-In rules in Windows Defender Firewall.*

### Step 4: Verification
After running `gpupdate /force`, I verified that the policy was successfully applied and the Z: drive was visible in 'This PC'.

<img width="1721" height="946" alt="lab5-08-gpresult-user-policy" src="https://github.com/user-attachments/assets/bcd4a620-e90c-4067-b042-cd253437cf19" />
<img width="1667" height="961" alt="mapped-drive-visible" src="https://github.com/user-attachments/assets/770f357e-2b4f-446c-a44d-61e6cba015ab" />
*Caption: Final verification of the mapped Z: drive.*

