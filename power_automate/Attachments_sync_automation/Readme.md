Power Automate Flow Documentation
This README describes two Power Automate flows used in the Work Order and Notes automation process.

Flow 1: Trigger on Note Added / Modified / Deleted
Trigger:
When a row is added, modified or deleted
Table: Notes
Scope: Organization
Flow Logic:
Trigger fires when a Note is created or updated.
Fetch related Incident (Service Request) using the Regarding field.
Check if the Incident contains a Work Order reference.
If Work Order exists → Check if the Owner Type = Team.
If both conditions are true → Create a new Note.
Otherwise → Flow ends or performs alternative actions.
Flow 2: Trigger When a Work Order Is Added
Trigger:
When a row is added
Table: Work Orders
Scope: Organization
Flow Logic:
Trigger fires when a new Work Order record is created.
Fetch all related Notes via lookup relationships.
Fetch the related Service Request using the Work Order's related fields.
Pass required data to:
Power Automate subflows
Plugins
Azure Integrations
Key Lookups Used:
Service Request (Value)
Primary Incident Customer Asset
Priority
Work Order Type
Billing Account
Service Account
Site
Territory
And other Dataverse relationships.
Architecture Diagram Summary
The two flows integrate with Dataverse and external services as shown: - Power Apps → Dataverse → Power Automate → Plugins → Azure Integrations
