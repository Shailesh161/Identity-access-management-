
## Optimized vs Unoptimized Aggregation in SailPoint ISC

### What is Unoptimized Aggregation?

* **Unoptimized aggregation** refers to **Full Aggregation**.
* In full aggregation, **all account records** from the source application are loaded into SailPoint.
* SailPoint processes every account, even if there are **no changes**.
* Because it consumes more time and resources, it is called **unoptimized aggregation**.

**Example:**
If an application has 500,000 accounts, SailPoint reads all 500,000 accounts during full aggregation.

---

### What is Optimized Aggregation?

* **Optimized aggregation** refers to **Delta Aggregation**.
* In delta aggregation, SailPoint fetches **only changed accounts**, such as:

  * Newly created accounts
  * Updated accounts
  * Deleted or disabled accounts
* Since SailPoint does not reprocess unchanged data, this approach is **faster and efficient**.

**Example:**
If only 200 accounts change out of 500,000, SailPoint processes only those 200 accounts.

---

## Aggregation in SailPoint ISC (UI vs Backend)

### UI Limitation

* In **SailPoint Identity Security Cloud (ISC)**:

  * Aggregation triggered from the **UI supports only Delta Aggregation**
  * **Full aggregation cannot be triggered directly from the UI**
* UI-based aggregation reads **only changed accounts**

---

### How to Run Full Aggregation in ISC

Since ISC is cloud-hosted, full aggregation must be triggered using backend tools.

#### Supported Tools:

* **VS Code**
* **Postman**

> Note: VS Code internally uses SailPoint **REST APIs**, similar to Postman.

---

### Steps to Run Full Aggregation Using VS Code

1. Open **VS Code**
2. Navigate to:

   ```
   Sources → Select the required source
   ```
3. Right-click on the source
4. Select **Import Accounts (Without Optimization)**
5. Choose the **Data Load CSV file**
6. Trigger the aggregation

This runs a **Full (Unoptimized) Aggregation**.

---

### How to Verify Aggregation Type from UI

1. Go to:

   ```
   Admin → Connections → Sources → Select Source
   ```
2. Open **Account Aggregation**
3. Scroll down to **Aggregation History**
4. Open **Details** of the latest aggregation

**Interpretation:**

* **Optimization = Enabled** → Delta Aggregation
* **Optimization = Disabled** → Full Aggregation

---

## Checking SailPoint Platform Health (ISC)

Since SailPoint ISC is hosted on the cloud, platform-level issues can be checked externally.

### SailPoint Status Page

* Visit: `status.sailpoint.com`
* Navigate to:

  * **Incidents**
  * **Service Status**

This helps confirm whether issues are:

* Source-related
* SailPoint platform-related

---

## How SailPoint Avoids Duplicate Identities

SailPoint prevents duplicate identities at **two levels**:

### 1️⃣ Account Level (Source Configuration)

Path:

```
Admin → Connections → Sources → Account Schema
```

* Unique attributes such as:

  * Account ID
  * Employee ID
  * Username
    are defined.
* These ensure accounts remain uniquely identified.

---

### 2️⃣ Identity Profile Level (Correlation)

Path:

```
Admin → Identities → Identity Profiles
```

* Identity correlation is configured by mapping:

  * Username or employeeNumber
  * With unique source attributes
* This ensures accounts are correctly linked to existing identities.

➡️ By managing uniqueness at **both account and identity levels**, SailPoint avoids duplicate identity creation.

---

## Creating a New Lifecycle State in SailPoint ISC

### Steps:

1. Go to:

   ```
   Admin → Identities → Identity Profiles
   ```
2. Open **Lifecycle Management**
3. Click **Create Lifecycle State**
4. Enter the lifecycle state name (e.g., Onboarding, Suspended)
5. Save the lifecycle state

The new lifecycle state will appear in the **left panel** under Lifecycle Management.

---

### Important Note

* Ensure the lifecycle state is **Enabled**
* Path to verify:

  ```
  Identity Profiles → Lifecycle Management → Select Lifecycle State
  ```
* Enable the **Lifecycle State checkbox** (e.g., Active, Terminated)

Only enabled lifecycle states are applied to identities.

---

## Interview One-Line Summary

> Full aggregation is unoptimized because it loads all accounts, whereas delta aggregation is optimized as it processes only changed accounts. In SailPoint ISC, UI supports only delta aggregation, and full aggregation is triggered using APIs via tools like VS Code or Postman.


