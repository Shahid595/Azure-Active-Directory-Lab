# Lab 06: Implementing Enterprise Group Policy & Security Restrictions

## 📝 Overview
In this lab, I acted as a System Administrator for the `lab.local` domain to implement security hardening. I configured **Group Policy Objects (GPOs)** to enforce a "3-strike" Account Lockout Policy and restricted access to sensitive OS components like the Control Panel to prevent unauthorized system changes.

## 🛠️ Technologies Used
* **Windows Server 2022** (Domain Controller)
* **Active Directory Domain Services (AD DS)**
* **Group Policy Management Console (GPMC)**
* **Windows 11 Pro** (Target Workstation)

## 🎯 Key Achievements
* **Brute Force Mitigation:** Set an automated lockout threshold to protect against credential harvesting.
* **Least Privilege Enforcement:** Restricted standard user access to System Settings and the Control Panel.
* **GPO Propagation:** Successfully used `gpupdate /force` to ensure real-time policy updates on remote clients.
* **Administrative Lifecycle:** Demonstrated the Help Desk process of identifying and unlocking accounts via ADUC.

## 📸 Evidence
*Refer to the `/screenshots` folder for the following proof:*
1. **GPO Configuration:** `Lab6_GPO_Settings.png`
2. **Client-Side Lockout:** `Lab6_Lockout_Proof.png`
3. **Admin Unlock Interface:** `Lab6_Admin_Unlock.png`
