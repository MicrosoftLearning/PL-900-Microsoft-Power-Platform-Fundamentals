---
lab:
    title: 'Lab 03: Power Automate'
    module: 'Module XX: Power Apps Build'
---

# PL-900: Microsoft-Power-Platform-Fundamentals
## Module X, Lab 3 – Power Automate

Scenario
========

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently and there are no means to collect and analyze data about the visits across the entire campus. 

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus. 

In this lab, you will create Power Automate flows to automate various parts of the campus management. 

High-level lab steps
======================

The following have been identified as requirements you must implement to complete the project.

* The unique code assigned to each visitor must be made available to them prior to their visit.
* Security personnel needs to receive notifications of visitors overstaying their scheduled timeslots.

## Prerequisites

* Completion of Lab 1 - Data Modeling
* Campus Staff app created in Part 1 of Lab 2 – Canvas App (for testing)

Things to consider before you begin
-----------------------------------

-   What is the most appropriate distribution mechanism for the visitor codes.
-   How overstays could be measured and strict policies enforced.

Exercise \#1: Create Visit Notification flow
===============================

**Objective:** In this exercise, you will create a Power Automate flow that implements the requirement. Visitor notification is done using email. Notification includes the unique code assigned to the visit.

Task \#1: Create flow
---------------------------

1.  Open the Campus Management solution.

    -   Sign in to <https://make.powerapps.com>

    -   Select your **environment.**

    -   Select **Solutions**.

    -   Click to open the **Campus Management** solution.

2.  Click **New** and select **Flow**. This will open the flow editor in a New window.

3. Search for **Current** and select **Common Data Service (Current Environment)** connector.

4. Select the trigger **When a Record is Created**, **Updated**, or **Deleted**.

   * Select **Create** for **Trigger condition**
   * Select **Visits** for **The entity name**
   * Select **Organization** for **Scope**

5.  Click **New Step**. This step is required to retrieve visitors information including email.

6. Search for **Current** and select **Common Data Service (Current Environment)** connector.

7. Select **Get Record** action. 

   * Select **Contacts** as **Entity name**
   * Search dynamic content, select **Visitor (Value)** as a value for **Item ID**

8. Click **New Step**. This is the step that will create and send email to the visitor.

9. Search for *mail*, select **Mail** connector and **Send an email notification** action 

   * Select **Email** as **To** value

   * Enter **Your scheduled visit to Bellows College** as **Subject**

   * Enter the following text in **Email Body**

     > Dear {**First Name**},
     >
     > your are currently scheduled to visit Bellows Campus from {**Scheduled Start**} until {**Scheduled End**}.
     >
     > Your security code is {**Code**}, please do not share it. You will be required to produce this code during your visit.
     >
     > Best regards,
     > Campus administration
     > Bellows  College
     
   * Bolded text denotes dynamic content that needs to be inserted in these places.
10.  Select flow name and rename it to **Visit notification**

11.  Press **Save**

Task \#2: Validate and test the flow
--------------------------------

1.  Open **Campus Staff** app you created 
2.  Press + to add a new visit record
3.  Enter required information, press **Save**
4.  Open the flow, locate and open most recent **Run**
5.  Open **Mail** step and verify that email content has been generated correctly.

# Exercise #2: Create Security Sweep flow

**Objective:** In this exercise, you will create a Power Automate flow that implements the requirement. Security sweep is performed every 15 minutes and security is notified if any of the visitors overstayed their scheduled time.

## Task #1: Create flow to retrieve records

1. Open the Campus Management solution.

   -   Sign in to <https://make.powerapps.com>

   -   Select your **environment.**

   -   Select **Solutions**.

   -   Click to open the **Campus Management** solution.

2. Click **New** and select **Flow**. This will open the flow editor in a New window.

3. Search for *recurrence*, select **Schedule** connector, **Recurrence** trigger.

4. Set **Interval** to **15 minutes**

5. Click **New step**. Search for **Current** and select **Common Data Service (Current Environment)** connector. Select **List records** action.

   * Enter **Visits** as **Entity name**

   * Enter the following expression as **Filter Query**

     ```
     statecode eq 0 and bc_actualstart ne null and bc_actualend eq null and Microsoft.Dynamics.CRM.OlderThanXMinutes(PropertyName='bc_scheduledend',PropertyValue=15)
     ```

   To break it down

   * `statecode eq 0` filters active visits (where Status equal Active)
   * `bc_actualstart ne null` restricts search to visits where Actual Start has a value, i.e. there was a checkin
   *  `bc_actualend eq null` restricts search to visits where there was no check out (Actual End has no value) 
   * `Microsoft.Dynamics.CRM.OlderThanXMinutes(PropertyName='bc_scheduledend',PropertyValue=15)` restricts visits where visits meant to complete more than 15 minutes ago.  

6.  Click **New step**. Search for **Apply**, select **Apply to each** action 

7.  Select **value** from dynamics content as **Select an output from previous steps**.

8.  Add data retrieval for related record

    * Click **Add an action** inside the loop.
    * Search for **Current** and select **Common Data Service (Current Environment)** connector. 
    * Select **Get record** action.
    * Click ..., select **Rename**. Enter **GetBuilding** as step name
    * Select **Buildings** as **Entity name**
    * Select **Building (Value)** as **Item ID**

9.  Repeat previous data retrieval sequence for **Visitor** and **User**, selecting related entity name and using **Visitor (Value)** and **Owner (Value) **as **Item ID**, respectively

10.  Add **Send an email notification** action from **Mail** connection.

11.  Enter your email address as **To**

12.  Enter "Contact **Full Name** overstayed their welcome". **Full Name** is a dynamics content from the current Visit record.

13.  Enter "It happened in building **Name**", where **Name** is dynamics content from **GetBuilding** step

14.  Locate **Primary Email** from **GetUser** step and insert it into CC field (meeting host will receive a copy of the email)

15.  Select flow name and rename it to **Security Sweep**

16.  Press **Save**

## Task #2: Validate and test the flow

1. Locate or create visit records that 
   1. Have active status
   2.  Scheduled End is in the past (by more than 15 minutes)
   3. Actual Start has a value.
2. Open the flow created in task 1 and press **Test**
3. Select **I'll perform the trigger action**
4. Press **Run flow**
5. When flow competes, expand **Apply to each** then expand **Send an email notification** steps
6. Check the **Subject**, **Email Body** values. Expand **Show more** and check **CC** value.
8. Navigate to solution, click ... next to flow, select **Turn off**. This is to prevent flow from executing on a schedule on the test system.

# Challenges

* Add building information and map to the notification flow.
* Can you generate barcode for the visit code? When will that be useful?
* How to ensure user-friendly date formatting in the email body?
* Is it possible to generate a table with overstay information and send only single email?