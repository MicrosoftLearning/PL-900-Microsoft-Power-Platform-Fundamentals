---
lab:
    title: 'Lab 3: How to build a model-driven app'
    module: 'Module 3: Get started with Power Apps'
---

# Lab 3: How to build a model-driven app

**WWL Tenants - Terms of Use**
If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training. 
Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and are not eligible for extension. 
Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time. 

## Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus.

In this lab, you will build a Power Apps model-driven app to allow the backoffice campus staff to manage visit records across the entire campus.

High-level lab steps

As part of creating the model-driven app, you will complete the following:

- Create a new model-driven app named Bellows Campus Management

- Edit the app navigation to reference the required tables

- Customize the forms and views of the required tables for the app

We will work with the following components:

- **Views**: Views allow the user to display the existing data in the form table.

- **Forms**: This is where the user creates/updates new rows in the tables.

Both will be integrated to the model-driven app for a better user-experience.

Prerequisites

- Completion of **Module 0 Lab 0 - Validate lab environment**

- Completion of **Module 2 Lab 1 - Data Modeling**

Things to consider before you begin

- What changes should we make to improve the user experience?

- What should we include in a model-driven app based on the data model we have built?

- What customizations can be made on the sitemap of a model-driven app?

Exercise 1: Customize Views and Forms

**Objective:** In this exercise, you will customize views and forms of the custom created tables that will be used in the model-driven app.

Task #1: Edit Visit Form

1.  Sign in to <https://make.powerapps.com> if you are not already signed in.

2.  Select your **[my initials] Practice** environment at the top right if it is not already selected.

3.  Using the navigation on the left, select **Tables**, and open your **Visit** table.

    If you do not see the Visit table, make sure you are in the correct environment (Step 2).

4.  Under the **Data experiences** section, select **Forms** and open the **Information** form with **Main** Form type. (**Important:** Make sure you select the form with the form type of **Main**.) 

    **IMPORTANT:** Since by default all forms are named Information, make sure to verify that the form you select has a Form Type of **Main** and not something else. By default, the form has two fields: Name and Owner.

5.  On the right side of the screen on the **Properties** panel, select the **Display Name** field, and change it to `Main Information`

6.  Select **Table columns** from the left navigation pane and add the following fields below the **Owner** field by dragging columns to the form or simply clicking column names:

	1. **Visitor**

	2. **Scheduled Start**

	3. **Scheduled End**

	4. **Actual Start**

	5. **Actual End**

7.  Drag the **Code** column and drop it in the form header.

    The header is the top right area of the form. You may need to collapse the Properties panel on the right side of the screen to see the field on the form.

8.  With the **Code** field still selected, check the checkbox for **Read-only** in the Properties panel on the right side of the screen.

9.  Select **Owner** field. In the Properties panel, change the **Label** to `Host`

10. Select the **Save and publish** button at the top right and wait for the save and publish to complete.

11. If the Edit view opened in a new browser tab or window, close it. Otherwise, select **🡠 Back** at the top left of the screen. You should now be back to the **Visit** table Forms.

12. Using the breadcrumbs in the upper left (**Tables** > **Visit** > **Forms**). Select **Visit** to return to the **Visit** Table properties screen. 


Task #2: Edit Active Visits view

In this task, we will modify the default Active Visits view and create a new view for today’s visits.

1.  Under the **Data experiences** section, select **Views** and open your **Active Visits** view.

2.  Add the following fields to the view by either clicking or dragging and dropping the fields:

    1. **Code**

    2. **Visitor**

    3. **Scheduled Start**

    4. **Scheduled End**

3.  Select the drop-down menu on the **Created On** column and select **Remove**. The field **Created On** will now be removed from the view.

4.  Resize the individual column widths as suits to fit the data.

5.  Under **Sort by …** select the X to remove **Name** and instead, select **Scheduled Start**.

6.  Select **Scheduled Start** to change the sort order to **Newer to older**.

7.  Select the **Save and publish** button at the top right and wait for the publishing to complete.


Task #3: Create new view for today’s visits

Now, we will clone the view to create a new view for today’s visits.

IMPORTANT: Make sure that you do not close the Active Visits view, as we will be leveraging it to create the new today’s visits view.

1.  Select **Save As**.

2.  Change the **Name** to `Today’s Visits` and select **Save**.

3.  Select **Edit filters**, in the Properties panel.

4.  Select **+ Add**, select **Add row**.

5.  Select **Scheduled Start** as field, then change **Equals** to **Today** as the condition in the drop-down.

6.  Select the **…** **More commands** on the **Status** row and select **Delete** to delete that filter condition.

7.  Select **Ok** to save the condition. The view is now filtered to show only records where the **Scheduled Start** date is today.

8.  Add **Actual Start** and **Actual End** fields to the view.

    **Note:** Since we no longer filter on the view status, we will get all today’s visits including completed ones. These fields will help to differentiate completed visits and visits in progress.

9.  Select the **Save and publish** button at the top right and wait for the publishing to complete.


Exercise 2: Create Model-driven app

**Objective:** In this exercise, you will create a model-driven app, customize the sitemap, and test the app.

For simplicity and time’s sake, we will not be addressing some of the Visit columns in this lab.

Task #1: Create app

1.  Sign into <https://make.powerapps.com>, if you are not already signed in.

2.  Select your **[my initials] Practice** environment at the top right, if it is not already selected.

3.  Select **+ Create** on the left navigation.

4.  Create the Model-Driven Application:

    1. Select **Blank app** in the **Start from** section of the **Create your app** screen.

    2. Under **Blank app based on Dataverse**, select **Create**.

    3. Enter `Bellows Campus Management` for **Name** and select **Create**.

5.  After your new model-driven application loads, select the **+ Add Page** button.

6.  On the **Add Page** screen, choose **Dataverse table**, and then select the **Next** button.

7.  Select the following tables:

    1. Visit

    2. Contact

8.  After you have both tables, select **Add**.

9.  Using the navigation icons on the left side of the screen, select **Navigation**.

10. On the Navigation Pane, select **New Group** below where it says Navigation. You may need to expand the menu on the left.

11. On the right side of the screen, in the **Display options** section, change the **Title** property to `Security`

12. Select **Save** and wait until the changes are saved.

13. Once the **Save** is complete, select the **Publish** button to publish your changes.


Task #2: Test app

Start the application

1. Select the **Play** button, the model-driven app will load in a new tab.

Create a new Contact

2.  The app should open to the **My Active Contacts** view. If it does not, select **Contacts** on the left-hand navigation.

3.  Select **+ New** from the command bar.

4.  Enter **First Name** as `John` and **Last Name** as `Doe`

5.  Provide your personal email as **Email**. This will be used in a future lab, where you will receive an email.

6.  Select **Save &amp; Close**.

7.  You should now see the created contact on the **My Active Contacts** view.

Create a new Visit

8.  Select **Visits** from the left-hand navigation (Also known as the sitemap.)

9.  Select **+ New**.

10. Enter the fields as follows:

	1. **Name**: `New test visit`

	2. **Visitor**: select **John Doe**

	3. **Scheduled Start**: Select tomorrow’s date and 2:00 PM as start time

	4. **Scheduled End**: Select tomorrow’s date and 3:30 PM as end time

11. Select **Save &amp; Close**. This will create the Visit and you should be able to see it on the **Active Visits** view.

12. Change view to **Today’s Visits** by using the drop-down next to **Active Visits**. You should no longer see the new visit in the view, since it is scheduled for tomorrow.

13. You may add some more test records.

Your running model-driven app should look approximately like the following:

![](media/3-model-driven-app.png)

Congratulations! You have created and configured your first model-driven app.

## Challenges

- Select specific views and forms for Contacts.

