# Test Cases

## Project
IT Service Request & Incident Management

---

## TC001 - Create Incident Ticket

### Objective
Verify user can create Incident Ticket.

### Steps

1. Open IT Ticket form.
2. Select Ticket Type = Incident.
3. Enter Short Description.
4. Submit record.

### Expected Result

Incident ticket created successfully.

### Status

Pass

---

## TC002 - Create Service Request

### Objective
Verify user can create Service Request.

### Steps

1. Open IT Ticket form.
2. Select Ticket Type = Service Request.
3. Enter Short Description.
4. Submit record.

### Expected Result

Service Request created successfully.

### Status

Pass

---

## TC003 - Auto Assignment Group

### Objective

Verify assignment group populates automatically.

### Steps

1. Create ticket.
2. Select Ticket Type.

### Expected Result

Assignment Group automatically populated.

### Status

Pass

---

## TC004 - Priority Calculation

### Objective

Verify priority calculation works correctly.

### Test Data

| Impact | Urgency | Expected Priority |
|---------|---------|------------------|
| High | High | Critical |
| High | Medium | High |
| High | Low | Moderate |
| Medium | Medium | Moderate |
| Medium | Low | Low |
| Low | Low | Planning |

### Status

Pass

---

## TC005 - Resolution Notes Validation

### Objective

Verify Resolution Notes mandatory before closure.

### Steps

1. Open ticket.
2. Change State to Closed.
3. Leave Resolution Notes empty.
4. Save record.

### Expected Result

System prevents closure.

### Status

Pass

---

## TC006 - Email Notification

### Objective

Verify email notification triggers.

### Steps

1. Create ticket.
2. Submit record.

### Expected Result

Email notification sent to Requested By user.

### Status

Pass

---

## Overall Result

All test cases executed successfully.
