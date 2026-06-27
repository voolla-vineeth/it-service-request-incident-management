# IT Service Request & Incident Management

## Project Overview

This ServiceNow application was developed to streamline IT service requests and incident management processes. The solution enables users to create and manage IT tickets while automating priority calculation, assignment management, and email notifications.

## Business Requirement

Organizations require a centralized system to manage IT service requests and incidents efficiently. Manual ticket handling can lead to delays, inconsistent prioritization, and lack of visibility into request status.

The application addresses these challenges by providing:

* Standardized ticket creation process
* Automated priority calculation
* Automated ticket assignment
* Email notification automation
* Improved ticket tracking and visibility

## Features

### Ticket Management

* Create IT Service Requests
* Create Incident Tickets
* Track ticket status
* Maintain resolution details

### Priority Management

* Impact and Urgency based prioritization
* Automatic Priority calculation
* Real-time priority updates using Client Scripts

### Assignment Management

* Automatic Assignment Group population
* Automatic ticket assignment to support personnel

### Workflow Automation

* Flow Designer integration
* Automated email notifications on ticket creation
* End-to-end ticket processing

## Technical Components

### Custom Table

IT Ticket

### Fields

* Number
* Ticket Type
* Short Description
* Description
* Requested By
* Assignment Group
* Assigned To
* Impact
* Urgency
* Priority
* State
* Resolution Note

### ServiceNow Components Used

* App Engine Studio
* Custom Tables
* Form Designer
* Business Rules
* Client Scripts
* Flow Designer
* Email Notifications
* Choice Lists
* Reference Fields

## Automation Implemented

### Business Rule

Automatically calculates ticket priority based on Impact and Urgency values.

### Client Script

Updates Priority in real time before the record is submitted.

### Flow Designer

Triggers when a ticket is created and sends an email notification to the requester.

## Testing

The application was tested for:

* Ticket Creation
* Priority Calculation
* Assignment Group Population
* Auto Assignment
* Email Notification
* End-to-End Flow Execution

## Screenshots

Refer to the Screenshots folder for detailed implementation and testing evidence.

## Outcome

Successfully developed a ServiceNow application demonstrating:

* ITSM fundamentals
* Workflow automation
* Business Rule development
* Client Script development
* Flow Designer implementation
* Form and Table configuration

## Author

Vineeth Voolla
ServiceNow Administrator | ITSM | Governance & Documentation
# it-service-request-incident-management
ServiceNow IT Service Request &amp; Incident Management Application
