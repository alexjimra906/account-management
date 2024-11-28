# Managing User Accounts and Observing Logs in Active Directory

## Overview
This project demonstrates critical aspects of managing user accounts within an Active Directory environment. The tasks include dealing with account lockouts, configuring account lockout policies, enabling/disabling accounts, and observing system logs.

---
## Environments and Technologies Used
- **Microsoft Azure**: Virtual Machines, Virtual Networks, Resource Groups, and Subnets.
- **Remote Desktop Protocol (RDP)**: Managing virtual machines from a remote interface.
- **Active Directory Domain Services (AD DS)**: User and group management, security policies.
- **Group Policy Management**: Account lockout thresholds and other security settings.
- **DNS Management**: Dynamic and static DNS record creation and resolution.

## Operating Systems Used
- **Windows Server 2022**: Domain Controller and DNS Server.
- **Windows 10**: Client machine for testing and validation.

## List of Prerequisites
1. Active Microsoft Azure subscription.
2. Basic understanding of networking concepts (IP, DNS, Subnets).
3. Familiarity with Windows operating systems.
4. Remote Desktop client installed on a local machine.
5. Script editor (e.g., PowerShell ISE) for user account automation.

---

## Key Activities

### 1. Dealing with Account Lockouts
- **Step 1:** Logged into the `DC-1` VM.
- **Step 2:** Selected a random user account previously created.
- **Step 3:** Attempted to log in 10 times with an incorrect password to simulate account lockout.

### 2. Configuring Account Lockout Policy
- Configured the **Account Lockout Threshold** to lock accounts after 5 failed attempts using Group Policy.
  ![image](https://github.com/user-attachments/assets/d825520f-c5ea-47ba-ae94-2ef18d000b41)
  ![image](https://github.com/user-attachments/assets/d6d661fa-a3de-4cb1-b466-6fb930ca48cc)



### 3. Testing Account Lockout
- Attempted to log in 6 times with a bad password and observed the account being locked out in Active Directory.
  ![image](https://github.com/user-attachments/assets/396bf6d7-d0c5-47b2-8c3f-52445ece98bf)

- Unlocked the account and reset its password.
  ![image](https://github.com/user-attachments/assets/643441df-1e31-4ddc-af56-9b5a0c6c417c)
  ![image](https://github.com/user-attachments/assets/e4f0f36e-d5c6-43bb-8425-c3ce9662e893)

- Successfully logged in after the password reset.
  ![image](https://github.com/user-attachments/assets/e9d2a7d7-e3b0-40d7-b21c-0ec403fce303)


### 4. Enabling and Disabling Accounts
- Disabled the user account in Active Directory.
  ![image](https://github.com/user-attachments/assets/7380b7b7-94fb-484c-8b68-d728dbf757f9)

- Attempted to log in and observed the error message indicating the account was disabled.
  ![image](https://github.com/user-attachments/assets/71f46a51-308d-40e5-aab0-a55465ba495d)

- Re-enabled the account and confirmed successful login.
  ![image](https://github.com/user-attachments/assets/cb9f91ac-06ca-4333-8408-aa6347e53c1b)


### 5. Observing Logs
- Reviewed logs on the **Domain Controller (DC-1)** to observe account-related activities.
- Examined logs on the client machine to understand client-side effects.
  ![image](https://github.com/user-attachments/assets/e5f0de72-72f1-44c0-bec8-234f2cd77357)


---

## Technical Insights
- **Account Lockout Policies:** Ensures security by limiting brute force login attempts.
- **Group Policy Configuration:** Centralized management of account policies across the domain.
- **Log Observation:** Critical for tracking and diagnosing security incidents.


---

## Reflection
This lab highlighted the importance of robust account management practices in a domain environment. By configuring lockout policies and monitoring logs, potential unauthorized access attempts can be mitigated effectively.

---

## Final Note
The `DC-1` and `Client-1` VMs will be used in subsequent labs. To save costs, these VMs were stopped in the Azure Portal after completing the lab.
