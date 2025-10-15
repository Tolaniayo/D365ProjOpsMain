# LAB [D365PO] M04Lab01 – Creating and Managing Projects after a Project Contract is Active

## Lab Overview
In this lab, you will learn how to create, review, and manage projects within **Dynamics 365 Project Operations** once the project contract is active. You will explore project components such as tasks, timelines, boards, resources, estimates, and sales information.

**Time to complete:** 2 hours  
**Lab type:** Hands-on  
**Module:** Project Management and Operations  

---

## Lab Objectives
After completing this lab, you will be able to:

- Create a new project linked to an active project contract.  
- Understand the structure and purpose of a project in D365 Project Operations.  
- Work with the *Project for the Web* interface — including grids, boards, and timelines.  
- Manage project resources and assignments.  
- Review cost, sales, and tracking data to monitor project performance.  
- Understand the built-in business process flow for projects.  

---

## Lab Prerequisites
- Access to a Dynamics 365 Project Operations environment.  
- An active project contract created from a previous module (e.g., “Module 3 – Creating a Project Contract”).  
- Basic understanding of the Project Management workspace in D365.  

---

## Exercise 1 – Create a New Project

### Task 1: Open and Review the Project Contract
1. Sign in to **Dynamics 365 Project Operations**.  
2. Go to **Project Contracts** → select the contract created in the previous module (e.g., *Contoso Implementation Contract*).  
3. Ensure the contract is **Activated**.  
4. Review the order lines — you should see both a **Fixed Price** and a **Time & Material** line.

---

### Task 2: Create a New Project
1. From the command bar, select **+ New Project**.  
2. Enter the following details:

   | Field | Value |
   |--------|--------|
   | **Project Name** | Contoso Implementation Project |
   | **Description** | Enter a description |
   | **Project Manager** | Automatically populated (your user) |


3. Save the project record.  


---

## Exercise 2 – Define Tasks and Work Breakdown

### Task 1: Add Tasks Using the Grid View
1. Navigate to the **Tasks** tab.  
2. In the **Grid View**, select **Add Task** and create the following sample tasks:

   | Task Name | Duration (Days) | Start Date | Finish Date | Effort (Hours) |
   |------------|----------------|-------------|--------------|----------------|
   | Planning and Kickoff | 3 | [Today’s Date] | +3 days | 12 |
   | Requirements Iteration | 5 | +4 days | +9 days | 20 |
   | Build Phase | 10 | +10 days | +20 days | 40 |

3. Assign each task to a **Generic Resource** (e.g., *Consultant* or *Developer*).  
4. Add columns such as **Effort Remaining**, **Effort at Completion**, and **% Complete** to the grid.

---

### Task 2: Organize Tasks into Buckets
1. Switch to **Board View**.  
2. Create two buckets:
   - **Fixed Price Phase**  
   - **Time & Material Phase**  
3. Drag tasks into the appropriate buckets.  
4. Add a new bucket if needed, e.g., **QA Phase**.

---

### Task 3: Set Dependencies Using Timeline View
1. Switch to **Timeline View (Gantt chart)**.  
2. Review all tasks and visually check dependencies.  
3. Create a dependency between:
   - *Planning and Kickoff* → *Requirements Iteration*  
   - *Requirements Iteration* → *Build Phase*  
4. Open task details from the right panel and add notes or modify duration.  

---

## Exercise 3 – Manage Project Resources

### Task 1: Review the Project Team
1. Navigate to the **Team** tab.  
2. Review existing **Generic Resources** (Consulatants, QA, PM).  
3. Add yourself as a **Project Manager** if not already listed.
4. Add more employee as team members  

---

### Task 2: View Resource Assignments
1. Go to the **Resource Assignments** tab.  
2. Change the view to **Group by Role**.  
3. Observe the total effort allocated per role.  

---

## Exercise 4 – Analyze Estimates and Financials



## Knowledge Check
1. What is the purpose of a **Generic Resource** in a project?  
2. How does the **Grid View** differ from the **Board View**?  
3. What are the key financial metrics visible under the **Estimates** tab?  
4. Where can you find task dependencies in a project?  
 

---

## Completion
🎉 **Congratulations!**  
You’ve successfully created and managed a project in **Dynamics 365 Project Operations** after activating its project contract. You now understand how to manage tasks, resources, and estimates, and how to monitor progress using Project for the Web tools.
