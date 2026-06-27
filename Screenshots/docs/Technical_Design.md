# Technical Design Document

## Application Name

IT Service Request & Incident Management

## Platform

ServiceNow

## Application Scope

Custom ServiceNow application developed to manage IT Service Requests and Incident Tickets.

---

# Data Model

## Custom Table

| Table Name | Purpose |
|------------|---------|
| IT Ticket | Stores service requests and incident tickets |

---

# Fields

| Field | Type |
|---------|---------|
| Number | Auto Number |
| Ticket Type | Choice |
| Short Description | String |
| Description | String |
| Requested By | Reference |
| Assigned To | Reference |
| Assignment Group | Reference |
| Impact | Choice |
| Urgency | Choice |
| Priority | Choice |
| State | Choice |
| Resolution Notes | String |

---

# Form Design

The application form contains:

### Assignment Details
- Requested By
- Assigned To
- Assignment Group

### Classification
- Impact
- Urgency
- Priority
- State

### Resolution
- Resolution Notes

---

# Client Scripts

## Calculate Priority

Type: onChange

Fields:

- Impact
- Urgency

Logic:

- High + High = Critical
- High + Medium = High
- High + Low = Moderate
- Medium + Medium = Moderate
- Medium + Low = Low
- Low + Low = Planning

Priority is calculated automatically without saving the record.

---

# Business Rules

## Auto Assign Group

When Ticket Type = Incident

Assignment Group:

- IT_Request_Fulfillment

When Ticket Type = Service Request

Assignment Group:

- IT_Request_Fulfillment

---

# UI Policies

## Resolution Notes Mandatory

Condition:

State = Closed

Action:

Resolution Notes becomes mandatory before ticket closure.

---

# Flow Designer

## IT Ticket Creation Flow

Trigger:

Record Created

Table:

IT Ticket

Action:

Send Email

Email includes:

- Ticket Number
- Ticket Type
- Short Description
- State

Recipient:

Requested By

---

# Testing

Successfully validated:

- Ticket Creation
- Priority Calculation
- Assignment Group Population
- UI Policy Validation
- Email Notification
- Record Updates

---

# Deployment Status

Completed Successfully
