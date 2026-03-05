# Lab 1 — Azure Virtual Machine Deployment

## Objective

Deploy two virtual machines in Microsoft Azure to simulate a small enterprise network.

This environment will include:

- A Domain Controller
- A Client Machine

These machines will later be used to configure Active Directory.

---

## Environment

Resource Group: Labtest1

Virtual Network: vnet-eastus

Subnet: snet-eastus-1

Machines:

Domain Controller  
Name: lab-vm  
Operating System: Windows Server 2022

Client Machine  
Name: IT-CLIENT-02  
Operating System: Windows 11

---

## Steps:

### Step 1 — Create Resource Group

Create a resource group in Azure.

Name: Labtest1  
Region: East US

---

### Step 2 — Create Virtual Network

Create a virtual network.

Name: vnet-eastus  
Address space: 172.16.0.0/16

Subnet: snet-eastus-1  
Subnet range: 172.16.0.0/24

---

### Step 3 — Deploy Domain Controller VM

Create a virtual machine.

Name: lab-vm  
Operating System: Windows Server 2022

---

### Step 4 — Deploy Client Machine

Create a second virtual machine.

Name: IT-CLIENT-02  
Operating System: Windows 11

Ensure both machines are placed in the same virtual network.

---

## Verification

Run the following command from the client machine: ping 172.16.04


A successful reply confirms network connectivity.

---

