# Lab 07: Enforcing Password Complexity & Length Restrictions

## 📝 Overview
In this lab, I hardened the security of the `lab.local` domain by implementing a **Password Policy GPO**. This ensures that all domain users follow modern security standards by requiring a minimum character length and the use of complex characters (uppercase, numbers, and symbols) to prevent simple credential-guessing attacks.

## 🛠️ Technologies Used
* **Windows Server 2022** (Domain Controller)
* **Active Directory Domain Services (AD DS)**
* **Group Policy Management Console (GPMC)**
* **Windows 11 Pro** (Target Workstation)

## 🎯 Key Achievements
* **Security Baselines:** Configured a minimum password length of **10 characters** and enabled mandatory complexity.
* **Validation Testing:** Verified policy enforcement by attempting to set a "Weak" password and capturing the system's rejection.
* **End-to-End Success:** Confirmed that a compliant, high-entropy password allows successful authentication on a domain-joined client.

## 📸 Evidence
*Refer to the `/screenshots` folder for the following proof:*
1. **GPO Configuration:** `Lab7_GPO_Config.png`
2. **Policy Enforcement (Rejection):** `Lab7_Complexity_Error.png`
3. **Client-Side Success:** `Lab7_Client_Success.png`
