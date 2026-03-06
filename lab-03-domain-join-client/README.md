# Lab 3 – Domain Join Client Machine

## Objective

Deploy a Windows workstation and join it to the Active Directory domain.

---

## Environment

Domain Controller: dc-1
Client Machine: client-1
Domain: lab.local

---

## Client Deployment

A Windows 11 Pro virtual machine was deployed in Azure.

VM Name: client-1
Operating System: Windows 11 Pro

---

## DNS Configuration

The client machine DNS server was configured to use the Domain Controller private IP address.

This allows the workstation to discover and authenticate with Active Directory.

---

## Domain Join

The workstation was joined to the domain:

lab.local

Administrative credentials were used to authorize the domain join.

The system was restarted to complete the process.

---

## Verification

The computer object appeared in Active Directory under the **_COMPUTERS** Organizational Unit.

A domain user was able to authenticate successfully.

---

## Skills Demonstrated

Active Directory workstation deployment
Domain join process
DNS configuration for AD
Computer object management in Active Directory
