
# LAB [MB-OPS] Day 4 – Project Budgeting and Resource Management

**Estimated Time:** 120 minutes  

---

## **Lab Scenario**

You are a **Project Manager** at *Contoso Consulting Group*. Your organization has just started implementing Dynamics 365 Project Operations to improve visibility into project budgets and resource utilization.  

Your task is to create a new project, plan a complete cost and sales budget, and then allocate resources based on defined requirements. You will explore both **budgeting** and **resource management** features, perform time phasing, and simulate variance tracking.

By the end of the lab, you will have a working example of how to manage financial and human resources from start to finish in Project Operations.

---

## **Learning Objectives**

After completing this lab, you will be able to:

1. Create and configure project budgets (cost and sales).  
2. Generate a project budget from estimates and apply time-phasing.  
3. Define budget periods and analyze variances.  
4. Create resource requirements and submit requests for fulfillment.  
5. Use the Schedule Assistant to find and assign the right resource.  
6. Perform reconciliation and substitution of project resources.

---

## **Lab Setup / Prerequisites**

- Access to **Dynamics 365 Project Operations (Lite Deployment)** or **Unified Operations Trial Environment**.  
- A user account with **Project Manager** and **Resource Manager** roles.  
- Sample data pack (optional) for Contoso Consulting projects.  
- Browser: Microsoft Edge or Chrome.  
- Ensure **Project Budgeting Feature Flag** is enabled in:  
  `Settings → Parameters → Feature Control`.

---

## **Exercise 1 – Create and Configure a Project Budget**

**Estimated Time:** 30 minutes  

### **Scenario**
You’ll create a new project, define a cost and sales budget, and prepare the data for forecasting.

### **Steps**

1. Navigate to **Projects → My Projects → New Project**.  
2. Name the project **“Contoso Data Migration”** and set the contract type to **Time and Material**.  
3. Save the project and open the **Budget tab**.  
4. Select **Create Budget → Manual**.  
5. In the **Context** field, select **Cost**.  
6. Add three budget lines:  
   - *Time*: Consultant – 200 hours @ $100/hour.  
   - *Material*: Software Licenses – $5,000.  
   - *Expense*: Travel – $2,000 + 10% contingency.  
7. Review the total estimated cost.  
8. Click **Submit for Approval**.  
9. After approval, note that the status changes to **Approved**.  

### **Validation**
- Verify one cost budget exists for the project.  
- Confirm all budget lines appear with correct amounts and contingencies.  

---

## **Exercise 2 – Generate a Budget from Estimates and Apply Time Phasing**

**Estimated Time:** 20 minutes  

### **Scenario**
You’ll create a second version of the budget using project estimates and distribute it across a monthly period.

### **Steps**

1. On the same project, select **Revise Budget**.  
2. Choose **Create Budget from Estimates**.  
3. Select **Time Source = Project Team Members**.  
4. Enter **Contingency = 5 %** for Time, Material, and Expense lines.  
5. In the import summary, confirm all lines were imported successfully.  
6. Navigate to **Project Parameters → Budget Periods** and set:  
   - Fiscal Start = January.  
   - Interval = Monthly.  
   - Year = Current Year.  
7. Return to the budget and enable **Time Phasing**.  
8. Save and submit the revised budget.  

### **Validation**
- Confirm monthly breakdowns appear under **Budget Line Details**.  
- Status = Approved and phasing is active.

---

## **Exercise 3 – Analyze Variance Between Forecast and Actuals**

**Estimated Time:** 15 minutes  

### **Scenario**
You will simulate actual transactions and analyze the resulting variance.

### **Steps**

1. Navigate to **Actuals → Project Transactions → New**.  
2. Enter a Time transaction: Consultant – 10 hours @ $100/hour.  
3. Post the transaction.  
4. Return to the project and open the budget.  
5. Select **Reevaluate Budget Association**.  
6. View the **Variance** column on each budget line.  

### **Validation**
- Variance displays as **Actual – Forecast** for the Time line.  
- All actuals are linked to budget lines automatically.

---

## **Exercise 4 – Create and Submit Resource Requirements**

**Estimated Time:** 20 minutes  

### **Scenario**
Now that financials are established, you’ll staff the project with available resources.

### **Steps**

1. Go to **Project Team → Add Generic Resource**.  
2. Add a resource named **Generic Consultant** with role = Consultant.  
3. Click **Generate Resource Requirements**.  
4. Open the new requirement record.  
5. Define details:  
   - Start Date = Project Start Date.  
   - End Date = +30 Days.  
   - Effort = 160 hours.  
6. Save and submit the requirement.  
7. Observe status changes from Draft → Submitted.  

### **Validation**
- Requirement record shows submitted status with linked project details.

---

## **Exercise 5 – Fulfill and Approve Resource Requests**

**Estimated Time:** 25 minutes  

### **Scenario**
You’ll act as Resource Manager to locate a qualified consultant and then approve the assignment as Project Manager.

### **Steps (Resource Manager Role)**

1. Open **Resource Requests → Needs Review**.  
2. Launch the **Schedule Assistant**.  
3. Apply filters: Role = Consultant, Location = US, Availability = Full.  
4. Review suggested resources and select **Alex Wilber**.  
5. Click **Propose Resource** and submit.  

### **Steps (Project Manager Role)**

6. Return to the project → Resource Requests tab.  
7. Review proposal and click **Accept Proposal**.  
8. The generic resource is automatically replaced with Alex Wilber.  

### **Validation**
- Resource request status = **Fulfilled**.  
- Team member grid shows assigned resource with booked hours.

---

## **Exercise 6 – Perform Reconciliation and Substitution**

**Estimated Time:** 10 minutes  

### **Scenario**
You’ll reconcile assignments and substitute a resource.

### **Steps**

1. Navigate to **Resource Management → Reconciliation View**.  
2. Compare bookings vs assignments.  
3. Identify a resource with unmatched assignment.  
4. Select **Substitute Resource** and launch the Schedule Assistant.  
5. Choose a replacement resource and confirm the substitution.  

### **Validation**
- The Reconciliation View shows no unmatched records.  
- Updated bookings reflect new resource.

---

## **Knowledge Check**

1. What is the difference between a booking and an assignment?  
→ Bookings reserve capacity; assignments define specific tasks.  

2. Which budget statuses allow editing?  
→ Draft and Rejected.  

3. How does the Schedule Assistant improve staffing decisions?  
→ It ranks resources based on availability, skills, and costs.  

4. What is variance in a project budget?  
→ The difference between actual and forecast values.  

---

## **Expected Results**

After completing the lab:
- You created both cost and sales budgets for a project.  
- Applied time-phased distribution and verified variance calculations.  
- Created, submitted, and fulfilled a resource requirement.  
- Used the Schedule Assistant for AI-based resource selection.  
- Reconciled and substituted resources to resolve capacity issues.  

The project is now fully budgeted, resourced, and financially traceable.

---

✅ **Lab Complete – Day 4 (Project Budgeting & Resource Management)**
