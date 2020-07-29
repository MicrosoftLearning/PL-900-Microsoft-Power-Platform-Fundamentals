---
lab:
    title: 'Lab: Model-driven App'
    module: 'Module 3: Get Started with Power Apps'
---

# Module 3: Get Started with Power Apps
## Lab: Model-driven App

Scenario
========

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus. 

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus. 

In this lab, you will build a Power Apps model-driven app to allow the backoffice campus staff to manage visit records across the entire campus.

High-level lab steps
======================

As part of creating the model-driven app, you will complete the following:

-   Create a new model-driven app named Campus Management

-   Edit the app navigation to reference the required entities

-   Customize the forms and views of the required entities for the app

We will work with the following components:

- **Views**: Views allow the user to display the existing data in the form
of table.

- **Forms**: This is where the user creates/updates new records in the entities.

Both will be integrated to the model-driven app for a better user-experience.

## Prerequisites

* Completion of Lab 1 - Data Modeling

Things to consider before you begin
-----------------------------------

-   What changes should we make to improve the user experience?

-   What should we include in a model-driven app based on the data model we have built?
    
-   What customizations can be made on the sitemap of a model-driven app?


Exercise \#1: Customize Views and Forms
=======================================

**Objective:** In this exercise, you will customize views and forms of the custom created entities that will be used in the model-driven app.

Task \#1: Edit Visit Form
-----------------------------------

1.  Sign in to <https://make.powerapps.com> if you are not already signed in.
2.  Select your **environment.**
3.  Select **Solutions**.
4.  Click to open your **Campus Management** solution.
5.  Click to open the **Visit** entity.
6.  Select the **Forms** tab and click to open the **Main** form type. 
    -   By default the form has two fields, Name (Primary Field) and Owner.
7.  Add the following fields below the **Owner** field by dragging fields to the form or simply clicking field names:
    * **Building**
    * **Visitor**
    * **Scheduled Start**
    * **Scheduled End**
    * **Actual Start**
    * **Actual End** 
8.  Drag the **Code** field and drop it in the form header. (You may need to minimize the Properties panel on the right side of the screen to see the field on the form.)
9.  While still selected on the Code field, check the checkbox for the **Read-only** field in the Properties panel.
10.  Select **Owner** field and in the Properties panel change the **Field label** to **Host**
11.  Click **Save** at the top right and wait for the save to complete.
12.  Click **Publish** at the top right and wait for the publishing to complete.
13.  Click **Back** at the top left of the screen. You should now be back to the
     Visit entity Forms Tab.

## Task \#2: Edit Visit Views

In this task, we will modify default Active Visits view and create new view for today's visits.

1.  Select the **Views** tab and click to open the **Active Visits** view.
2.  Add the following fields to the view by either clicking or dragging and dropping the fields:
    1.  **Code**
    2.  **Visitor**
    3.  **Building**
    4.  **Scheduled Start** 
    5.  **Scheduled End**
3.  Click on the dropdown arrow by the **Created On** column and select **Remove**. Field **Created On** will now be removed from the view.
4.  Click on the dropdown arrow by the **Name** column and select **Remove**. Field **Name** will now be removed from the view.
5.  In the Properties panel on the right, click **Sort by** and select **Scheduled Start**. Click on **Scheduled Start** again to change the order to descending (new visits on top).
6.  Resize the individual column widths to fit the data.
7.  Click **Save** and wait until the changes are saved.
8.  Click **Publish** and wait for the publishing to complete.
9.  Now we will clone the view to create a new view for today's visits. Click `x` next to the existing filter in the Properties panel to remove the filter.
10.  Click on the dropdown arrow by the **Save** button (be careful not to press the button itself) and select **Save As**.
11.  Change the name to **Today's Visits** and press **Save**.
12.  Press **Edit filters** link in the Properties panel.
13.  Click **Add**, select **Add row**.
14.  Select **Scheduled Start** as a field, then select **Today** as the condition. 
15.  Click the **...** on the **Status** row and click **Delete**. 
16.  The view is now filtered to show only records where the Scheduled Start date is today. Press **Ok** to save the condition.
15.  Add **Actual Start** and **Actual End** fields to the view. Since we no longer filter on the view status, we will get all today's visits including completed ones. These fields will help to differentiate completed visits and visits in progress.
16.  Click **Save** and wait until the changes are saved.
17.  Click **Publish** and wait for the publishing to complete.


Exercise \#2: Create Model-Driven Application
=============================================

**Objective:** In this exercise, you will create the model-driven app, customize the sitemap, and test the app.

**Note:** You will see several fields not addressed as you build out your application, particularly on the sitemap steps. We have taken some short cuts in the interest of doing the labs. In a real implementation, you would give these items logical names.

Task \#1: Create Application
----------------------------

1.  Open your Campus Management solution if you are not already in it.

    -   Sign in to <https://make.powerapps.com>

    -   While in your environment, click to open your **Campus Management**
        solution.
2.  Create the Model-Driven Application

    -   Click **New** and select **App** and then **Model-Driven App**. This will open a new tab.
    -   Select **Use existing solution to create the App** checkbox
    -   Enter **[Your Last Name] Campus Management** for Name and click **Done**.
3.  Click the pencil icon next to **Site Map.**
4.  Edit the default titles

    -   Select **New Area**.

    -   Change the Title of the **New Area** to **Campus** in the properties pane on the right.

    -   Select **New Group**.

    -   Change the Title of the **New Group** to **Security** in the properties pane on the right.
5.  Add the Contact entity to the sitemap

    -   Select **New Subarea**.

    -   In the **Properties** pane, select **Entity** from the dropdown
        for **Type**.

    -   Search for **Contact** entity from the dropdown for **Entity**.
6.  Add the Visit entity to the sitemap

    -   Select **Security** group and click **Add**.

    -   Select **Subarea**.

    -   Go to the **Properties** pane.

    -   Select **Entity** from the dropdown for **Type** and search for
        **Visit** entity from the dropdown for **Entity**.
7.  Add the Building entity to the sitemap

    -   Select **Campus** area and click **Add**.
-   Select **Group**.
    -   Enter **Settings** for **Title** in the **Properties** pane.
    -   WHile still selected on the **Settings** Area, click **Add**.
    -   Select **Subarea**.
    -   Go to the **Properties** pane.
    -   Select **Entity** from the dropdown for **Type** and search for **Building** entity from the dropdown for **Entity**.

8.  Click **Save**. This will show the loading screen while the changes are getting saved.

9.  Click **Publish** to publish the sitemap and wait for the publishing to complete.
10.  Click **Save and Close** to close the sitemap editor.
11.  You will see the assets for the entities that were added to the sitemap are
     now all in the application.
12.  Click **Save** to save the application.
13.  Click **Validate** to validate the changes done in the application. This will show some warnings but we can ignore them, since we have not referenced a specific View and Form for the entities and the users will have access to all the Views and Forms for **Visit** and **Building** entities.
14.  Click **Publish** to publish the application and wait for the publishing to
     complete.
15.  Click **Save and Close** to close the app designer.
16.  Click **Done**.
17.  Select **Solutions** and select **Publish all Customizations.**
18.  Select **Apps** and your application should now be listed.

Task \#2: Test Application
--------------------------

1.  Start the application

    -   Select **Apps** and click on your **Campus Management** app. (If you don't see your app at first, you may need to refresh your browser.)

    -   The application should open in a new window.
2.  Create new Contact record

    -   Select **Contacts**

    -   Click **New** from the top menu.

    -   Provide **First Name** as **John** and **Last Name** as **Doe**.

    -   Click **Save and Close**.

    -   You should now see the created contact on the **Active Contacts** view.
3.  Create new Building record

    -   Select **Buildings** from the sitemap.

    -   Click **New**.

    -   Enter the **Name** as Microsoft Building
        
    -   Click **Save and Close** and this will show the newly created record on
        the Active Buildings View.
4.  Create new Visit record

    -   Select **Visits** from the sitemap.
    -   Click **New**.
    -   Enter the fields as following 
        -   **Name**: New test visit
        -   **Building**: select Microsoft Building
        -   **Visitor**: select John Doe
        -   **Scheduled Start**: select today's date and 2:00 PM as start time
        -   **Scheduled End**: select today's date and 3:30 PM as end time
    -   Click **Save and Close**. This will create the record and you should be able to see it on the
        Active Visits View.
    -   Change view to **Today's Visits**. You should be able to see the entered visit in the view.
5.  You may add more test records.

# Challenges

* Select specific views and forms for Visits and Buildings
* Security personnel typically work in a single building. How would you provide an easy way for them to display visits only for a selected building?
* Restrict access to specific entities, e.g. Buildings should be read-only for all staff members except the administrators
* What Dashboards would you consider adding to the app?
