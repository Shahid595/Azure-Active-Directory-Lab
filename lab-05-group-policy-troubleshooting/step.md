# Lab 5: Detailed Implementation Steps

---

### 1. Group Policy Creation (Domain Controller)
* **Log In:** Accessed **dc-1** as `lab.local\admin`.
* **GPO Management:** Opened Group Policy Management (`gpmc.msc`).
* **New Policy:** Created a GPO named **"Map Shared Drive"**.
* **Configuration:** * Path: `User Configuration > Preferences > Windows Settings > Drive Maps`.
    * **Action:** Replace (Ensures the drive maps reliably on every login).
    * **Location:** `\\dc-1\Shares`
    * **Drive Letter:** Z:
    * **Security:** Enabled "Run in logged-on user's security context" under the Common tab.
* **Linking:** Linked the GPO to the **CLIENTS** Organizational Unit (OU).

### 2. Enabling Loopback Processing
* **Purpose:** Since Drive Mapping is a *User* configuration but needs to apply to specific *Computers* in the CLIENTS OU, I enabled Loopback Processing.
* **Path:** `Computer Configuration > Policies > Admin Templates > System > Group Policy`.
* **Setting:** Set **Configure user Group Policy loopback processing mode** to **Merge**.

---

### 3. Troubleshooting Phase 1: RDP Permissions
* **Issue:** Domain user `john.it` encountered "Credentials did not work" when attempting to RDP into `client-1`.
* **Diagnosis:** Standard domain users do not have rights to log into Windows workstations via RDP by default.
* **Resolution:** 1. Logged into **client-1** as local administrator.
    2. Opened **Computer Management** > **Local Users and Groups**.
    3. Added `LAB\john.it` to the local **Remote Desktop Users** group.

### 4. Troubleshooting Phase 2: The "Ghost" Share
* **Issue:** After successful login, the Z: drive was missing and the path `\\dc-1\Shares` was unreachable.
* **Initial Check:** Verified Windows Firewall on **dc-1**. **SMB-In (Port 445)** was already enabled; therefore, the firewall was not the blocker.
* **Root Cause:** Discovered that following the environment rebuild, the physical directory `C:\Shares` did not exist on the new **dc-1** virtual machine.
* **Resolution:** 1. Created the `C:\Shares` folder on **dc-1**.
    2. Shared the folder as **"Shares"**.
    3. Configured Share Permissions for **Everyone: Change/Read**.
    4. Re-created organizational subfolders (`HR`, `IT`, `Finance`).

---

### 5. Verification & Success
* **Action:** Performed a `gpupdate /force` on **client-1**.
* **Result:** Ran `gpresult /r` to verify the "Map Shared Drive" policy was successfully filtered and applied.
* **Final Proof:** Confirmed the **Z: Drive** appeared in File Explorer, providing full access to the shared network resources.
