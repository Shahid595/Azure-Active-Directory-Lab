# Lab 08: DNS Name Resolution & Troubleshooting

## 📝 Overview
DNS (Domain Name System) is the "heartbeat" of Active Directory. Without correct name resolution, workstations cannot locate the Domain Controller, leading to login failures and resource access issues. In this lab, I simulated a DNS outage, diagnosed the failure using industry-standard tools, and restored connectivity.

## 🛠️ Tools & Commands Used
* **nslookup:** Used to query DNS servers and verify domain name resolution.
* **ipconfig /flushdns:** Cleared the local DNS resolver cache to remove stale/incorrect records.
* **ipconfig /registerdns:** Forced the client to refresh its settings and re-register with the Domain Controller.
* **ncpa.cpl:** Shortcut to manage Network Adapter properties.

## 🎯 Key Achievements
* **Incident Simulation:** Manually misconfigured DNS to mimic a common "lost connection" scenario.
* **Troubleshooting:** Identified that the workstation was querying an external DNS (`8.8.8.8`) instead of the internal Lab DC.
* **Resolution:** Re-aligned the DNS hierarchy and verified that `lab.local` resolved to the correct internal IP.

## 📸 Evidence
1. **The Failure:** <img width="1756" height="983" alt="Lab8_DNS_Failure png" src="https://github.com/user-attachments/assets/24cea623-bb77-4275-a329-b8d065fbeae6" />

2. **The Success:** <img width="1813" height="983" alt="Lab8_DNS_Success" src="https://github.com/user-attachments/assets/236070f0-4282-4b55-a7e6-8a945b83caf0" />
