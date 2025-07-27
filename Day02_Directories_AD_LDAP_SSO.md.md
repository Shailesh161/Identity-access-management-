
#  Day 2 – Directory Services, Active Directory, LDAP & Desktop SSO

**Author:** Shailesh Gatkul  
**Date:** 27 July 2025

---

##  Where Are Identities Stored?

Identities (like users, devices, or systems) are stored in secure data sources known as **identity repositories**. Common places where identities are stored:

| Source              | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| ✅ Database (DB)     | Custom-built systems store user info in SQL/NoSQL databases.                |
| ✅ Directory Service | Structured systems that store and manage identities (like Active Directory).|
| ✅ Active Directory  | A Microsoft-based directory used by most enterprises.                       |
| ✅ Cloud Directory   | e.g., AWS IAM, Azure AD, Google Cloud Identity.                             |
| ✅ LDAP Directory    | Lightweight directory with hierarchical structure.                          |
| ✅ Servers           | Legacy systems or applications may store local user info.                   |
| ✅ HR Systems        | e.g., Workday, SAP SuccessFactors — source of truth for employee info.      |

---

##  What Is a Directory?

A **directory** is like a **digital telephone directory**.

- It stores structured info like names, email IDs, departments, phone numbers, etc.
- It helps **organize and manage user identities** across systems.

>  Real-life Example:  
> A **telephone directory** stores names & numbers alphabetically.  
> A **digital directory** stores usernames, roles, passwords, departments, etc.

---

##  What Is Active Directory (AD)?

**Active Directory (AD)** is a **directory service by Microsoft** used by organizations to **store and manage identities**, such as:

- Employees
- Computers
- Groups
- Printers
- Devices

### Why Do Companies Use AD?

- Central place to **store users and devices**
- Helps with **authentication** (login) and **authorization** (permissions)
- Easy to **add, update, delete, and search** users
- Used by tools like IAM solutions, HR systems, etc.

> **AD = Source of Truth**
> Everything in IAM depends on the data in AD — from login to access control.

---

###  AD in Action

| AD Connected To       | Purpose                                       |
|------------------------|-----------------------------------------------|
| IAM Tools (e.g., SailPoint) | Sync users and roles                       |
| HR Systems             | Sync employee status (join/leave/update)      |
| Applications           | Login using AD credentials (SSO)              |

---

##  Components of Active Directory

| Component             | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Domain Services**    | Logical structure (e.g., `mycompany.com`) that defines network identity.     |
| **LDAP**               | A communication **protocol** to query and modify directory data.             |
| **Domain Controllers** | Servers that store AD and respond to auth requests.                         |

---

##  AD Structure: Organizational Units (OUs)

AD uses a **tree-like structure** to group and organize users.

###  Organizational Units (OUs)

- Like folders inside folders.
- Group users by departments or teams.
- Helps assign group policies or permissions.

> **Example**:
> ```
> Company
> ├── HR
> │   ├── Recruiters
> ├── Development
> │   ├── Frontend Devs
> │   ├── Backend Devs
> │   ├── DevOps
> ├── Security
> └── Finance
> ```

---

##  What Is LDAP?

**LDAP (Lightweight Directory Access Protocol)** is a **protocol** (like HTTP or FTP) used to communicate with directory services like Active Directory.

###  What LDAP Does

- Acts as a **messenger between applications and directories**
- Helps **search, retrieve, add, delete, or update** directory entries

> **Analogy**:
> AD = water tank  
> App = bucket  
> LDAP = the tap used to fetch water (data)

### LDAP Port Numbers

| Port | Purpose         |
|------|-----------------|
| 389  | Standard LDAP   |
| 636  | Secure LDAP (LDAPS) |

---

##  What Is Desktop SSO (DSSO) – Kerberos?

**Desktop SSO (Single Sign-On)** allows users to **log into their computer once** and automatically gain access to all apps and systems — without re-entering credentials.

It uses **Kerberos** — a secure authentication protocol.

###  How Kerberos Works (Simplified)

1. User logs into laptop (AD login).
2. Kerberos gives a **ticket** (like a movie ticket).
3. User uses the ticket to access apps like Outlook, HR portal, Jira, etc.

###  Real-Life Analogy

> Think of a **Kerberos ticket like an entry stamp** in a theme park.  
> You show the stamp (ticket) at each ride (app) to prove you’re authorized — no need to show ID again and again.

### Benefits of DSSO

- Saves time for users
- Improves user experience
- Strengthens security (no password reuse)

---

##  Summary

| Concept           | Description                                             | Example                                  |
|-------------------|---------------------------------------------------------|------------------------------------------|
| Identity Storage  | Where identities are kept                               | DB, AD, LDAP, HR System                  |
| Directory         | Structured identity store                               | Like a digital telephone book            |
| Active Directory  | Microsoft's directory system for managing identities    | Stores user, group, device info          |
| OU                | Sub-group/folder inside AD                              | HR OU, Dev OU, Finance OU                |
| LDAP              | Protocol to communicate with directory services         | Acts like a messenger                    |
| DSSO              | Login once → access many apps automatically             | Used in office computers using Kerberos  |
| Kerberos          | Protocol for secure, ticket-based authentication        | Issues “access ticket” on login          |

---

## 💬 Final Note

💬 I’m always open to feedback, suggestions, collaboration, or professional opportunities in the Identity and Access Management (IAM) space.  
Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/shailesh-gatkul/) or reach out via email at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).

---

📌 **Disclaimer:**  
This repository is intended for **personal learning and educational purposes only**. The content has been compiled using knowledge gathered from publicly available sources such as technical blogs, documentation, YouTube tutorials, LinkedIn posts, community forums, and AI tools.  
If you believe any part of this content requires credit, correction, or removal, please contact me at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).

