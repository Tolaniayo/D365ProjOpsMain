
# Lab [D365-PO] Day 2: Configuring Labor Pricing and Costing

## Lab Overview
In this lab, you will configure labor pricing and costing in Dynamics 365 Project Operations.  
You’ll create **Sales Price Lists** for billing, **Cost Price Lists** for internal costing, and test **transfer pricing** between multiple divisions using the Fabrikam demo data.

**Estimated time:** 2 hours  
**Lab Type:** Hands-on configuration

---

## Learning Objectives
After completing this lab, you will be able to:
1. Configure and manage **labor bill rates** on Sales Price Lists.  
2. Configure **labor cost rates** on Cost Price Lists.  
3. Enable and apply **Cost Plus Pricing**.  
4. Set up **transfer pricing** between multiple organizational units.  
5. Validate rates through **time entry** and ensure correct pricing determination.

---

## Lab Prerequisites
- Access to a D365 Project Operations (Lite Deployment) environment.  
- System Administrator or Project Manager role permissions.  
- Demo data (Fabrikam) installed.  

---

## Scenario
Fabrikam Corporation manages projects across multiple regions — US, India, and the Philippines.  
Each region has its own labor cost rates, but the US division is responsible for client billing.  
You have been asked to:
- Set up cost and sales price lists for each division,  
- Enable cost-plus pricing,  
- And validate pricing accuracy across the system.

---

## Exercise 1: Create Sales Price List (Bill Rates)
**Objective:** Configure bill rates for project sales

### Steps:
1. Navigate to **Sales → Customers → Price Lists**.  
2. Select **New** to create a Sales Price List:
   - **Name:** Fabrikam US Bill Rates FY25  
   - **Context:** Sales  
   - **Currency:** USD  
   - **Start Date:** 01/01/2025  
   - **End Date:** 12/31/2025  
3. Save the record.  
4. Under **Role Prices**, add the following lines:  

| Role | Resourcing Unit | Pricing Method | Price | Currency | Unit |
|------|------------------|----------------|--------|-----------|------|
| Developer | Fabrikam India | Price per Unit | 100 | USD | Hour |
| Developer | Fabrikam US | Price per Unit | 150 | USD | Hour |
| Consultant | Fabrikam Switzerland | Price per Unit | 90 | USD | Hour |

5. Save and close the price list.

### Validation
- Confirm all role prices appear under the Sales Price List.  
- Ensure the **Context = Sales** is correctly set.

---

## Exercise 2: Enable Cost Plus Pricing (Skip this Lab, Feature is in Preview)
**Objective:** Enable advanced pricing methods (Markup over cost, At cost)

### Steps:
1. Navigate to **Project Operations → Settings → Parameters**.  
2. Select the **Feature Control** tab.  
3. Locate **Enable Cost Plus Pricing** and toggle to **Yes**.  
4. Save and refresh the browser.

### Validation
- Confirm that **Markup over Cost** and **At Cost** options now appear under Pricing Methods on role lines.

---

## Exercise 3: Create Cost Price List (Cost Rates)
**Objective:** Configure internal cost rates per division.

### Steps:
1. Navigate to **Sales → Customers → Price Lists**.  
2. Select **New** and create a Cost Price List:
   - **Name:** Fabrikam India Cost Rates FY25  
   - **Context:** Cost  
   - **Currency:** Rupee  
   - **Start Date:** 01/01/2025  
   - **End Date:** 12/31/2025  
3. Save the record.  
4. Add the following lines under **Role Prices**:

| Role | Resourcing Unit | Price | Currency | Unit |
|------|------------------|--------|-----------|------|
| Developer | Fabrikam India | 1000 | INR | Day |
| Consultant | Fabrikam India | 1200 | INR | Day |

5. Repeat the process for **Fabrikam US Cost Rates FY25**:
   - Currency: USD  
   - Developer = $150/hr  
   - Consultant = $180/hr  

### Validation
- Verify that each cost list’s **Context** = Cost.  
- Ensure that cost lists reflect correct currencies per region.

---

## Exercise 4: Configure Transfer Pricing
**Objective:** Define cross-division rate logic.

### Steps:
1. Navigate to **Settings → Organizational Units**.  
2. Select **Fabrikam US** as the contracting unit.  
3. Under **Default Cost Price List**, add *Fabrikam US Cost Rates FY25*.  
4. Save changes.  
5. Repeat for **Fabrikam India** linking its own cost list.  

### Validation
- Each contracting unit has a default cost price list.  
- Ensure no overlapping effective dates exist.

---
# Exercise 5: Create a Project Contract

## Objective
In this exercise, you’ll create a **Project Contract** in Dynamics 365 Project Operations that connects your project to billing, pricing, and funding sources.  
You’ll configure the contract header, link the customer and project, and define contract lines with appropriate **contract types** and **price lists**.

---

## Learning Goals
By completing this exercise, you will be able to:
1. Create and configure a **Project Contract**.  
2. Associate **Projects** and **Funding Sources** with the contract.  
3. Assign **Price Lists** for billing and costing.  
4. Understand how **contract lines** control invoicing and revenue recognition.

---

## Scenario
Fabrikam has won a new project with **Contoso Ltd** to implement a global ERP rollout.  
You have already prepared the **Sales and Cost price lists**.  
Now, you need to create a **Project Contract** that will be used to bill Contoso for project work.

---

## Steps

### Step 1: Navigate to Project Contracts
1. In Dynamics 365, select the **Project Operations** app.  
2. Navigate to **Project Contracts** from the left-hand navigation pane.  
3. Click **+ New** to create a new contract.

---

### Step 2: Define the Contract Header
1. Enter the following details:
   - **Name:** Contoso ERP Implementation FY25  
   - **Customer:** Contoso Ltd  
   - **Contracting Unit:** Fabrikam US  
   - **Start Date:** 01/15/2025  
   - **End Date:** 12/31/2025  
   - **Currency:** USD  
2. Click **Save**.

> 💡 *Tip:* Setting **Type = Work-based** on the previous steps ensures that the contract supports project-based billing and time entry.

---

### Step 3: Add a Project to the Contract (Skip this as there is no existing project)
1. In the **Related Projects** section, select **+ Add Existing Project**.  
2. Choose the project named *Global Implementation FY25*.  
3. Click **Add**.  

> ⚙️ The system now links this project to the contract for billing and actual cost tracking.

---

### Step 4: Add Contract Lines 
1. In the **Contract Lines** tab, click **+ New Contract Line**.  
2. Enter:
   - **Line Name:** ERP Implementation – Time & Materials  
   - **Type:** Work-based  
   - **Billing Method:** Time and Materials  
   - **Sales Price List:** Fabrikam US Bill Rates FY25  
3. Save the contract line.

> 🔁 Each contract line defines how a specific part of the project is billed — by time, fixed fee, or milestone.

---

### Step 5: Assign a Cost Price List (Skip this, this is determined by the contracting unit)
1. Still within the **Contract Line**, scroll to the **Cost Price List** field.  
2. Select *Fabrikam India Cost Rates FY25*.  
3. Save changes.

> ✅ This ensures that labor costs from the resourcing unit are properly applied to this contract.

---

### Step 6: Split funding Sources (if there are multiple customers)
1. Select the **Funding Sources** tab.  
2. Click **+ Add Funding Source**.  
3. Enter:
   - **Funding Source:** Contoso Ltd  
   - **Percentage:** 100%  
4. Save.

> 🧾 If multiple customers or departments are funding a project, you can split the funding here (e.g., 70/30).

---

### Step 7: Activate the Contract
1. Once all details are correct, click **Confirm** on the command bar.  
2. Confirm the activation.  
3. The status changes to **Active**, meaning:
   - It’s now available for **invoicing**.  
   - Linked projects can post actuals against this contract.  
   - Billing transactions can be generated.

---

## Validation
- Confirm the **Project Contract** is visible under **Project Contracts → Active Contracts**.  
- The linked **Project**, **Contract Lines**, and **Funding Sources** should all be displayed.  
- Create a **sample time entry** for the project to verify that rates are pulled from the assigned **price lists**.

---

## Expected Result
| Validation Item | Expected Outcome |
|------------------|------------------|
| Contract Type | Work-based |
| Billing Method | Time & Materials |
| Sales Price List | Fabrikam US Bill Rates FY25 |
| Cost Price List | Fabrikam India Cost Rates FY25 |
| Status | Active |
| Linked Project | Global Implementation FY25 |

✅ The contract now enables automatic pricing, billing, and revenue recognition for the project.

---

## Lab Summary
In this exercise, you:
- Created a **Project Contract**.  
- Linked a **Project** and **Funding Source**.  
- Defined **Sales and Cost Price Lists**.  
- Activated the contract for **billing and reporting**.

🎯 You now have a fully functioning **contract-to-billing setup** in Dynamics 365 Project Operations.

