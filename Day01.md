#  Day 1 – Introduction to IAM

---

## What is IAM?

**Identity and Access Management (IAM)** is a **security discipline** that enables the **right individuals or systems** to **access the right resources**, at the **right time**, and for the **right reasons**.

IAM helps organizations manage:

* **Who** can access systems (identity)
* **What** they can do (access/permissions)
* **How** and **when** they can do it (controls, rules, policies)

It includes processes like:

* User authentication & authorization
* Role-based access control (RBAC)
* Provisioning & deprovisioning
* Privileged access management

---

##  What is an Identity?

An **identity** is any entity (human or non-human) whose access to digital resources needs to be managed.

### 🔹 Human Identity:

Represents real users such as:

* Employees
* Contractors
* Customers
* Partners

> **Example**: "John Doe" (an employee) logs into the internal HR portal.

### 🔹 Machine Identity:

Represents systems or applications that interact with other systems:

* Service accounts
* APIs
* Containers
* Bots

> **Example**: A CI/CD pipeline job accessing cloud resources using a service principal.

IAM systems treat both human and machine identities equally in terms of assigning roles, policies, and permissions.

---

##  What is Access?

**Access** refers to the level of **permissions granted to an identity** to perform specific operations on resources.

It includes:

* **Read** / **Write** / **Execute** access on files
* API access scopes
* Admin vs. user-level privileges

> **Example**:
>
> * An HR manager has read/write access to employee records.
> * A regular employee only has read access to their own record.

Access is governed by **policies**, **roles**, and **group memberships** defined in the IAM system.

---

##  Why Do Organizations Need IAM?

IAM is essential for both **security** and **compliance**, especially in today’s cloud-first, remote, and highly regulated environments.

### 1. **Security**

* Prevents unauthorized access to sensitive data and systems
* Mitigates insider threats and external breaches
* Enforces least privilege access

### 2. **Compliance**

Helps meet legal and industry regulations like:

* **GDPR** (General Data Protection Regulation)
* **HIPAA** (Health Insurance Portability and Accountability Act)
* **PCI-DSS** (Payment Card Industry Data Security Standard)
* **SOX** (Sarbanes-Oxley Act)

Non-compliance can lead to:

* Fines
* Lawsuits
* Loss of customer trust

### 3. **Audit & Reporting**

IAM tools track:

* Login events
* Access changes
* Permission usage

This makes it easier to generate reports for audits or forensic investigations.

### 4. **Operational Efficiency**

IAM automates:

* **User provisioning** (onboarding)
* **Access updates** (role changes)
* **Deprovisioning** (termination)

> Example: When a new employee joins via the HR system, IAM automatically assigns them appropriate access (JML flow).

### 5. **Scalability**

IAM systems allow organizations to scale securely from 10 users to 10,000+ users across departments and geographies.

---

##  What is Authentication?

**Authentication** is the process of **verifying the identity** of a user or system.

Common authentication methods include:

* Username & password
* OTP (One-Time Password)
* Biometrics (fingerprint, face scan)
* OAuth/OpenID tokens

> **Example**: Entering a password or scanning your fingerprint to access your laptop.

---

##  What is Authorization?

**Authorization** is the process of **determining what actions** a verified user or system is **allowed to perform**.

> **Example**:
> After successful login (authentication), IAM checks if the user has permission to:
>
> * View reports
> * Manage users
> * Access admin settings

**Authentication answers:** *"Who are you?"*
**Authorization answers:** *"What can you do?"*

---

## Security Principles IAM Follows – The CIA Triad

The **CIA Triad** is a fundamental model in cybersecurity. IAM plays a key role in enforcing all three:

---

###  Confidentiality

Ensures that sensitive information is only accessible to authorized users.

> Example: Only the finance team should have access to company budget files.

IAM enforces this via:

* Role-based access
* Policies
* Encryption

---

###  Integrity

Ensures that data is **accurate and cannot be modified** by unauthorized parties.

> Example: Audit logs should not be tampered with by regular users.

IAM supports this by:

* Allowing write permissions only to trusted roles
* Tracking changes (via logs)

---

###  Availability

Ensures systems and data are **available when needed**.

> Example: If the IAM system is down, employees may be locked out of business apps.

IAM supports high availability via:

* Load-balanced services
* Failover mechanisms
* Redundancy

---

## ❗Which Is Most Important in CIA?

In IAM, **Confidentiality** is often considered the most critical.

> Reason:
> If unauthorized users get access to sensitive data (like customer PII or passwords), it can lead to:
>
> * Legal consequences
> * Data breaches
> * Loss of reputation

---

##  Summary

| Concept        | Meaning                                  | Example                                 |
| -------------- | ---------------------------------------- | --------------------------------------- |
| IAM            | Identity and Access Management           | Grants users access to internal systems |
| Identity       | Human or machine using the system        | Employee, API                           |
| Access         | What actions are allowed                 | Read/write data                         |
| Authentication | Proving identity                         | Login using password                    |
| Authorization  | What can be done                         | Access reports                          |
| CIA Triad      | Confidentiality, Integrity, Availability | IAM enforces all 3                      |


