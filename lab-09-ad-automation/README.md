# Lab 09: Active Directory Bulk Automation (PowerShell)

## 📝 Overview
Manually creating users is inefficient and prone to human error. In this lab, I transitioned from GUI-based management to **Infrastructure as Code (IaC)** principles by using PowerShell to automate the onboarding of multiple users from a CSV data source.

## 🛠️ Tools & Technologies
* **PowerShell ISE / Core:** Used for scripting and execution.
* **Active Directory Module:** Utilized `New-ADUser` and `Set-ADUser` cmdlets.
* **Microsoft Excel / Notepad:** Used to manage the `users.csv` source file.

## 🎯 Key Achievements
* **Bulk Processing:** Successfully created multiple user accounts (`agreen`, `bwhite`, `cblack`) in a single execution.
* **Security Compliance:** Scripted a mandatory "Password Change at Next Logon" policy for all new accounts.
* **Troubleshooting RDP/NLA:** Diagnosed and resolved the NLA (Network Level Authentication) conflict that occurs when remote users are forced to change passwords.

## 📸 Evidence
1. **Automation Success:** <img width="1737" height="991" alt="Lab9_AD_Automation" src="https://github.com/user-attachments/assets/24cd2841-11fc-4e52-a9fe-a18ac4d31ab8" />
2. **User Validation:** <img width="1740" height="997" alt="users_created" src="https://github.com/user-attachments/assets/7ffd4b81-6281-485b-ab37-fa84d5acf93e" />
