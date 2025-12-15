# SailPoint ISC – Full and Delta Aggregation

## 1. What is Aggregation in SailPoint ISC?
Aggregation in SailPoint Identity Security Cloud (ISC) is the process of **collecting identity data from target applications** into SailPoint.

During aggregation, SailPoint pulls:
- Accounts (users)
- Entitlements (roles, groups, permissions)
- Account–entitlement relationships

In simple terms, aggregation means **syncing application data into SailPoint**.

---

## 2. Full Aggregation

### Definition
Full Aggregation is a process where **all data from the target application is fetched**, regardless of whether data has changed or not.

It retrieves:
- All accounts
- All entitlements
- All account–entitlement mappings

---

### When is Full Aggregation Used?
- Initial application onboarding
- Major schema or attribute changes
- Data inconsistency or corruption
- Periodic full reconciliation (rare)

---

### Real-Life IAM Example
**Application:** Active Directory (AD)  
**Scenario:** AD is integrated with SailPoint ISC for the first time.

- AD has 50,000 user accounts
- SailPoint performs Full Aggregation

Result:
- All 50,000 users are imported
- All AD groups are imported
- User–group relationships are mapped

Even if only one user changes later, Full Aggregation still fetches **all data**.

---

### Key Characteristics
- Time-consuming
- High system load
- Provides a complete snapshot of application data
- Not suitable for frequent execution

---

### Simple Analogy
Reading the **entire book again**, even if only one page was updated.

---

## 3. Delta Aggregation

### Definition
Delta Aggregation fetches **only the data that has changed** since the last successful aggregation.

It includes:
- Newly created accounts
- Modified accounts
- Deleted or disabled accounts
- Updated entitlements

---

### When is Delta Aggregation Used?
- Daily or hourly synchronization
- Large-scale enterprise environments
- Production systems
- Performance optimization

---

### Real-Life IAM Example
**Application:** Active Directory  
**Last 24 hours changes:**
- 3 new employees joined
- 2 employees changed roles
- 1 employee left the organization

Delta Aggregation:
- Imports only these 6 changes
- Does not re-fetch all 50,000 users

---

### Key Characteristics
- Fast and efficient
- Low system load
- Scales well for large organizations
- Depends on accurate tracking of changes

---

### Simple Analogy
Reading **today’s newspaper**, not the entire archive.

---

## 4. Full vs Delta Aggregation Comparison

| Aspect | Full Aggregation | Delta Aggregation |
|------|------------------|------------------|
| Data Pulled | All data | Only changed data |
| Speed | Slow | Fast |
| System Load | High | Low |
| Frequency | Rare | Frequent |
| Usage | Initial setup | Regular updates |
| Best For | Baseline sync | Daily sync |

---

## 5. Enterprise IAM Best Practice
1. Perform **Full Aggregation** during application onboarding to establish a baseline.
2. Schedule **Delta Aggregation** for daily or near-real-time updates.
3. Run Full Aggregation only when major changes occur.

This approach ensures **accuracy, performance, and scalability** in SailPoint ISC.

---

## 6. Interview / Exam One-Liners
- **Full Aggregation:** Fetches complete application data every time, irrespective of changes.
- **Delta Aggregation:** Fetches only incremental changes since the last aggregation.

---

## 7. Why Delta Aggregation is Critical in IAM
- Enterprises manage millions of identities
- Frequent full aggregations cause performance issues
- Delta aggregation enables scalable and efficient identity governance
