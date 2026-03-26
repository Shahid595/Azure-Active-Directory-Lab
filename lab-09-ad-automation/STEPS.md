# Technical Documentation: Lab 09 Step-by-Step

### Phase 1: Preparing the Data Source
1. Created a CSV file at `C:\users.csv` on **DC-1**.
2. Structured the data with headers: `FirstName, LastName, Username, Department`.
3. Populated the file with test users for the Finance and IT departments.

### Phase 2: Executing the PowerShell Script
1. Opened PowerShell as Administrator.
2. Ran a loop to import the CSV and create users with a secure temporary password:
   ```powershell
   $SecurePassword = ConvertTo-SecureString "P@ssw0rd123!" -AsPlainText -Force
   Import-Csv "C:\users.csv" | ForEach-Object {
       New-ADUser -Name "$($_.FirstName) $($_.LastName)" `
                  -SamAccountName $_.Username `
                  -Path "CN=Users,DC=lab,DC=local" `
                  -AccountPassword $SecurePassword -Enabled $true
   }
### Phase 3: Solving the RDP Password Block
1. Encountered a "Must change password" prompt that blocked RDP access due to NLA.

2. Resolved the issue by running a targeted attribute update:
PowerShell
Set-ADUser -Identity agreen -ChangePasswordAtLogon $false
3. Successfully logged into Client-1 as agreen to verify account integrity and profile creation.


  

