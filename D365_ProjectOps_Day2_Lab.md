
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
1. Navigate to **Project Operations → Price Lists**.  
2. Select **New** and create a Cost Price List:
   - **Name:** Fabrikam India Cost Rates FY25  
   - **Context:** Cost  
   - **Currency:** INR  
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
3. Under **Default Cost Price List**, select *Fabrikam India Cost Rates FY25*.  
4. Save changes.  
5. Repeat for **Fabrikam Philippines** linking its own cost list.  

### Validation
- Each contracting unit has a default cost price list.  
- Ensure no overlapping effective dates exist.

---

## Exercise 5: Validate Pricing in a Project
**Objective:** Confirm correct bill and cost rates apply to time entries.

### Steps:
1. Navigate to **Projects → Active Projects**.  
2. Create a new project:
   - **Name:** Global Implementation FY25  
   - **Customer:** Contoso Ltd  
   - **Contracting Unit:** Fabrikam US  
3. Assign **Resources**:
   - Developer (India)
   - Consultant (Philippines)
4. Navigate to **Estimates → Effort and Cost** tab.  
5. Add 8 hours of time for each role.  
6. Review the automatically applied:
   - **Cost Rate** from the Cost Price List  
   - **Bill Rate** from the Sales Price List  

### Validation
| Role | Source Unit | Cost Rate | Bill Rate | Method |
|------|--------------|------------|------------|---------|
| Developer | India | ₹100/hr (converted) | $150/hr | Price per Unit |
| Consultant | Philippines | $90/hr | $110/hr | Markup over cost |

---

## Exercise 6: Apply a Markup Over Cost
**Objective:** Demonstrate use of markup-based pricing.

### Steps:
1. In **Fabrikam US Bill Rates FY25**, open the **Developer (India)** role line.  
2. Change **Pricing Method** to *Markup over cost (%)*.  
3. Set **Percent = 10%**.  
4. Save and refresh.  
5. Return to your project and create a new time entry for Developer (India).  

### Validation
- Bill rate should automatically reflect cost × 1.10 (10% markup).  
- Example: ₹100 cost → $110 bill rate (after conversion).

---

## Exercise 7: Reporting & Review
**Objective:** Review pricing data and ensure accuracy.

### Steps:
1. Open your project → **Actuals** tab.  
2. Filter by **Resource** to confirm each role’s rates.  
3. Check **Project Invoice Estimate** to validate total billed amount.  
4. Export report to Excel if required.

### Expected Result
- Labor rates apply correctly by Role + Resourcing Unit.  
- Cost and Bill rates reflect correct price lists and methods.

---

## Lab Summary
In this lab, you:
- Created **Sales** and **Cost** price lists for Fabrikam divisions.  
- Enabled **Cost Plus Pricing**.  
- Configured **Transfer Pricing** across organizational units.  
- Validated **automatic rate determination** during time entry.  

✅ You have successfully configured **Labor Pricing and Costing** in D365 Project Operations.
