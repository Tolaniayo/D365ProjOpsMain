# LAB[PROJ-OPS]_Day5Lab01 — Manage Vendor Invoicing and Subcontractor Costs

## Lab overview
In this lab, you will work through a complete subcontractor management workflow — from associating contract workers and costing assignments to creating, verifying, and approving vendor invoices.  
You’ll use an existing subcontract and project to simulate how subcontractor costs flow into project financials.

**Estimated time:** 2 hours

---


---

## Exercise 1 – Associate Contract Workers with a Subcontract Line

**Scenario:**  
You’ve already created a subcontract for *Contoso Consulting Services*. You now need to associate their contract workers to specific project roles to allow time entry and costing.

### Tasks
1. Navigate to Purchasing > Vendor.
2. Create a new vendor
3. Navigate to **Purchasing > Subcontracts**.
4. Create a new **Contoso Implementation Support** subcontract and complete the compulsory fields.
5. On the **Subcontract Lines** tab, select the **Time** line for “Consultant" and complete necessary fields as needed.
6. Go to **Subcontract Line Resources** > **+ New Resource**.
7. Select:
   - **Bookable Resource:** Select an existing resource
   - **Type of Worker:** Contract Worker
   - **Vendor:** Contoso Consulting Services
   - **Start/End Dates:** Cover project duration.
   - **Effort:** 160 hours
8. Save and close.

**Expected Result:**  
The resource is linked as a subcontracted consultant and available for staffing and time entry.

---

## Exercise 2 – Subcontract a Project Team Member

**Scenario:**  
You have a generic team member (Consultant) on your project. You’ll now link this team member to your subcontract.

### Tasks
1. Navigate to **Projects > Implementation Project > Team Members.**
2. Select the **Consultant (Generic)** role.
3. In the **Subcontract** field, select **Contoso Implementation Support.**
4. In **Subcontract Line**, choose **Consultant – Time Line.**
5. Save your changes.

**Expected Result:**  
The generic team member is now subcontracted. The Worker Type is set to **Contract Worker**, and cost rates are updated using the **Purchase Price List** on the subcontract.

---

## Exercise 3 – Estimate Costs for Subcontracted Assignments

**Scenario:**  
You need to ensure that subcontracted resources are costed correctly using the purchase price list linked to the subcontract.

### Tasks
1. Go to **Projects > Implementation Project > Estimates Tab.**
2. Select **Update Prices**.
3. Review cost estimation for:
   - Role = Consultant
   - Resource = Select the previous resource (contractor)
4. Confirm that cost rates reflect vendor purchase prices, not internal employee rates.

**Expected Result:**  
Project cost estimates are recalculated using subcontract purchase pricing rules.

---

## Exercise 4 – Configure Schedule Board for Contract Workers

### Tasks
1. Navigate to **Projects > Schedule Board > Settings.**
2. On the **General Tab**, set:
   - **Filter Layout:** Default Filter Layout for Project Operations Core
   - **Retrieve Resources Query:** Default Retrieve Resources Query for Project Operations Core
3. Save settings.
4. Return to the Schedule Board.
5. In the Filter Pane, add:
   - **Worker Type:** Contract Worker
   - **Vendor:** Contoso Consulting Services
   - **Subcontract Line:** Consultant (Time)

**Expected Result:**  
Contract workers from the vendor are visible on the Schedule Board for resource booking.

---

## Exercise 5 – Book Contract Worker to Project

### Tasks
1. From the Schedule Board, filter for **Vendor = Contoso Consulting Services.**
2. Select **Alex Wilber** and book him to the **Implementation Project.**
3. Review:
   - Booking Dates align with subcontract line.
   - Effort booked = 160 hours.
4. Return to the project and confirm the booking appears under **Team Members.**

**Expected Result:**  
The subcontracted resource is booked on the project and can record time entries.

---

## Exercise 6 – Record Subcontractor Time

### Tasks
1. Sign in as **Resource (Contract Worker).**
2. Navigate to **Time Entries > + New.**
3. Enter:
   - **Project:** Implementation Project
   - **Subcontract:** Contoso Implementation Support
   - **Subcontract Line:** Consultant (Time)
   - **Hours:** 8
   - **Date:** Today
4. Submit the entry for approval.

**Expected Result:**  
Time entry is recorded against subcontract line and pending approval by Project Manager.

---

## Exercise 7 – Create Vendor Invoice from Subcontract

### Tasks
1. Sign back in as Project Manager.
2. Navigate to **Project Operations > Subcontracts.**
3. Open the subcontract and select **Create Vendor Invoice.**
4. Verify auto-populated header fields:
   - Vendor: Contoso Consulting Services
   - Contracting Unit: North America Delivery
   - Currency: USD
   - Payment Terms: Net 30
5. Confirm **Invoice Status = Draft.**

**Expected Result:**  
A vendor invoice is created from the subcontract with appropriate defaults.

---

## Exercise 8 – Add and Verify Vendor Invoice Lines

### Tasks
1. On the Vendor Invoice record, add lines as follows:
   - **Line 1:**
     - Transaction Class: Time
     - Subcontract Line: Consultant (Time)
     - Quantity: 8 hours
     - Unit Price: 125 USD
   - **Line 2:**
     - Transaction Class: Expense
     - Subcontract Line: Travel (Expense)
     - Quantity: 1
     - Unit Price: 1,000 USD
2. Save the invoice.
3. Verify total and tax calculations.

**Expected Result:**  
Vendor invoice lines accurately reflect subcontractor time and expense entries.

---

## Exercise 9 – Match and Verify Vendor Invoice

### Tasks
1. Select the **Verify** option on the invoice.
2. Confirm the system matches:
   - Subcontract Lines
   - Vendor Invoice Lines
   - Project Actuals
3. Once verified, set invoice **Status = Ready for Payment.**

**Expected Result:**  
Vendor invoice verified successfully. Project costs are reversed and recreated based on vendor invoice values.

---

## Exercise 10 – Review Updated Project Costs

### Tasks
1. Navigate to **Project > Implementation Project > Actuals Tab.**
2. Observe:
   - Time and Expense actuals now reflect vendor invoice-based costs.
   - Cost Rate aligns with subcontract purchase prices.
3. Confirm financial accuracy.

**Expected Result:**  
All subcontract-related actuals are posted at the correct vendor rates.

---

## Exercise 11 – Close Subcontract

### Tasks
1. Return to **Project Operations > Subcontracts.**
2. Open the Contoso subcontract.
3. Change **Status Reason** to **Closed.**
4. Verify that:
   - Subcontract lines are locked.
   - Vendor invoice processing is complete.
   - No new time or expense entries can reference the subcontract.

**Expected Result:**  
Subcontract is successfully closed and all related financials finalized.

---

## Lab Summary
In this lab, you:
- Linked contract workers and project team members to a subcontract.
- Configured cost estimation using purchase price lists.
- Created and verified vendor invoices.
- Matched invoice lines to subcontract and project actuals.
- Closed the subcontract to complete the delivery cycle.

You’ve now completed the end-to-end subcontractor and vendor invoicing process in D365 Project Operations.
