**Author:** Shailesh Gatkul  
**Date:** 26 July 2025




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

**Identity** is a unique way to represent a person, system, or device in a digital system — so the system knows who is trying to access it.(An identity tells the system "who you are")

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

### 🤖 Examples of Machine Identities

|  Use Case                                 |  Machine Identity Used          |
|-------------------------------------------|---------------------------------|
| A microservice calls another microservice | OAuth token or mTLS certificate |
| IoT device sends data to the cloud        | Device certificate or key pair  |


IAM systems treat both human and machine identities equally in terms of assigning roles, policies, and permissions.


##  What is Access?

**Access** defines **what an identity is allowed to do** with a specific resource in a system.

In IAM, access is controlled through **permissions**, which determine:

* What actions can be performed (e.g., read, write, delete)
* On which resources (e.g., files, databases, APIs)
* Under what conditions (e.g., only during working hours, from trusted devices)

---

###  Common Types of Access:

* **Read** – View or retrieve data
* **Write** – Create or modify data
* **Execute** – Run scripts or commands
* **Delete** – Remove data
* **Admin Access** – Full control over configurations and permissions

---

### 📌 Real-Life Examples:

| Role             | Resource                   | Level of Access         |
| ---------------- | -------------------------- | ----------------------- |
| HR Manager       | Employee database          | Read + Write            |
| Regular Employee | Own profile page           | Read-only               |

---

Access is governed using:

* **Policies** (what is allowed or denied)
* **Roles** (predefined sets of permissions)
* **Groups** (collection of users with similar access)

>  IAM ensures that **only authorized identities** get the **appropriate level of access**, nothing more, nothing less.

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

Confidentiality means that sensitive data is only accessible to the right people — and kept hidden from unauthorized users or systems

> Example: Only the finance team should have access to company budget files.

IAM enforces this via:

* Role-based access control (RBAC)
 - Users are assigned roles (like HR, Finance, Admin), and each role has specific permissions.
 - This ensures that users can only access data relevant to their job.
 - e.g A user with the “Finance Analyst” role can access financial dashboards, but not HR records. 

* Policies
- Policies are the rules and conditions that define what actions an identity can or cannot perform on specific resources.
- In IAM, policies are used to grant or deny access based on things like user role, resource type, time, or device.
- They are typically written in a structured format (e.g., JSON in AWS IAM) and attached to users, groups, or roles.
-Example:A policy might say:
   “Allow users in the FinanceTeam group to read and edit files in the /budgets/ folder, but deny access to /executive-salaries/.”

  {
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::finance-bucket/budget-reports/*",
      "Condition": {
        "StringEquals": {
          "aws:username": "finance-user"
        }
      }
    }
  ]
}


* Encryption
- Even if someone gets access to the data, encryption ensures they can’t read it without proper keys.
- IAM tools often manage and integrate with encryption systems like KMS (Key Management Service).
- E.g., Budget data stored in the cloud is encrypted at rest, and only the Finance app (with valid IAM role) can decrypt it.

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
In IAM, confidentiality is the most important because its main job is to ensure that only the right people can access sensitive information. For example, in an online shopping site, if the system is temporarily down (availability issue), users can wait and try later. If some data is shown incorrectly (integrity issue), it can be fixed. But if an unauthorized person gets access to user details like saved cards or addresses (confidentiality issue), it leads to serious problems like data breaches, fraud, and legal issues. That’s why protecting data from unauthorized access is the top priority in IAM

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


---

💬 I’m always open to feedback, suggestions, collaboration, or professional opportunities in the Identity and Access Management (IAM) space.  
Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/shailesh-gatkul/) or reach out via email at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).

---

📌 **Disclaimer:**  
This repository is intended for **personal learning and educational purposes only**. The content has been compiled using knowledge gathered from publicly available sources such as technical blogs, documentation, YouTube tutorials, LinkedIn posts, community forums, and AI tools.  
If you believe any part of this content requires credit, correction, or removal, please contact me at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).

