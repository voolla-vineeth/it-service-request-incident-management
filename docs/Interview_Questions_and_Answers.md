# Interview Questions and Answers

## Project-Based Questions

### Q1. Explain your ServiceNow project.

**Answer:**

I developed a custom ServiceNow application called **IT Service Request & Incident Management** using App Engine Studio.

The application allows users to create Incident and Service Request tickets. I implemented custom tables, form design, UI Policies, Client Scripts, Business Rules, Assignment Group automation, and Flow Designer email notifications.

The application automatically calculates priority based on Impact and Urgency and routes tickets to appropriate support groups.

---

### Q2. Why did you create a custom table instead of using the Incident table?

**Answer:**

This was a learning and portfolio project. Creating a custom table helped me understand data modeling, field configuration, Business Rules, Client Scripts, and Flow Designer without modifying out-of-box Incident functionality.

---

### Q3. What Business Rules did you create?

**Answer:**

1. Priority Calculation Business Rule
2. Assignment Group Routing Business Rule
3. Resolution Note Validation Business Rule

Purpose:

* Automate processing
* Enforce data integrity
* Reduce manual effort

---

### Q4. What Client Script did you create?

**Answer:**

I created an onChange Client Script on Impact and Urgency fields. Whenever the user changes either field, the script automatically calculates Priority and updates the form without requiring a save.

---

### Q5. Why use both Client Script and Business Rule for Priority?

**Answer:**

Client Script provides immediate user feedback.

Business Rule ensures server-side enforcement and data integrity for records created through imports, APIs, integrations, or background scripts.

---

### Q6. Difference between Client Script and Business Rule?

| Client Script         | Business Rule       |
| --------------------- | ------------------- |
| Client Side           | Server Side         |
| Runs in Browser       | Runs on Server      |
| Immediate UI Feedback | Data Integrity      |
| Uses g_form           | Uses current object |

---

### Q7. What is a UI Policy?

**Answer:**

UI Policy dynamically changes form behavior without scripting.

In my project, I made Resolution Note mandatory when State is set to Resolved.

---

### Q8. Why did you also create a Business Rule for Resolution Notes?

**Answer:**

UI Policies only work on forms and can be bypassed through integrations or imports.

The Business Rule ensures Resolution Notes are always enforced at the server level.

---

### Q9. Explain the Flow Designer implementation.

**Answer:**

I created a Flow that triggers when a new IT Ticket is created.

The Flow sends an email notification to the requester containing ticket details such as Number, Ticket Type, Short Description, and State.

---

### Q10. What is Impact?

**Answer:**

Impact measures the extent of business disruption caused by an issue.

Examples:

* Entire company affected = High Impact
* Single user affected = Low Impact

---

### Q11. What is Urgency?

**Answer:**

Urgency measures how quickly the issue needs to be resolved.

Examples:

* Payroll system down before salary processing = High Urgency
* Minor cosmetic issue = Low Urgency

---

### Q12. How is Priority determined?

**Answer:**

Priority is derived using an Impact and Urgency matrix.

| Impact | Urgency | Priority |
| ------ | ------- | -------- |
| High   | High    | Critical |
| High   | Medium  | High     |
| Medium | Medium  | Moderate |
| Low    | Low     | Low      |

---

### Q13. What is the purpose of Assignment Groups?

**Answer:**

Assignment Groups help route tickets to the correct support teams.

Examples:

* Service Desk
* Application Support
* Network Team
* Database Team

This ensures tickets are handled by the appropriate team.

---

### Q14. What automation did you implement in your project?

**Answer:**

I implemented:

* Automatic Priority Calculation
* Automatic Assignment Group Routing
* Resolution Note Validation
* Email Notification Flow

These automations reduce manual effort and improve consistency.

---

### Q15. What ServiceNow components did you use?

**Answer:**

* App Engine Studio
* Custom Tables
* Form Designer
* UI Policies
* Client Scripts
* Business Rules
* Flow Designer
* Email Notifications
* Reference Fields
* Choice Lists
