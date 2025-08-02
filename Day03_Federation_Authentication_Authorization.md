**Author:** Shailesh Gatkul  
**Date:** 28 July 2025


# Day 3: Federation, Authentication, Authorization & Compliance – Foundation of IAM

---

## Federation – The Backbone of Connected Identity

**Federation** allows a user to log in once and access multiple systems without re-entering credentials. It connects different identity systems using trust relationships.

### Real-life Example – Multi-vendor SSO at a Product Company:
A MNC like **XYZ** uses federation to enable its employees to access third-party SaaS apps like **Salesforce**, **Workday**, **GitHub**, and **Zoom** via a single company identity. The company’s IDP (like Azure AD or ForgeRock) issues tokens (via SAML or OIDC), which those SaaS apps trust.

### What Federation Enables:
- **SSO (Single Sign-On)** across multiple systems
- Enforces **MFA** before access is handed off to external systems
- Supports **third-party identity providers** (e.g., partner orgs logging into your systems)
- Reduces need to manage separate credentials in every service

---

## Authentication – Proving Identity

Authentication answers the question: **"Are you who you claim to be?"**

It’s the gate that checks user identity before any access is granted.

### Types of Authentication with Real-world Use:
- **LDAP** – Still used in legacy and enterprise apps for directory-based login (e.g., internal HR portals)
- **Kerberos** – Common in Microsoft enterprise environments (e.g., accessing shared drives or printers)
- **SAML / OIDC / WS-Fed / WS-Trust** – Used to authenticate users from federated/cloud systems like Google Workspace, AWS Console, Salesforce

### Example:
You log into your company laptop. Your username/password is validated by Active Directory (Kerberos). Then, using SSO (via SAML), you access internal HR apps without re-entering your credentials.

---

## Pass-through Authentication – Hybrid Identity Strategy

**Pass-through Authentication (PTA)** is used when organizations keep credentials on-premises but want cloud authentication. Cloud passes the credential to on-prem AD securely for validation.

### Real-life Example:
You log into **Microsoft 365** from your browser. Azure AD receives the login request and forwards it to your on-prem Active Directory via PTA. Passwords aren’t stored in Azure AD. It's seamless.

> **When Used:**
> - Hybrid environments (on-prem + cloud)
> - Compliance policies prevent cloud password storage
> - Want real-time password validation without sync delays

---

## Pre-auth vs Post-auth – When Access Controls Kick In

### Pre-authentication
Occurs *before* a user is fully authenticated. It blocks or filters logins based on certain policies.

#### Use Case:
An IAM policy blocks any login request from outside India unless the user is on a trusted device. This is enforced even before username/password validation begins.

### Post-authentication
Occurs *after* a successful login. The system checks what resources the user can now access.

#### Use Case:
A user logs into **AWS Console**. After authentication, IAM policies prevent them from accessing S3 but allow EC2 management.

### Benefits:
- **Pre-auth** reduces risk from untrusted devices or geolocations
- **Post-auth** supports fine-grained access decisions and session-level control

---

## Authorization – What You’re Allowed to Do

After authentication, **authorization** determines *what you can do*.

### Models:
- **RBAC** – HR Manager gets access to HR tools
- **ABAC** – Access based on location, device, time
- **PBAC** – Access rules defined by central policy engine

### Real-life Example:
An employee logs into ServiceNow. If they're from Finance, they can access invoice-related tickets. If they’re from IT, they can manage user provisioning.

---

## Authorization Use Cases in IAM

- **Federation Outcome:** Federation provides the identity. Authorization decides the access.
- **Granular Access:** You can grant access down to file, button, or field level
- **Least Privilege:** Users only get what’s needed (nothing more)
- **Segregation of Duties (SoD):** Critical in finance/IT. No user should deploy code *and* approve change requests.
- **Just-in-Time Provisioning (JIT):** Temporary access given dynamically and revoked after a task.

---

## Least Privilege – Security by Limiting Access

Organizations must ensure users only get what they *absolutely need*. Not more.

### Real-world Example:
A DevOps engineer in **a fintech startup** gets access to non-prod AWS accounts for testing, not production. Access to production is given temporarily via ticket approval.

### Why It Matters:
- Reduces blast radius during compromise
- Meets audit and compliance demands
- Enables safer collaboration with contractors or vendors

> IAM platforms like **Saviynt, SailPoint, ForgeRock** enforce least privilege through dynamic access provisioning and role-based access controls.

---

## Zero Trust – Security Without Borders

**Zero Trust** means never trusting any entity by default — even inside your network. Trust is earned dynamically, with multiple factors.

### Real-life Industry Use:
- **Google BeyondCorp**: Employees access apps based on device trust, location, role, and real-time signals
- **Okta + Zscaler**: Only devices with valid certificates and up-to-date patches can access cloud resources

### Use Case:
A remote employee must:
- Be on a corporate-managed device
- Use MFA
- Be located within approved countries
- Pass real-time checks (e.g., antivirus running)

Only then can they access internal apps.

---

## Segregation of Duties (SoD) – Preventing Risky Combinations

SoD ensures users can't misuse systems by having too many powerful roles at once.

### Real-life Enterprise Use Case:
In a **banking system**, a person who creates new loan applications must not be able to approve or disburse them. IAM systems flag these violations.

> Platforms like **SAP GRC**, **Saviynt**, and **SailPoint** have SoD engines that scan for role conflicts.

---

## Compliance – Why IAM Exists in Enterprises

IAM doesn’t exist in a vacuum. It’s often implemented to **meet compliance needs**.

### Real-life Examples:
- **Positive:** An insurance company uses IAM for RBAC and passes its annual ISO audit.
- **Negative:** A pharma company gets fined under GDPR for not deleting a customer’s identity after account closure.

### Compliance Frameworks that Drive IAM:
- **SOX** – Ensure SoD in financial workflows
- **HIPAA** – Restrict healthcare data access
- **GDPR** – Manage consent, right-to-be-forgotten, and access controls

Without strong IAM, compliance is nearly impossible.

---

💬 I’m always open to feedback, suggestions, collaboration, or professional opportunities in the Identity and Access Management (IAM) space.  
Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/shailesh-gatkul/) or reach out via email at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).

---

📌 **Disclaimer:**  
This repository is intended for **personal learning and educational purposes only**. The content has been compiled using knowledge gathered from publicly available sources such as technical blogs, documentation, YouTube tutorials, LinkedIn posts, community forums, and AI tools.  
If you believe any part of this content requires credit, correction, or removal, please contact me at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).



