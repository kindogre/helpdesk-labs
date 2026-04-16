# 🏢 Active Directory Home Lab (Windows Server + GPO)

## 📌 Overview
This project simulates a real-world enterprise Active Directory environment.

I built a domain, joined client machines, created users/groups, and enforced security policies using Group Policy Objects (GPO).

---

## 🧰 Technologies Used
- Windows Server (Domain Controller)
- Active Directory Domain Services (AD DS)
- DNS
- Windows 11 Client VM
- Group Policy Management (GPO)
- Hyper-V

---

## 🏗️ Lab Architecture
- 1 Domain Controller (DC01)
- 1 Windows 11 Client
- Domain: `corp.local`
- Organizational Unit: `Employees`
  ![Architecture Diagram](assets/diagram.png)



---

## 👥 Users & Groups
Created test users and applied role-based access control:

- Users:
  - John Doe (Restricted)
  - Kim Smith (Normal)
  ![User1](screenshots/33-Adding-new-employee.jpg)
  ![User2](screenshots/34-Adding-another-employee.jpg)

- Security Group:
  - `Restricted-Users`
  ![Restricted-Users](screenshots/35-Created-Restricted-Users_Group.jpg)

- 🧩 Password Policy
![password max age](screenshots/57-set-password-max-age.jpg)
![password min length](screenshots/58-set-password-minimum-length.jpg)


---

## ⚙️ Group Policy (GPO)
Created and applied GPO:
![Created-new-GPO](screenshots/45-adding-new-GPO.jpg)


### 🎯 Policy Goal:
Restrict specific users without affecting others

### 🔒 Example Restriction:
- Disabled Control Panel access
- Restricted system features
- Disabled Command prompt for Restricted users

---

## 🧪 Testing & Validation

### ✅ Test 1 — Restricted User (John Doe)
- Policy applied successfully
- Restrictions enforced
 ![Restricted User](screenshots/36-Added-employee-to-RestrUsers-Group.jpg)
 ![Logged as restricted user](screenshots/51-logged-as-JohnDoe.jpg)
 ![Restricted control panel access](screenshots/52-try-to-open-Control-Panel-as-JohnDoe.jpg)
 ![Verified via PowerShell](screenshots/53-verification.jpg)



---

### ✅ Test 2 — Normal User (Kim Smith)
- No restrictions applied
- System works normally
  ![Logged as non-restricted user](screenshots/54-logged-as-KimSmith.jpg)
  ![Accessed Control Panel](screenshots/55-accessed-Control-Panel-as-KimSmith.jpg)



---

###✅ Test 3- Restricted User (John Doe)



---

## 🧠 Key Skills Demonstrated
- Active Directory setup & management
- Domain join & authentication
- Group Policy creation & targeting
- Security group-based access control
- Troubleshooting login and policy issues

---

## 🛠️ Troubleshooting

### Issue: Unable to log in
- Cause: Used local account instead of domain account
- Fix: Used `CORP\username`

### Issue: GPO not applying
- Fix:
  - `gpupdate /force`
  - Verified Security Filtering


---

## 🚀 Conclusion
This lab demonstrates how to manage users, enforce security policies, and troubleshoot real-world Active Directory environments.

---
