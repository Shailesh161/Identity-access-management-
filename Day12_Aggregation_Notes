}
**Author:** Shailesh Gatkul
---

# Full and Delta Aggregation in SailPoint ISC

---

## What is Aggregation in SailPoint ISC?

In **SailPoint Identity Security Cloud (ISC)**, **Aggregation** is the process of **collecting identity-related data from target applications into SailPoint**.

During aggregation, SailPoint pulls:

* User accounts
* Entitlements (roles, groups, permissions)
* Account–entitlement relationships

In simple terms, aggregation means **keeping SailPoint in sync with connected applications** so identities can be governed correctly.

> Without aggregation, SailPoint would not know:
>
> * Who exists in the application
> * What access they have
> * What has changed over time

---

## What is Full Aggregation?

### Definition

**Full Aggregation** is a process where **all data from the target application is fetched**, regardless of whether the data has changed or not.

It retrieves:

* All accounts
* All entitlements
* All account–entitlement mappings

This is also referred to as **Unoptimized Aggregation** because it processes everything every time.

---

### When is Full Aggregation Used?

Full Aggregation is typically used when:

* An application is onboarded for the first time
* Major schema or attribute changes occur
* Data inconsistency or corruption is suspected
* A complete baseline refresh is required (rare in production)

---

### Real-Life IAM Example

**Application:** Active Directory (AD)

**Scenario:**
AD is integrated with SailPoint ISC for the first time.

* AD contains 50,000 user accounts
* SailPoint runs a Full Aggregation

**Result:**

* All 50,000 users are imported
* All AD groups are imported
* User–group relationships are established

Even if only one user changes later, Full Aggregation still reads **all 50,000 records**.

---

### Key Characteristics of Full Aggregation

* Time-consuming
* High load on source application
* Provides a complete snapshot of data
* Not recommended for frequent execution

---

### Simple Analogy

Reading the **entire book again**, even though only one page was updated.

---

## What is Delta Aggregation?

### Definition

**Delta Aggregation** fetches **only the data that has changed** since the last successful aggregation.

It includes:

* Newly created accounts
* Updated or modified accounts
* Deleted or disabled accounts
* Updated entitlements

This is called **Optimized Aggregation** because it avoids unnecessary processing.

---

### When is Delta Aggregation Used?

Delta Aggregation is used for:

* Daily or scheduled synchronizations
* Large enterprise environments
* Production IAM systems
* Performance-efficient identity governance

---

### Real-Life IAM Example

**Application:** Active Directory

**Changes in the last 24 hours:**

* 3 new employees joined
* 2 employees changed departments
* 1 employee left the organization

**Delta Aggregation Result:**

* Only these 6 changes are processed
* Existing 50,000 users are not re-fetched

---

### Key Characteristics of Delta Aggregation

* Fast and efficient
* Low system and application load
* Scales well for millions of identities
* Depends on accurate change tracking

---

### Simple Analogy

Reading **today’s newspaper**, not the entire archive.

---

## Full vs Delta Aggregation – Comparison

| Aspect       | Full Aggregation            | Delta Aggregation |
| ------------ | --------------------------- | ----------------- |
| Data Pulled  | All data                    | Only changed data |
| Speed        | Slow                        | Fast              |
| System Load  | High                        | Low               |
| Frequency    | Rare                        | Frequent          |
| Usage        | Initial setup / major fixes | Regular updates   |
| Optimization | Unoptimized                 | Optimized         |

---

## Aggregation in SailPoint ISC – UI vs Backend

In **SailPoint ISC**:

* Aggregation triggered from the **UI supports only Delta Aggregation**
* Full Aggregation **cannot be triggered directly from the UI**

To run Full Aggregation, backend tools are used:

* **VS Code**
* **Postman**

> Both VS Code and Postman internally use **SailPoint REST APIs**.

---

## How to Verify Aggregation Type from UI

Path:

```
Admin → Connections → Sources → Select Source
```

Steps:

1. Open **Account Aggregation**
2. Scroll to **Aggregation History**
3. Open **Details** of the aggregation run

**Interpretation:**

* **Optimization = Enabled** → Delta Aggregation
* **Optimization = Disabled** → Full Aggregation

---

## Enterprise IAM Best Practices

* Run **Full Aggregation** only during onboarding or major changes
* Schedule **Delta Aggregation** for daily or near-real-time updates
* Avoid frequent Full Aggregations in production

This ensures:

* Performance
* Scalability
* Stable identity governance

---

## Interview One-Liners

* **Full Aggregation:** Loads all application data every time, irrespective of changes.
* **Delta Aggregation:** Loads only incremental changes since the last aggregation.

---

## Key Takeaway

> Full Aggregation establishes the baseline, while Delta Aggregation keeps identities continuously updated without impacting performance.

---

💬 I’m always open to feedback, suggestions, collaboration, or professional opportunities in the Identity and Access Management (IAM) space.
Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/shailesh-gatkul/) or reach out via email at [shaileshgatkul2003@gmail.com](mailto:shaileshgatkul2003@gmail.com).

---

📌 **Disclaimer:**
This repository is intended for **personal learning and educational purposes only**. The content has been compiled using knowledge gathered from publicly available sources such as documentation, blogs, community discussions, and practical experience.
If you believe any part of this content requires credit, correction, or removal, please contact me.
