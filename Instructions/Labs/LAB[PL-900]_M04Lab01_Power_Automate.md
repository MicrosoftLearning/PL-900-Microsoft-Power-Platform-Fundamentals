---
lab:
    title: 'Lab 6: How to build an automated solution'
    module: 'Module 4: Get Started with Power Automate'
---

# Module 4: Get Started with Power Automate
## Lab: How to build an automated solution

## Scenario

Bellows College is an educational organization with multiple buildings on
campus. Campus visitors are currently recorded in paper journals. The
information is not captured consistently, and there are no means to collect and
analyze data about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system
where access to the buildings is controlled by security personnel and all visits
are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to
enable the Bellows College administration and security personnel to manage and
control access to the buildings on campus.

In this lab, you will create Power Automate flows to automate various parts of
the campus management.

# High-level lab steps

The following have been identified as requirements you must implement to
complete the project:

-   Security personnel need to receive notifications of visitors overstaying
    their scheduled timeslots.

## Prerequisites

-   Completion of **Module 0 Lab 0 - Validate lab environment**

-   Completion of **Module 2 Lab 1 - Introduction to Microsoft Dataverse**

-   John Doe contact created with a personal email address in

## Things to consider before you begin

-   How could overstays be measured and strict policies enforced?

# Exercise \#1: Create Visit Notification flow

**Objective:** In this exercise, you will create a Power Automate flow that
implements the requirement. The visitor should be sent an email that includes
the unique code assigned to the visit.

## Task \#1: Create flow

1.  Open your Campus Management solution.

    1.  Sign in to <https://make.powerapps.com>

    2.  Select your **environment.**

    3.  Select **Solutions**.

    4.  Click to open your **Campus Management** solution.

2.  Click **New** and select **Automation**, **Cloud flow** and then
    **Automated**. This will open the Power Automate flow editor in a new
    window.

3.  In **Choose your flow's trigger**, search for **Microsoft Dataverse**.

4.  Select the trigger **When a row is added, modified or deleted**, and then
    click **Create**.

    1.  Select **Added** for **Change type**

    2.  Select **Visits** for **Table name**

    3.  Select **Organization** for **Scope**

    4.  On the trigger step, click the ellipsis (**...**) and click **Rename**.
        Rename this trigger **"When a visit is added"**. This is a good
        practice, so you and other flow editors can understand the purpose of
        the step without having to dive into the details.

5.  Select **New Step**. This step is required to retrieve visitors information,
    including email address.

6.  Search for **Microsoft Dataverse**.

7.  Select **Get a row by ID** action.

    1.  Select **Contacts** as **Table name**

    2.  In the **Row ID** field, select **Visitor (Value)** from the Dynamic
        content list.

    3.  On this action, click the ellipsis (**...**) and click **Rename**.
        Rename this action **"Get the Visitor"**. This is a good practice, so
        you and other flow editors can understand the purpose of the step
        without having to dive into the details.

8.  Click **New Step**. This is the step that will create and send email to the
    visitor.

9.  Search for *mail*, select **Office 365 Outlook** connector and **Send an
    email (V2)** action.

    1.  If asked to Accept terms and conditions for using this action, click
        **Accept**.

    2.  Select **To** field, select **Email** from the Dynamic content list.
        Notice that it is beneath the **Get the Visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

    3.  Enter **Your scheduled visit to Bellows College** in the **Subject**
        field.

    4.  Enter the following text in **Email Body**:

>   Dynamic content needs to be placed where fields are named in brackets. It is
>   recommended to copy & paste all text first and then add dynamic content in
>   the correct places.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1.  Highlight the **{Text First}** text. Replace it with the **First Name**
    field from the **Get the Visitor** step.

2.  Highlight the **{Scheduled Start}** text. Replace it with the **Scheduled
    Start** field **Get the Visitor** step.

3.  Highlight the **{Scheduled End}** text. Replace it with the **Scheduled
    End** field from the **Get the Visitor** Step.

4.  Select the **Untitled** flow name at the top and rename it to `Visit
    notification`

5.  Press **Save**

    Leave this flow tab open for the next task. You flow should look
    approximately like the following:

## ![](media/4973f9db7b65b1232d5c78ca8aceafec.png)

## Task \#2: Validate and test the flow

1.  Open a new tab in your browser and navigate to <https://make.powerapps.com>

2.  Click **Apps** and select the **Campus Management Model-driven** app you
    created earlier.

3.  Leaving this tab open, navigate back to the previous tab with your flow.

4.  On the command bar, click **Test**. Select **Manually** and then **Save &
    Test**.

5.  Using the navigation on the left, select **Contacts**.

6.  Press **+ New** to add a new **Contact** record

7.  Complete the Contact as follows:

    -   **First Name:** Your First Name

    -   **Last Name:** Your Last Name

    -   **Email:** Enter your personal or work email

8.  Select the **Save and Close** button.

9.  Using the navigation on the left, select **Visits**

10. Press the **+ New** button to add a new **Visit** record.

11. Complete the Visit record as follows:

    -   **Name:** Test Visit

    -   **Building:** Select Any Building

    -   **Visitor:** Select the Contact you just created

    -   **Scheduled Start:** Tomorrow at 8:00 AM

    -   **Scheduled End:** Tomorrow at 9:00 AM

12. Select the **Save and Close** button.

After a short delay, you should see an email in the mailbox of the that you
entered into the contact’s name.
