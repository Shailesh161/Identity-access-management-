# Identity State vs Lifecycle State in SailPoint ISC

> **100 Days of IAM – SailPoint Identity Security Cloud (ISC)**  
> This note explains the **difference between Identity State and Lifecycle State** in SailPoint ISC, how **Access Profiles** fit into the model, and how all three work together in real enterprise environments.


---

## 1. What is Identity State in SailPoint ISC?

**Identity State** represents the **technical/system status of an identity inside SailPoint**.

It answers:
> _“Does this identity exist in SailPoint, and should SailPoint process it?”_

Identity State is **system-driven**, not business-driven.

---

### Common Identity States (Practical View)

| Identity State | Meaning | IAM Impact |
|---------------|--------|-----------|
| Active | Identity exists and is usable | Provisioning, reviews, policies apply |
| Inactive / Disabled | Identity exists but should not be used | No new access |
| Deleted | Identity removed | SailPoint stops processing |
| Archived | Stored for audit | Read-only, no actions |

> If Identity State is **Deleted**, SailPoint will **not apply lifecycle rules, access profiles, or workflows**.

---

### Real-Life Example (Identity State)

**User:** Amit (Employee)

| Event | Identity State |
|-----|---------------|
| Joined company | Active |
| HR account disabled | Inactive |
| Record permanently removed | Deleted |

Identity State controls **existence and processing**, not access design.

---

## 2. What is Lifecycle State in SailPoint ISC?

**Lifecycle State** represents the **business stage of an identity** within the organization.

It answers:
> _“Where is this person in their employment journey, and what access should they have?”_

Lifecycle State is:
- Business-driven
- Configured under **Identity Profiles**
- Core to **Joiner–Mover–Leaver (JML)** automation

---

### Common Lifecycle States (Enterprise Standard)

| Lifecycle State | Meaning |
|----------------|--------|
| Onboarding | New joiner |
| Active | Fully active employee |
| Transfer / Role Change | Internal movement |
| Leave of Absence (LOA) | Temporarily inactive |
| Offboarding | Exit process started |
| Terminated | Employment ended |

---

### Real-Life Example (Lifecycle State)

**User:** Neha

| Business Event | Lifecycle State |
|---------------|----------------|
| Joined as intern | Onboarding |
| Converted to full-time | Active |
| Took long leave | LOA |
| Resigned | Offboarding → Terminated |

Lifecycle State decides **what access should exist**, not whether the identity exists.

---

## 3. Where Access Profiles Fit In (Critical Concept)

This is the **most important missing link in many explanations**.

### What are Access Profiles?

**Access Profiles** are **bundles of access** that contain:
- Entitlements (groups, roles, permissions)
- Provisioning logic
- Application mappings

They answer:
> _“What exact access should be provisioned?”_

---

### Lifecycle State → Access Profile Mapping

👉 **Lifecycle State directly controls which Access Profiles are assigned or removed.**

| Lifecycle State | Access Profiles Assigned |
|----------------|--------------------------|
| Onboarding | Email, HR Portal |
| Active | Email, HR, Finance App |
| LOA | None (access removed) |
| Offboarding | Revocation only |
| Terminated | Identity disabled |

> **Access Profiles are never driven by Identity State.**

---

## 4. Identity State vs Lifecycle State vs Access Profiles

| Concept | Purpose | Controls |
|------|--------|---------|
| Identity State | Technical existence | Whether SailPoint processes the identity |
| Lifecycle State | Business phase | Which access should apply |
| Access Profiles | Access definition | What access is provisioned |

---

## 5. End-to-End Real-Life Flow (ISC)

**User:** Rahul

1. HR record created  
   - Identity State → Active  
   - Lifecycle State → Onboarding  
   - Access Profiles → Email, Jira

2. Rahul becomes full-time  
   - Lifecycle State → Active  
   - Access Profiles → Email, Jira, Git, Prod Read

3. Rahul takes sabbatical  
   - Lifecycle State → LOA  
   - Access Profiles → Removed

4. Rahul resigns  
   - Lifecycle State → Offboarding → Terminated  
   - Identity State → Disabled  
   - Result → Identity retained for audit, no access

---

## 6. Common Misconfigurations and Impact

| Issue | Impact |
|-----|-------|
| Incorrect Identity State | Identity ignored or duplicated |
| Wrong Lifecycle State | Over- or under-provisioning |
| Poor Access Profile mapping | Security or compliance risk |

---

## 7. Interview-Ready One-Liners

- **Identity State** controls whether an identity exists and is processed.
- **Lifecycle State** controls the business phase of the identity.
- **Access Profiles** define the actual access provisioned.
- Lifecycle State **drives Access Profile assignment**, not Identity State.

---

## 8. Key Takeaway

> In SailPoint ISC, **Identity State controls existence**, **Lifecycle State controls business context**, and **Access Profiles control access**.  
> Together, they enable secure and automated Joiner–Mover–Leaver flows at scale.

---
