# 🎓 Capstone Project: Dynamics 365 Project Operations Implementation

## **Scenario Overview**
You have been hired as a **Dynamics 365 Project Operations Consultant** by **Contoso Engineering Services (CES)**, a mid-sized professional services firm specializing in **civil engineering and infrastructure design**.  
CES wants to implement **Dynamics 365 Project Operations** to streamline their **project sales, planning, resource management, and billing processes**.

Your task is to design and configure a **functional system prototype** in D365 Project Operations that supports CES’s business processes from **lead to cash**.

---

## **Business Background**

**Company:** Contoso Engineering Services (CES)  
**Industry:** Civil Engineering / Professional Services  
**Headquarters:** Chicago, Illinois  
**Employees:** 250  
**Departments:** Sales, Projects, Resource Management, Finance, HR  

### **Current Challenges**
- Manual tracking of project milestones and budgets.  
- Inconsistent quoting and billing for project-based work.  
- Difficulty forecasting resource utilization.  
- Delays between project delivery and invoicing.

---

## **Project Objectives**
1. Implement Dynamics 365 Project Operations from **sales to billing**.  
2. Configure **project contracts, quotes, price lists, and resource management**.  
3. Set up **timesheets, approvals, and invoice generation**.  
4. Simulate **reporting and performance tracking**.

---

## **Project Requirements and Data**

### **1. Organizational Setup**
| Business Unit | Description | Contracting Unit | Resourcing Unit |
|----------------|-------------|------------------|----------------|
| Contoso HQ | Main business unit for US operations | Yes | Yes |
| Contoso Canada | Sub-unit for Canadian operations | Yes | Yes |

---

### **2. Project Price List**
| Price List | Currency | Valid From | Valid To |
|-------------|-----------|-------------|-----------|
| Engineering Services 2025 | USD | 01/01/2025 | 12/31/2025 |

| Role | Cost Rate | Bill Rate |
|------|------------|------------|
| Project Manager | $75/hr | $150/hr |
| Civil Engineer | $60/hr | $120/hr |
| Drafter | $40/hr | $80/hr |
| QA Analyst | $50/hr | $100/hr |

---

### **3. Sample Customer Data**
| Customer Name | Industry | Country | Primary Contact |
|----------------|-----------|----------|----------------|
| Northwind Developers | Real Estate | USA | Henry Adams |
| Maple City Construction | Construction | Canada | Sarah Green |

---

### **4. Sample Project Data**
| Project Name | Customer | Project Type | Start Date | End Date | Budget (USD) |
|---------------|-----------|---------------|-------------|-----------|--------------|
| Downtown Bridge Design | Northwind Developers | Time and Material | 01/20/2025 | 05/30/2025 | 250,000 |
| Suburban Road Expansion | Maple City Construction | Fixed Price | 02/15/2025 | 08/31/2025 | 400,000 |

---

### **5. Resources**
| Resource Name | Role | Skills | Location | Availability |
|----------------|------|--------|-----------|--------------|
| John Miller | Project Manager | PMP, MS Project | Chicago | Full-time |
| Alicia Kim | Civil Engineer | AutoCAD, Bridge Design | Toronto | 50% |
| Mark Spencer | Drafter | CAD, Revit | Chicago | Full-time |
| Diana Lopez | QA Analyst | QA/QC | Remote | Full-time |

---

## **Implementation Phases**

### **Phase 1 – Environment Setup**
- Create Org Unit, and Users.  
- Configure Contracting and Resourcing Units.  
- Assign Security Roles (Project Manager, Salesperson, Resource Manager).

### **Phase 2 – Sales and Project Contract Setup**
- Create **Customer** accounts.  
- Build **Project Quotes** using price lists.  
- Convert quotes to **Project Contracts**.  
- Link contract lines with **Projects and Tasks**.

### **Phase 3 – Project Planning**
- Create **Projects** for both customers.  
- Add a **Work Breakdown Structure (WBS)** with at least 3 phases:  
  1. Planning  
  2. Execution  
  3. QA/Delivery  
- Assign resources and allocate hours.

### **Phase 4 – Resource Management**
- Configure **Bookable Resources** and **Skills**.  
- Use the **Resource Scheduling Board** for allocation.  

### **Phase 5 – Time and Expense Entry**
- Enable **Timesheet Approvals**.  
- Submit and approve timesheets.  
- Record **expenses** (travel, materials, etc.).

### **Phase 6 – Billing and Invoicing**
- Generate **Invoice Proposals** from actuals.  
- Review, correct, and post invoices.  
- Export invoices.

### **Phase 7 – Reporting**
-Review dashboards for **Budget vs Actuals**, **Utilization**, and **Profitability**.

---

## **Evaluation Criteria**

| Category | Weight | Description |
|-----------|--------|-------------|
| System Setup & Configuration | 20% | Correct setup of entities, price lists, and users |
| Project Planning | 20% | Proper WBS and scheduling |
| Resource Management | 15% | Correct allocation and utilization |
| Time & Expense | 15% | Complete timesheet/expense flow |
| Billing & Invoicing | 20% | Accurate invoice process |
| Reporting | 10% | Clear, functional dashboards |

---

## **Submission Requirements**
- Walkthrough** of setup.  
- Demo presentation  
- Provide **sample invoice(s)** and **project report(s)**.

---

## **Bonus Challenge**
  

