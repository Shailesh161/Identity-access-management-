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

> **Example**: "Shailesh" (an employee) logs into the internal HR portal.

### 🔹 Machine Identity:

Just like humans (employees or users) have usernames and passwords to access systems, machines also need a digital identity to securely communicate with other machines, apps, or services.These are called machine identities.

* Service accounts
* APIs
* Containers
* Bots
* Servers

> **Example**: 
* Use Case -A microservice calls another microservice
* Machine Identity Used-OAuth token or mTLS certificate

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


Companies that deal with sensitive data — like health records, credit cards, or personal info — must follow certain **rules and laws** to keep that data safe. These are called **compliance regulations**, and IAM plays a big part in helping companies follow them.

* **GDPR** (General Data Protection Regulation)
* **HIPAA** (Health Insurance Portability and Accountability Act)
* **PCI-DSS** (Payment Card Industry Data Security Standard)
* **SOX** (Sarbanes-Oxley Act)


#### **HIPAA** (USA – Healthcare)

* Rule made for hospitals, clinics, or health-tech companies.
* It protects **patients' private health data**.

**IAM helps by**:

* Making sure only doctors or medical staff can see patient reports.
* Logging who accessed what and when.

> **Example**: A hospital uses IAM to ensure that only your assigned doctor can view your medical test results — not everyone in the system.

---

####  **PCI DSS** (Global – Payment Systems)

* This applies to any business that **accepts or handles credit/debit cards**.
* It protects your **payment information** from being misused or stolen.

**IAM helps by**:

* Making sure only payment systems or specific users can access card data.
* Enforcing **multi-factor authentication** for admins.

> **Example**: In an online shopping app, only the payment processor can see your card details — the marketing or support team cannot.

---

####  **GDPR** (Europe – Data Privacy)

* Made to protect the **privacy of people in the EU**.
* Gives users control over their own data (like deleting or downloading it).

**IAM helps by**:

* Giving data access only to people who need it.
* Letting users request data deletion or download.
* Keeping track of who accessed user data.

> **Example**: If you delete your account from a social media app, GDPR ensures your data is also deleted from the company’s systems — and IAM helps make that happen securely.

---

####  **SOX** (USA – Finance)

* Applies to public companies to prevent **fraud in financial data**.

**IAM helps by**:

* Making sure no single person can control everything (like creating and approving a payment).
* Tracking changes made to financial systems.
* Ensuring access is reviewed regularly.

> **Example**: In a finance department, one employee enters invoices and another approves them — IAM makes sure this separation is enforced.

---

### Why This Matters


**IAM makes it easier to follow the rules** by:

* Controlling who has access to what
* Logging every access or change
* Making sure only the right people can see sensitive data


Non-compliance can lead to:

* Fines
* Lawsuits
* Loss of customer trust


### 3. **Audit & Reporting**



### What are Audits & How Does IAM Help? 

An **audit** is a check to make sure a company is **following rules, security policies, and compliance standards**.

Auditors may ask:

* Who accessed sensitive systems or data?
* Were users given more access than needed?
* Is old or unused access being removed?

---

###  How IAM Helps in Audits 

IAM makes audits much easier by:

*  **Tracking all access** 
  → Keeps a record of who logged in, what they accessed, and when.

*  **Providing reports** 
  → Quickly shows which users have access to what systems.

*  **Cleaning up unused access** 
  → Helps remove access that is no longer needed.

*  **Enforcing policies** 
  → Makes sure only the right people have access to sensitive data.

> **Example**: 
> If an auditor asks, “Who had access to the HR system last month?”,
> IAM can generate a full report in seconds.

Without IAM, doing this manually would take hours or even days.



### 4. **Operational Efficiency**

IAM automates: (JML - Joiner , Mover , Leaver)

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


📝 Disclaimer:
This project is for personal learning only. Content is created by referring to public sources like blogs, Articles, YouTube, and AI tools. If any part needs credit or removal, kindly contact me ( Contact details in readme file of this repo).

💬 For suggestions, improvements, or opportunities, feel free to connect with me on LinkedIn or via email at shaileshgatkul2003@gmail.com.
