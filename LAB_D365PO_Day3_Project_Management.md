
# LAB [D365-PO] Day 3 – Managing Projects, Work Breakdown, and Estimation

## Lab Overview
In this lab, you will practice key skills in **Dynamics 365 Project Operations** related to **project planning, estimation, and pricing**.
You will:
- Create and manage a project with multiple stages.
- Build and modify a Work Breakdown Structure (WBS).
- Add time, expense, and material estimates.
- Configure pricing modes and verify financial impact.

This lab will take approximately **2 hours** to complete.

---

## Lab Objectives
After completing this lab, you will be able to:
1. Create a new project and define its key parameters.
2. Build and save a Work Breakdown Structure (WBS).
3. Create and update time, expense, and material estimates.
4. Configure and test different pricing modes.
5. Validate how financial and discount postings appear in journals.

---

## Prerequisites
- Access to **Dynamics 365 Project Operations** (Integrated or Lite deployment).
- Security Role: **Project Manager** or **System Administrator**.
- Existing Price Lists and Resources in your Organization Unit.
- Microsoft Edge or Chrome browser.

---

## Exercise 1 – Create a New Project
**Duration:** 15 minutes

1. Sign in to **Dynamics 365 Project Operations**.
2. Navigate to **Projects → + New Project**.
3. Complete the following fields:
   - **Project Name:** *Northwind Implementation*
   - **Customer:** *Northwind Traders*
   - **Currency:** *USD*
   - **Contracting Unit:** *US Delivery*
   - **Project Manager:** *(Your name)*
4. Select **Save**.
5. Verify the project **Stage = New**.
6. Change the project **Stage → Plan** to allow WBS creation.
7. Confirm that the record saves successfully.

✅ *Checkpoint:* The project record should display the correct contracting unit and project manager.

---

## Exercise 2 – Build a Work Breakdown Structure (WBS)
**Duration:** 25 minutes

1. On your new project, navigate to the **Tasks** tab.
2. Select **Edit in Project for the Web**.
3. Create the following tasks:

| Task | Duration | Predecessor | Role |
|-------|-----------|--------------|------|
| 1. Initiation | 2 days | — | Project Manager |
| 2. Planning | 3 days | 1 | Consultant |
| 3. Execution | 5 days | 2 | Developer |
| 4. Testing | 3 days | 3 | QA Engineer |
| 5. Closure | 2 days | 4 | Project Manager |

4. Use **Indent/Outdent** to create hierarchy (e.g., Planning and Execution as sub-tasks).
5. Click **Save** and observe save indicators:
   - 🟢 Green check = successful save.
   - 🔵 Spinner = save in progress.
   - 🔴 Red X = failure (refresh required).
6. Return to Project Operations and verify your WBS appears in Dataverse.

✅ *Checkpoint:* Verify WBS tasks sync successfully with Dataverse (check in Timeline view).

---

## Exercise 3 – Add Time Estimates
**Duration:** 20 minutes

1. Open your project record.
2. Go to **Estimates → Time**.
3. Select **+ New Estimate**.
4. Enter:
   - **Task:** *Execution*
   - **Resource Role:** *Developer*
   - **Effort:** *60 hours*
   - **Cost Rate:** *$80/hr*
   - **Sales Rate:** *$120/hr*
5. Click **Save**.
6. Verify that two records are created: one for **Cost**, one for **Sales**.
7. Confirm that totals roll up to the task and project header.

✅ *Checkpoint:* Project cost and sales totals should automatically update.

---

## Exercise 4 – Add Expense and Material Estimates
**Duration:** 25 minutes

### Part A – Expense Estimate
1. Navigate to **Estimates → Expenses**.
2. Click **+ New Expense**.
3. Set:
   - **Task:** *Testing*
   - **Category:** *Travel*
   - **Quantity:** *10 units*
   - **Price:** *$200*
   - **Sales Price:** *$200*
4. Save and confirm total = $2,000 cost and sales.

### Part B – Material Estimate
1. Select **Estimates → Materials**.
2. Click **+ New Material**.
3. Add details:
   - **Task:** *Execution*
   - **Product:** *Laptop – Write-in*
   - **Quantity:** *5 units*
   - **Cost:** *$1,200 each*
   - **Sales Price:** *$1,400 each*
4. Save and verify total material cost = $6,000.

✅ *Checkpoint:* Confirm all estimate types appear in project summary totals.

---

## Exercise 5 – Configure and Test Pricing Modes
**Duration:** 15 minutes

1. Navigate to **Settings → Parameters → Estimate Pricing Options**.
2. Review options:
   - **Real-Time Pricing** – Auto-updates every edit.
   - **On-Demand Pricing** – Requires manual update.
3. Switch to **On-Demand Pricing**.
4. Return to your project and modify task duration.
5. Observe that cost/sales rates do not change until you click **Update Prices**.

✅ *Checkpoint:* Pricing updates only when manually triggered in On-Demand mode.

---

## Exercise 6 – Validate Financial and Discount Posting
**Duration:** 20 minutes

1. From the project form, open **Financials → Journal Entries**.
2. Review **WIP** and **Accrual** postings generated from approved actuals.
3. Add a **Discount** to your project line (e.g., 10%).  
4. Observe how discount affects total revenue.
5. Verify whether discount posts to **Discount Ledger Account** or reduces revenue directly.
6. Confirm tax applies to the net amount after discount.

✅ *Checkpoint:* Discount postings should appear correctly in Financial journals.

---

## Exercise 7 – Review and Discussion
**Duration:** 10 minutes

- Review your project totals:
  - Total Cost vs Total Sales
  - Expense and Material roll-ups
  - Pricing mode effects
- Discuss:
  - When to use Real-Time vs On-Demand pricing?
  - How do discounts impact project margin?
  - What data is shared between Project Operations and Finance?

✅ *End of Lab Check:* All project data should be visible in Dataverse and pricing should reflect configuration.

---

## Summary
In this lab, you:
- Created a new project and defined lifecycle stages.
- Built a WBS and observed asynchronous saving.
- Added time, expense, and material estimates.
- Tested real-time vs on-demand pricing.
- Validated financial and discount postings in journals.

You now understand how **estimation, pricing, and project management** work together in **Dynamics 365 Project Operations**.
