# Technical Documentation: Lab 07 Step-by-Step

### Phase 1: Security Policy Configuration (DC-1)
1. Open **Group Policy Management** on **DC-1**.
2. Edit the **Default Domain Policy**.
3. Navigate to: `Computer Configuration` > `Policies` > `Windows Settings` > `Security Settings` > `Account Policies` > **Password Policy**.
4. **Configure Settings:**
   * Set **Minimum password length** to `10`.
   * Set **Password must meet complexity requirements** to `Enabled`.
5. **📸 Evidence:** <img width="1892" height="945" alt="Lab7_GPO_Config" src="https://github.com/user-attachments/assets/f4688ed4-4d67-4b33-8c78-8502657e00a1" />


### Phase 2: Testing Policy Enforcement (DC-1)
1. Open **Active Directory Users and Computers** (ADUC).
2. Right-click the test user `ltest` and select **Reset Password**.
3. Attempt to set the password to a non-compliant string: `123`.
4. **Result:** Windows displays an error stating: *"The password does not meet the password policy requirements."*
5. **📸 Evidence:**
<img width="1907" height="1007" alt="Lab7_Complexity_Error" src="https://github.com/user-attachments/assets/a7b3fe3c-3ca9-42ce-8567-3746937abde7" />


### Phase 3: Verification (Client-1)
1. On **DC-1**, set a compliant password for `ltest` (e.g., `AzureLab!2026`).
2. Log into **Client-1** using the new compliant password.
3. **Result:** Access is granted, confirming the policy allows compliant passwords while blocking weak ones.
4. **📸 Evidence:**
   <img width="1907" height="952" alt="Lab7_Client_Success" src="https://github.com/user-attachments/assets/c63419d1-4120-403e-8bf3-6b1a9532235b" />
