# servicenow-it-asset-access-and-support-request-management
End-to-end ServiceNow IT Asset Access &amp; Support Request Management solution built using low-code/no-code features such as Service Catalog, Custom Tables, Import Sets, Flow Designer, Data Policies, Reference Qualifiers, and Dependent Fields — fully implementable in a ServiceNow PDI without scripting.

# IT Asset Access & Support Request Management – ServiceNow

## 📌 Project Overview
This project demonstrates a **real-time enterprise ServiceNow implementation** for managing **IT Asset Access and Support Requests** using **configuration-only (no scripting)** best practices.

The solution is designed to be:
- Interview-ready (CSA / CAD aligned)
- Easily implementable in a ServiceNow PDI
- Fully configuration-driven (low-code governance)

---

## 🎯 Business Requirement
Organizations need a **single standardized request process** where:
- Employees can request IT asset access or support
- Requests are automatically routed to the correct support teams
- SLAs are applied based on priority
- Mandatory rules are enforced even during imports
- Bulk legacy requests can be uploaded
- No scripting is allowed

---

## 🧩 Features Used

| Feature | Implementation |
|------|----------------|
| User Administration | Users, Roles, Groups |
| Custom Table | `u_it_access_request` |
| Service Catalog | IT Asset / Access Request |
| Variables & UI Policies | Dynamic behavior |
| Dependent Fields | Category → Subcategory |
| Reference Qualifiers | Active Applications only |
| Flow Designer | Auto-assignment |
| Import Set | Bulk data upload |
| Data Policy | Server-side validation |
| ❌ Scripting | Not used |

---

## 👥 User & Group Setup

### Users
- IT Asset Team Lead (itil)
- Network Support Agent (itil)
- Application Support Agent (itil)
- Employee User (ess)

### Groups
- IT Asset Support
- Network Support
- Application Support

---

## 🗂️ Custom Table

**Table Name:** `u_it_access_request`

| Field | Type |
|------|----|
| Request Number | Auto-number |
| Requested For | Reference → User |
| Request Type | Choice |
| Category | Choice |
| Subcategory | Choice (Dependent) |
| Asset / Application | Reference |
| Priority | Choice |
| State | Choice |
| Assignment Group | Reference → sys_user_group |

---

## 🔗 Dependent Fields
**Category → Subcategory**

| Category | Subcategory |
|--------|-------------|
| Hardware | Laptop, Desktop |
| Network | VPN, WiFi |
| Application | Email, HRMS |

Configured using **Dependent Choice Lists** (no scripts).

---

## 🔍 Reference Qualifier
**Requirement:** Show only active applications.

Reference Qualifier used:
active=true


Ensures users can select only valid, active records.

---

## 🛒 Service Catalog
**Catalog Item:** IT Asset / Access Request

Variables:
- Request Type
- Category
- Subcategory (dynamic via UI Policies)
- Asset / Application
- Priority

Catalog UI Policies control visibility and mandatory behavior.

---

## 🔄 Auto Assignment (Flow Designer)
Requests are automatically assigned based on Category:

| Category | Assignment Group |
|--------|------------------|
| Network | Network Support |
| Application | Application Support |
| Hardware | IT Asset Support |

Implemented using **Flow Designer (no scripting)**.

---

## 📥 Import Set
Supports bulk upload of legacy requests.

### Sample CSV
requested_for,request_type,category,subcategory,priority
john.doe,New Access,Network,VPN,2
jane.smith,Support,Application,Email,3
raj.kumar,New Access,Hardware,Laptop,1

---

## ✅ Data Policy
- Priority is mandatory
- Enforced for UI, Import Sets, and APIs
- Ensures data integrity

---

## 🔁 End-to-End Flow
1. Employee submits request via Service Catalog
2. Dependent fields guide correct inputs
3. Reference qualifier filters valid data
4. Flow auto-assigns request
5. SLA starts automatically
6. Agents resolve and close request
7. Import Set supports bulk creation

---

## 🎓 Interview Value
This project demonstrates:
- Strong ServiceNow fundamentals
- Real-world enterprise design
- CSA & CAD exam alignment
- Low-code / no-code best practices

---

## 🚀 How to Use
- Import into your ServiceNow PDI
- Follow the setup steps in order
- Test via Service Catalog and Import Sets

---

## 📎 Author
**Swati Balla ServiceNow Administrator / Developer**  
3+ Years Experience  

