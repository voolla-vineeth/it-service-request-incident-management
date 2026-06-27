# ServiceNow Scripts Repository

## 1. Priority Calculation Client Script

### Purpose

Automatically calculate Priority based on Impact and Urgency without saving the record.

### Type

onChange Client Script

### Fields

- Impact
- Urgency

### Script

```javascript
function onChange(control, oldValue, newValue, isLoading) {

    if (isLoading || newValue === '') {
        return;
    }

    var impact = g_form.getValue('impact');
    var urgency = g_form.getValue('urgency');

    if (impact == 'high' && urgency == 'high') {
        g_form.setValue('priority', 'critical');
    }
    else if (impact == 'high' && urgency == 'medium') {
        g_form.setValue('priority', 'high');
    }
    else if (impact == 'high' && urgency == 'low') {
        g_form.setValue('priority', 'moderate');
    }
    else if (impact == 'medium' && urgency == 'medium') {
        g_form.setValue('priority', 'moderate');
    }
    else if (impact == 'medium' && urgency == 'low') {
        g_form.setValue('priority', 'low');
    }
    else if (impact == 'low' && urgency == 'low') {
        g_form.setValue('priority', 'planning');
    }
}
```

### Explanation

- Triggered when Impact or Urgency changes.
- Reads Impact and Urgency values.
- Calculates Priority automatically.
- Updates Priority field instantly.

---

## 2. Auto Assignment Business Rule

### Purpose

Automatically assign Assignment Group based on Ticket Type.

### Type

Before Insert

### Script

```javascript
(function executeRule(current, previous) {

    if (current.ticket_type == 'Incident') {
        current.assignment_group = '2156c3a80b982300cac6c08393673a7e';
    }

    else if (current.ticket_type == 'Service Request') {
        current.assignment_group = '2156c3a80b982300cac6c08393673a7e';
    }

})(current, previous);
```

### Explanation

- Executes before record creation.
- Checks Ticket Type.
- Assigns support group automatically.
- Removes manual assignment effort.

---

## 3. Resolution Notes UI Policy

### Purpose

Force users to enter Resolution Notes before ticket closure.

### Configuration

Condition:

State = Closed

Actions:

- Resolution Notes = Mandatory

### Explanation

- Ensures tickets contain closure details.
- Prevents incomplete ticket resolution.

---

## 4. Email Notification Flow

### Purpose

Send automatic email when ticket is created.

### Trigger

Record Created

### Table

IT Ticket

### Email Fields

- Ticket Number
- Ticket Type
- Short Description
- State

### Explanation

- Runs automatically after ticket creation.
- Notifies Requested By user.
- Improves communication and transparency.

---

## Lessons Learned

### Client Scripts

Used for:

- Form level automation
- Immediate user feedback
- Dynamic field updates

### Business Rules

Used for:

- Server side processing
- Data validation
- Automatic field population

### Flow Designer

Used for:

- Workflow automation
- Email notifications
- Event driven actions

### UI Policies

Used for:

- Dynamic field control
- Mandatory fields
- Better user experience
