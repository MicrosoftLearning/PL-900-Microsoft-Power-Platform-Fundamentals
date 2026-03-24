---
lab:
    title: 'Lab 3: Create a model-driven app'
    learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
    module: 'Build a model-driven app'
    description: In this lab, learners will create a model-driven app in Power Apps using the modern app designer. You will add Dataverse tables to the app, configure navigation groups, and publish and test the application.
    duration: 30 minutes
    level: 100
    islab: true
    primarytopics:
        - Power Apps
---
# Practice Lab 3 - Create a model-driven app

**Estimated time:** 30 minutes

## Lab objectives

In this lab, you will learn to:

-   Understand the difference between canvas apps and model-driven apps
-   Create a model-driven app using the modern app designer
-   Add a Dataverse table to the app’s site map
-   Customize the main form and view for the table
-   Publish and test the model-driven app

## Scenario

While employees submit requests using a mobile canvas app, the Contoso facilities management team needs a full-featured desktop application to manage, triage, and track all requests. Model-driven apps are ideal for this because the interface is automatically generated from the data model, providing a consistent and professional experience.

# Exercise 1: Create the model-driven app

## Task 1: Create a model-driven app

1.  Navigate to Power Apps Maker portal `https://make.powerapps.com` and sign in.
1.  Select **+ Create** from the left navigation, then select **Blank Page with navigation**.
1.  Name the app **Contoso Facilities Management** and click **Create**.
1.  The modern App Designer will open.

## Task 3: Add the Facility Request table

1.  In the **App Designer**, Click **+ New page (or + Add page)** and select **Dataverse** table.
1.  Search for and select both the **Facility Request** and **Rooms** tables (if you completed Lab 1) additionally choose the **Account** and **Contact** tables.
1.  Make sure Show in navigation is selected and select **Add**. The tables will now appear in your app's navigation.

    ![Screenshot of Navigation](media/9444e25f3cc06dcda4d636224bc7a949.png)

1.  Under **Navigation**, select **New Group**.
1.  On the right side of the screen, expand the **New Group** pane.
1.  Change the title from **New Group** to **Customers.**
1.  Select the **three dots** next to the **Customers** group and choose **New group**.
1.  Change the **Name** of the **New Group** to **Facilities**.
1.  Under **Navigation** select the **Facility Requests** view, select **Move Down** until it is in the **Facilities Group**.
1.  Select the **Rooms** view and **Move** it down below **Facility Requests**.
1.  Select the **Save** button.
1.  Your completed App should resemble the image below:

    ![Screenshot of updated navigation ](media/cde7b0696e4a49f586820351b404c066.png)

# Exercise 2: Edit Facility Request form and Facility Request public view
## Task 1: Modify the Facility Request main form

1.  Open a new tab and navigate to the Power Apps Maker portal `https://make.powerapps.com`
1.  Make sure you are in the Dev One environment.
1.  In the left navigation pane, select **Tables**. 
1.  In the search bar at the top-right, type **Facility Request**, and then select the **Facility Request** table from the results.
1.  Under **Data experiences**, select **Forms**.
1.  Select the **Information** form where the Form type is Main, select the Commands menu (...), and select Edit > Edit in new tab.
1.  Drag the **Owner** column into the Header area.
1.  Drag the **Description** column below **Request Title**.
1.  Drag the **Date Requested** column below **Description**.
1.  Drag the **Estimated Cost** column below **Date Requested**.
1.  Drag the **Category** column below **Estimated Cost**.
1.  Drag the **Priority** column below **Category**.
1.  Drag the **Status** column below **Priority**.
1.  Select **Save and publish**.
1.  **Close** the form designer.
1.  Select **Done**

## Task 2: Modify the Facility Request public view

1.  Navigate to the Power Apps Maker portal `https://make.powerapps.com`
1.  Make sure you are in the Dev One environment.
1.  In the left navigation pane, select **Tables**. 
1.  In the search bar at the top-right, type **Facility Request**, and then select the **Facility Request** table from the results.
1.  Under **Data experiences**, select **Views**.
1.  Select the Active Facility Requests view, select the Commands menu (...), and select Edit > Edit in new tab.
1.  Select the caret next to the **Created On** column and select **Remove**.
1.  Select the **Description** column to add to the view.
1.  Select the **Date Requested** column to add to the view.
1.  Select the **Estimated Cost** column to add to the view.
1.  Select the **Category** column to add to the view.
1.  Select the **Priority** column to add to the view..
1.  Select the **Status** column to add to the view.
1.  Select **Save and publish**.
1.  **Close** the view designer.
1.  Select **Done**


## Task 3: Publish and test

1.  Navigate to the Power Apps Maker portal `https://make.powerapps.com`
1.  In the left navigation pane, select **Apps**.
1.  Select **Contoso Facilities Management** Model-driven app.
1.  Click **Save and then Publish** in the upper right.
1.  Click Play to open the app in a new browser tab.
1.  Verify the following:
    -   The navigation menu shows your Facility Request table.
    -   Clicking the table name shows the list view with the columns you configured.
    -   Clicking on a record opens the form with the layout you customized.
    -   You can create a new record by clicking + New.
****










