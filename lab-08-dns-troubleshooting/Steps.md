# Technical Documentation: Lab 08 Step-by-Step

## DNS Name Resolution & Troubleshooting

---

## Phase 1: Simulating the DNS Outage (Client-1)

1. Logged into **Client-1** and opened the **Run** dialog (**Win + R**).
2. Typed `ncpa.cpl` to open **Network Connections**.
3. Right-clicked the Ethernet adapter and selected **Properties**.
4. Modified **Internet Protocol Version 4 (TCP/IPv4)** to use an external DNS address: `8.8.8.8`.
5. Opened **Command Prompt** and executed the following diagnostic command:

```cmd
nslookup lab.local
```

**Result:**
The request returned a *"Non-existent domain"* error because the external DNS server does not have records for the private `lab.local` zone.

📸 **Evidence:**
Captured the failure in `Lab8_DNS_Failure.png`.

---

## Phase 2: Diagnostic & Resolution

1. Re-opened the IPv4 Properties for the network adapter.
2. Reverted the **Preferred DNS Server** to the static internal IP of **DC-1**.
3. Cleared the local DNS resolver cache to remove the incorrect cached records:

```cmd
ipconfig /flushdns
```

4. Forced the workstation to re-register its host records with the Domain Controller:

```cmd
ipconfig /registerdns
```

---

## Phase 3: Final Verification

1. Re-ran the name resolution test in **Command Prompt**:

```cmd
nslookup lab.local
```

**Result:**
The system successfully identified **DC-1** as the resolver and returned its correct internal IP address.

📸 **Evidence:**
Captured the successful resolution in <img width="1813" height="983" alt="Lab8_DNS_Success" src="https://github.com/user-attachments/assets/5329b5ab-8c36-4c64-8e61-b3a0f567a115" />

