# 💻 Laptop Request Catalog Item – ServiceNow Project

## 📘 Overview
The **Laptop Request Catalog Item** project is developed on the **ServiceNow** platform to provide employees with an easy, efficient, and automated way to request laptops through the **Service Catalog**.  
This solution replaces the traditional manual request process with a dynamic form that ensures accurate data collection, improves workflow visibility, and enhances user experience.

---

## 🧩 Problem Statement
Employees often face delays and confusion while requesting laptops through manual or email-based processes.  
The existing system lacks:
- Dynamic field behavior  
- Real-time form validation  
- Clear instructions and reset options  

This leads to errors, incomplete submissions, and longer turnaround times.  
Hence, an automated catalog-based solution is needed to simplify the process.

---

## 🚀 Proposed Solution
The project introduces a **ServiceNow Catalog Item** titled **“Laptop Request”**, designed under the **Hardware Category** in the Service Catalog.  
It allows employees to submit structured and guided laptop requests through dynamic form fields.

### 🔧 Key Features:
- **Dynamic Form Behavior:** Fields like *Accessories Details* appear only when the *Additional Accessories* checkbox is selected.  
- **Reset Form Action:** A *UI Action* script adds a button to clear all form inputs instantly.  
- **Governance via Update Sets:** All configurations are tracked through update sets for deployment between instances.  
- **User-Friendly Interface:** Provides clear instructions and structured variables for accurate data entry.  
- **Reusability & Scalability:** Can be extended for other IT asset requests such as desktops or mobile devices.

---

## 🧱 Components Used
| Component | Description |
|------------|-------------|
| **Catalog Item** | “Laptop Request” created under Hardware category |
| **Variables** | Laptop Model, Justification, Additional Accessories, Accessories Details |
| **Catalog UI Policy** | Controls field visibility dynamically |
| **UI Action (Client Script)** | Implements “Reset Form” functionality |
| **Update Set** | Used for tracking and migrating configuration |
| **ServiceNow Cloud Platform** | Backend and hosting environment |

---

## ⚙️ Implementation Steps
1. Create and activate an update set named **Laptop Request Project**.  
2. Navigate to **Service Catalog → Maintain Items → New** and create the catalog item.  
3. Add variables:
   - Laptop Model (Single Line Text)
   - Justification (Multi Line Text)
   - Additional Accessories (Checkbox)
   - Accessories Details (Multi Line Text)
4. Create a **Catalog UI Policy**:
   - Condition: *Additional Accessories* is *true*
   - Action: Show and make *Accessories Details* mandatory
5. Create a **UI Action (Client Script)** for Reset:
   ```javascript
   function resetForm() {
       g_form.clearForm();
       alert("The form has been reset.");
   }
