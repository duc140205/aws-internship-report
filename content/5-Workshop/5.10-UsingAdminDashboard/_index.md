---
title : "Using the Admin Dashboard"
date :  "2025-09-09" 
weight : 10
chapter : false
pre : " <b> 5.10. </b> "
---

## Using the Admin Dashboard

The Admin Dashboard provides a comprehensive interface for managing consultants, schedules, and appointments.

### Overview Page

After logging in, the dashboard homepage displays:

**System Statistics:**
- Total number of customers
- Total number of consultants
- Total number of appointments

**Appointments Breakdown:**
- Visual chart showing appointments by status:
  - Pending
  - Confirmed
  - Completed
  - Cancelled

**Recent Appointments:**
- List of the most recent appointments
- Quick view of customer, consultant, date, and status

### Consultants Management

Navigate to the **Consultants** section to manage your consultant team.

#### View Consultants

- See all consultants in a table view
- Columns: Name, Email, Specialization, Status
- Search and filter capabilities

#### Add a New Consultant

1. Click the **Add Consultant** button
2. Fill in the consultant details:
   - Full Name
   - Email
   - Specialization
   - Biography
   - Profile Picture URL (optional)
3. Click **Create**

{{% notice info %}}
Creating a consultant will automatically create a corresponding Cognito user account with temporary credentials sent to their email.
{{% /notice %}}

#### Edit Consultant Information

1. Click the **Edit** button next to a consultant
2. Update the desired fields
3. Click **Save Changes**

#### Delete a Consultant

1. Click the **Delete** button next to a consultant
2. Confirm the deletion
3. The consultant's Cognito account will also be removed

{{% notice warning %}}
Deleting a consultant will not delete their historical appointments, but they will no longer be bookable.
{{% /notice %}}

#### Reset Consultant Password

1. Click the **Reset Password** button
2. A new temporary password will be generated
3. The consultant will receive the password via email

### Schedule Management

Navigate to the **Schedules** section to manage consultant availability.

#### View Schedules

- See all time slots across all consultants
- Filter by consultant, day of week, or status
- Calendar view for better visualization

#### Add Time Slots

1. Click **Add Time Slot**
2. Select consultant
3. Choose day of week (Monday - Sunday)
4. Set start time and end time
5. Click **Create**

#### Edit Time Slots

1. Click the **Edit** button next to a time slot
2. Modify the time or availability
3. Click **Save**

#### Delete Time Slots

1. Click the **Delete** button next to a time slot
2. Confirm deletion

{{% notice tip %}}
You can create recurring time slots by adding the same time for multiple days of the week.
{{% /notice %}}

### Appointments Management

Navigate to the **Appointments** section for comprehensive appointment oversight.

#### View Appointments

- Table view of all appointments
- Filter by:
  - Status (Pending, Confirmed, Completed, Cancelled)
  - Date range
  - Consultant
  - Customer

#### Appointment Details

Click on any appointment to see:
- Customer information
- Consultant information
- Date and time
- Status
- Notes
- Creation timestamp

#### Create Manual Appointment

1. Click **Create Appointment**
2. Select customer (or create new)
3. Select consultant
4. Choose date and time
5. Add notes (optional)
6. Click **Book Appointment**

#### Update Appointment

1. Click **Edit** on an appointment
2. Modify details (time, consultant, notes)
3. Click **Update**

{{% notice info %}}
Email notifications will be sent to both customer and consultant when appointments are created or updated.
{{% /notice %}}

#### Cancel Appointment

1. Click **Cancel** on an appointment
2. Optionally add cancellation reason
3. Confirm cancellation
4. Notification emails will be sent

#### Change Appointment Status

Manually update appointment status:
- **Pending** → **Confirmed**: Approve a booking
- **Confirmed** → **Completed**: Mark as finished
- **Any** → **Cancelled**: Cancel the appointment

### Search and Filter Features

All data tables support:
- **Search**: Free-text search across relevant fields
- **Sort**: Click column headers to sort
- **Filter**: Use dropdown filters for status, dates, etc.
- **Pagination**: Navigate through large datasets

### Dashboard Settings

Access settings from the top-right menu:
- Update your admin profile
- Change password
- Configure email templates
- System preferences

{{% notice tip %}}
Use the dashboard's search features to quickly find specific consultants, customers, or appointments instead of scrolling through long lists.
{{% /notice %}}

You now have full control over the MeetAssist system through the Admin Dashboard!
