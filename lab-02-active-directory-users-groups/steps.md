# Lab 2 – Active Directory Users and Groups (Steps)

## Step 1 – Open Active Directory Users and Computers

1. RDP into **dc-1**.
2. Open **Server Manager**.
3. Click **Tools → Active Directory Users and Computers**.

---

## Step 2 – Create Organizational Units

Inside the domain **lab.local**, create the following Organizational Units.

Right click the domain → **New → Organizational Unit**

Create:

_USERS
_GROUPS
_COMPUTERS
_SERVERS

Then create departmental OUs:

HR
IT
Finance

---

## Step 3 – Create Security Groups

Navigate to the **_GROUPS** OU.

Right click → **New → Group**

Create the following groups:

HR_Users
IT_Admins
Finance_Users

Configuration:

Group scope: Global
Group type: Security

---

## Step 4 – Create Users

Navigate to the **_USERS** OU.

Right click → **New → User**

Create the following users.

User 1

Name: John Smith
Username: jsmith

User 2

Name: Sarah Johnson
Username: sjohnson

User 3

Name: Mike Brown
Username: mbrown

Set a temporary password and enable **User must change password at next logon**.

---

## Step 5 – Assign Users to Groups

Navigate to **_GROUPS**.

Open each group and add users.

IT_Admins
→ Add: jsmith

HR_Users
→ Add: sjohnson

Finance_Users
→ Add: mbrown

---

## Step 6 – Verify Group Membership

Open each group and confirm the correct users appear in the **Members** tab.

This confirms group-based access control is working correctly.
