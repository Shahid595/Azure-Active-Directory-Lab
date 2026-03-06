# Lab 3 – Domain Join Client Workstation (Steps)

## Step 1 – Deploy Client Virtual Machine

1. Navigate to the Azure Portal.
2. Click **Create a resource → Virtual Machine**.
3. Configure the VM with the following settings:

Name: client-1
Image: Windows 11 Pro
Region: East US
Resource Group: labtest1
Virtual Network: vnet-eastus
Subnet: snet-eastus-1

4. Create an administrator username and password.
5. Click **Review + Create → Create**.

---

## Step 2 – Connect to the Client VM

1. Navigate to the **client-1 VM** in Azure.
2. Click **Connect → RDP**.
3. Download the RDP file.
4. Open the file and connect using the local administrator credentials.

---

## Step 3 – Configure DNS

The client must use the Domain Controller as its DNS server.

1. Open **Network Settings**.
2. Open **Network Adapter Properties**.
3. Select **Internet Protocol Version 4 (IPv4)**.
4. Configure the DNS server:

Preferred DNS Server → DC private IP address.

Example:


_172.16.0.4_


5. Click **OK** and apply the changes.

---

## Step 4 – Join the Domain

1. Open **Settings → System → About**.
2. Click **Advanced system settings**.
3. Under **Computer Name**, click **Change**.
4. Select **Domain**.

Enter:


_lab.local_


5. Enter Domain Administrator credentials when prompted.

Example:


_LAB\labadmin_


6. Restart the computer when prompted.

---

## Step 5 – Verify Domain Join

After the system restarts:


1. On the Domain Controller, open:


Active Directory Users and Computers


2. Verify that **client-1** appears under the domain.

3. Move the computer object to the:

_COMPUTERS OU

---

## Step 6 – Confirm Domain Authentication

Login to **client-1** using a domain user.

Successful login confirms:

• DNS configuration works
• Domain join succeeded
• Authentication through Active Directory is functional
