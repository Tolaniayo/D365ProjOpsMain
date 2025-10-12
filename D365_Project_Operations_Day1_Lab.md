
# LAB [D365-PO] Day 1: Configure and Manage Project-Based Sales Scenarios

## Lab Title: Configure and Manage Leads, Opportunities, and Quotes for Project Operations

**Lab Duration:** 2 hours  
**Module:** Day 1 – Project Operations Fundamentals  
**Lab Type:** Hands-on Exercise  

---

## Lab Overview

In this lab, you will configure and experience the core entities that form the foundation of Dynamics 365 Project Operations: Leads, Opportunities, Quotes, Products, Units, Currencies, and Organizational Units.  
By the end of this lab, you will understand how data flows from a Work-based Lead to a finalized Project Quote, and how financial structures (price lists, currencies, units) underpin this process.

---

## Lab Objectives

After completing this lab, you will be able to:

1. Create and qualify a **Work-based Lead**.  
2. Manage a **Project-based Opportunity** and add both **Product** and **Project lines**.  
3. Create and configure a **Project Quote** from an opportunity.  
4. Add **Products, Price Lists, and Organizational Units** to support quoting.  
5. Apply **custom pricing** and review profitability analytics.

---

## Scenario

You are a project sales manager at **Contoso Global Solutions**, responsible for preparing a proposal for a new consulting engagement.  
You must capture the customer’s interest, qualify the lead, estimate work through a project opportunity, and generate a quote including both product-based and project-based items.  
Your organization operates two divisions: **Contoso US** and **Contoso India**, each with distinct cost structures.

---

## Exercise 1: Create and Qualify a Work-Based Lead (Estimated time: 20 minutes)

### Task 1 – Create a Lead

1. Navigate to **Sales > Leads**.  
2. Select **+ New**.  
3. Enter the following details:
   - **Topic:** Contoso CRM Implementation  
   - **Type:** Work-based  
   - **First Name:** John  
   - **Last Name:** Carter  
   - **Company:** Northwind Traders  
   - **Currency:** USD  
4. Save the record.

### Task 2 – Qualify the Lead

1. In the command bar, select **Qualify**.  
2. Verify that:
   - An **Account**, **Contact**, and **Opportunity** were created automatically.  
   - The **Opportunity Type** is *Work-based*.

✅ **Result:** The system created a new project opportunity linked to Northwind Traders.

---

## Exercise 2: Manage a Project-Based Opportunity (Estimated time: 25 minutes)

### Task 1 – Add Opportunity Lines

1. Open the newly created opportunity.  
2. On the **Project Opportunity Lines** tab, add:
   - **Product Type:** Project-based Service  
   - **Customer Budget:** 50,000  
   - **Billing Method:** Time and Materials  
3. On the **Product Opportunity Lines** tab, add:
   - **Product:** Dynamics 365 Licenses (or create a Write-In product if unavailable).  
   - **Budget:** 5,000 USD.  

### Task 2 – Review Key Fields

Ensure the following:
- **Contracting Unit** = Contoso US.  
- **Account Manager** = Your user account.  
- **Estimated Revenue** = 55,000 USD.

✅ **Result:** The opportunity now contains both service and product line items.

---

## Exercise 3: Create and Configure a Project Quote (Estimated time: 30 minutes)

### Task 1 – Create a Quote

1. From the opportunity, select **Create Quote**.  
2. Confirm that **Quote Type** = Work-based.  
3. Review the **Summary Tab** to confirm:
   - Account = Northwind Traders  
   - Currency = USD  
   - Contracting Unit = Contoso US  

### Task 2 – Add a Project Price List

1. Navigate to the **Project Price Lists** tab.  
2. Select **+ Add New Project Price List**.  
3. Choose **Sales context**, ensure currency matches USD.  
4. Add a **date range** that covers the current fiscal year.  

### Task 3 – Add Quote Lines

1. In **Project Lines**, create:
   - **Line 1:** CRM Implementation – Time and Materials, Budget = 45,000 USD  
   - **Line 2:** System Configuration – Fixed Price, Budget = 5,000 USD  
2. In **Product Lines**, add:
   - **Product:** Dynamics 365 Licenses, Quantity = 10, Price = 500 USD each.  
3. Save and confirm **Total Quote Value = 55,000 USD**.

✅ **Result:** A fully configured project quote is ready for internal review.

---

## Exercise 4: Configure Supporting Data (Products, Units, and Org Units) (Estimated time: 25 minutes)

### Task 1 – Add a Product
1. Navigate to **Settings > Product Catalog > Products**.  
2. Select **+ New** and fill:
   - **Name:** Dynamics 365 License  
   - **Product ID:** D365-LIC-001  
   - **Unit Group:** Each  
   - **Default Unit:** Piece  
   - **Default Price List:** USD Standard Price List  
3. Save.

### Task 2 – Create a Unit Group
1. Navigate to **Settings > Unit Groups** → **+ New**.  
2. Enter **Name:** Consulting Hours.  
3. Add Units:
   - **Hour (Base Unit)**  
   - **Day (8 Hours)**  

### Task 3 – Create Organizational Units
1. Go to **Settings > Organizational Units**.  
2. Create two units:
   - **Contoso US**, Currency = USD  
   - **Contoso India**, Currency = INR  
3. Add distinct **Cost Price Lists** for each.

✅ **Result:** Supporting financial entities now align with company structure.

---

## Exercise 5: Apply Custom Pricing and Review Analytics (Estimated time: 20 minutes)

### Task 1 – Adjust Pricing
1. Return to your **Project Quote**.  
2. Select **Price Override** on the Summary tab.  
3. Increase line item 1 (CRM Implementation) price by 10%.  
4. Click **Recalculate**.

### Task 2 – Analyze Profitability
1. Open the **Analytics tab**.  
2. Review:
   - **Chargeable Costs**
   - **Revenue**
   - **Gross Margin**  
3. Compare results before and after the price change.

✅ **Result:** The quote margins now reflect the pricing adjustments and profitability metrics.

---

## Exercise 6: Close Opportunity as Won (Estimated time: 10 minutes)

1. Navigate back to the **Opportunity** record.  
2. Verify all quotes are closed or inactive.  
3. Select **Close as Won**.  
4. Enter **Actual Revenue = 55,000 USD** and **Close Date = Today’s Date**.  

✅ **Result:** The opportunity is successfully closed as won, creating the foundation for a project contract.

---

## Validation

| Validation Task | Expected Outcome |
|------------------|------------------|
| Lead qualified as Work-based | Account, Contact, and Opportunity created |
| Opportunity with two line types | Correct estimated revenue and Contracting Unit |
| Project Quote with pricing and analytics | Accurate total and margin data |
| Products, Units, and Org Units configured | Available for quote association |
| Opportunity closed as won | Record transitions to delivery stage |

---

## End of Lab

🎓 **Congratulations!** You have completed the Day 1 lab for Dynamics 365 Project Operations.  
You now understand how to configure foundational sales entities, manage financial data, and move a deal from Lead to Quote — ready for project execution.
