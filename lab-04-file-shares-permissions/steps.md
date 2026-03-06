# Lab 4 — File Shares and NTFS Permissions

## Objective
Configure shared folders on the domain controller and restrict access using NTFS permissions based on department groups.

---

## Environment

| Component | Value |
|----------|------|
| Domain Controller | dc-1 |
| Client Machine | client-1 |
| Domain | lab.local |
| Share Location | C:\Shares |

---

## Step 1 — Create Folder Structure

On **dc-1**, create the following folders:

```
C:\Shares
C:\Shares\HR
C:\Shares\Finance
C:\Shares\IT
```

Screenshot:

```
lab4-01-folder-structure.png
```

---

## Step 2 — Enable Folder Sharing

Right-click:

```
C:\Shares → Properties → Sharing
```

Select:

```
Advanced Sharing
```

Enable:

```
Share this folder
```

Share name:

```
Shares
```

Screenshot:

```
lab4-02-share-settings.png
```

---

## Step 3 — Configure Root Permissions

Navigate to:

```
C:\Shares → Properties → Security
```

Configure permissions:

| Group | Permission |
|------|------|
| SYSTEM | Full Control |
| Administrators | Full Control |
| Authenticated Users | Read |

Screenshot:

```
lab4-03-root-permissions.png
```

---

## Step 4 — Configure HR Folder Permissions

Navigate to:

```
C:\Shares\HR → Properties → Security
```

Permissions:

| Group | Permission |
|------|------|
| HR_Users | Modify |
| SYSTEM | Full Control |
| Administrators | Full Control |

Screenshot:

```
lab4-04-hr-permissions.png
```

---

## Step 5 — Configure Finance Folder Permissions

Navigate to:

```
C:\Shares\Finance → Properties → Security
```

Permissions:

| Group | Permission |
|------|------|
| Finance_Users | Modify |
| SYSTEM | Full Control |
| Administrators | Full Control |

Screenshot:

```
lab4-05-finance-permissions.png
```

---

## Step 6 — Configure IT Folder Permissions

Navigate to:

```
C:\Shares\IT → Properties → Security
```

Permissions:

| Group | Permission |
|------|------|
| IT_Admins | Modify |
| SYSTEM | Full Control |
| Administrators | Full Control |

Screenshot:

```
lab4-06-it-permissions.png
```

---

## Step 7 — Verify Share Access

On **client-1**, open:

```
\\dc-1\Shares
```

Screenshot:

```
lab4-07-share-access.png
```

---

## Step 8 — Test Access Restrictions

Attempt to open folders outside the user's department.

Expected result:

```
Access Denied
```

Screenshot:

```
lab4-08-access-denied.png
```

---

## Result

Users can only access folders assigned to their department, demonstrating role-based access control using NTFS permissions.
