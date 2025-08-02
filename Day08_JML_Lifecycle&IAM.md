
---
## 🔹 What is the JML Lifecycle?

**JML (Joiner-Mover-Leaver)** is the identity lifecycle management process followed by organizations to control user access from **onboarding** to **offboarding**.

In simple terms:

* **Joiner:** When someone joins the company.
* **Mover:** When they change roles, departments, or teams.
* **Leaver:** When they leave the company.

Each phase should automatically trigger access changes through the IAM system.

---

## 🔹 Why JML Matters in IAM

1. **Security:** Prevent unauthorized access.
2. **Compliance:** Ensure timely de-provisioning of access.
3. **Efficiency:** Speed up onboarding and internal transfers.
4. **Audit Readiness:** Clear trace of access history over time.

Without JML, accounts stay active long after employees leave or move, leading to access creep and insider risk.

---

## 🔹 How IAM Enables JML (Step-by-Step)

###  Step 1: Integration with Source of Truth (HRMS)

IAM connects with Workday, SAP SuccessFactors, BambooHR, etc., to detect changes.

* When HR adds/updates a user, IAM gets notified in real time.

###  Step 2: Identity Creation and Role Assignment

IAM creates a digital identity using attributes like title, department, and location.

* Roles are auto-assigned (via RBAC or ABAC logic).
* Group memberships and app access are provisioned automatically.

###  Step 3: Monitoring and Policy Enforcement

IAM continuously monitors identities for events:

* Role change triggers SoD checks.
* Long-inactive accounts flagged for review.

###  Step 4: Leaver Automation and Access Revocation

When someone exits:

* IAM disables access to all systems.
* Notifies stakeholders (manager, IT, HR).
* Ensures compliance with defined offboarding SLA.

###  Step 5: Reporting and Audit Logging

All access events are logged:

* What access was granted, changed, or revoked.
* Timestamped logs for compliance reviews.

---

## 🔹 Traditional vs IAM-Based JML Process

| Aspect                | Traditional Process                    | IAM-Based JML Process                             |
| --------------------- | -------------------------------------- | ------------------------------------------------- |
| Joiner provisioning   | Manual by IT (emails/tickets)          | Automatic from HR feed                            |
| Mover role changes    | Often missed or delayed                | Triggered by role/department change in HRMS       |
| Leaver deprovisioning | Manual and error-prone                 | Automatically revokes access, alerts stakeholders |
| Audit readiness       | Incomplete logs, manual trails         | Centralized, timestamped access and change logs   |
| Risk exposure         | High (standing access, stale accounts) | Low (least privilege, time-bound access)          |

---

## 🔹 Real-Life Use Cases of JML in IAM

### 1. **Joiner – Day One Access Provisioning**

**Scenario:** A software engineer joins the product team.
**IAM Workflow:**

* HR system updates the new hire in Workday.
* IAM detects the new entry.
* Auto-assigns `Engineer_Role`.
* Access granted to Jira, GitHub, Slack.
  **Why it matters:** Engineer is productive from Day 1.

### 2. **Mover – Transfer to Security Team**

**Scenario:** QA engineer shifts to InfoSec team.
**IAM Solution:**

* Change detected in HR tool.
* IAM revokes old roles (`QA_Tester`), assigns new (`Security_Analyst`).
* SoD checks prevent role conflict.
  **Why it matters:** Prevents excessive or conflicting access.

### 3. **Leaver – Clean Offboarding**

**Scenario:** Employee resigns.
**IAM Steps:**

* HR logs resignation.
* IAM revokes access to apps, disables identity.
* Notifies asset team for hardware recovery.
  **Why it matters:** Closes all access paths, avoids insider threat.

---

## 🔹 IAM Tools That Automate JML

| Tool          | Capability                                                                        |
| ------------- | --------------------------------------------------------------------------------- |
| **SailPoint** | Lifecycle Manager module – automates JML workflows, integrates with HRMS          |
| **Saviynt**   | End-to-end user lifecycle management tied to business processes                   |
| **Okta**      | Universal Directory + Lifecycle hooks to automate provisioning and deprovisioning |
| **Azure AD**  | Dynamic group memberships, auto role assignment, and provisioning rules           |

---

## 🔹 Benefits of Implementing JML in IAM

* **Consistency:** Fewer manual errors.
* **Scalability:** Works across thousands of users.
* **Reduced Risk:** No access creep or orphan accounts.
* **Compliance-Ready:** Easy to show access changes to auditors.
* **Speed:** Automated access improves productivity.

---

## 🔹 Common Pitfalls and Fixes

| Problem                            | Fix                                                            |
| ---------------------------------- | -------------------------------------------------------------- |
| Manual provisioning delays         | Integrate IAM with HRMS and use automation                     |
| Orphan accounts after resignations | Trigger automated de-provisioning from HR feed                 |
| Access creep during role change    | Build movement policies with revocation logic                  |
| No audit trail                     | Ensure IAM logs all events (join/move/leave) to a central SIEM |

---

## 🔹 JML + IAM = Identity Lifecycle Done Right

IAM doesn’t just help with access control — it acts as a bridge between HR, IT, and security to ensure that identity data is always in sync, access is always accurate, and risk is always managed.

If implemented properly:

* IAM automates 90% of the JML tasks.
* It enforces SoD, RBAC, and deprovisioning rules in real time.
* It ensures your org never fails an audit because of stale or excessive access.

---

## 🔚 Final Thoughts

The JML lifecycle is **not just about onboarding and offboarding** — it’s about managing identities securely *throughout their journey* in the organization.

---

💬 I’m always open to feedback, suggestions, collaboration, or professional opportunities in the Identity and Access Management (IAM) space.  
Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/shailesh-gatkul/) or reach out via email at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).

---

📌 **Disclaimer:**  
This repository is intended for **personal learning and educational purposes only**. The content has been compiled using knowledge gathered from publicly available sources such as technical blogs, documentation, YouTube tutorials, LinkedIn posts, community forums, and AI tools.  
If you believe any part of this content requires credit, correction, or removal, please contact me at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).


