---
lab:
    title: 'Lab 2: How to build a canvas app'
    module: 'Module 3: Get started with Power Apps'
---

# Lab 2: How to build a canvas app

**WWL Tenants - Terms of Use**
If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training. 
Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and is not eligible for extension. 
Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time. 

## Scenario

Bellows College is an educational organization with multiple campuses and programs. Many of Bellow Colleges instructors and administrators need to attend events, and purchase items. Historically tracking these expenses has been a challenge. 

Campus administration would like to modernize their expense reporting system by providing employees with a digital way to report expenses. 

Throughout this course, you will build applications and perform automation to enable the Bellows College employees to manage expenses. 


## High-level lab steps

We will follow the below outline to design the canvas app:

- Create a canvas app from data in the Visit table

- Configure how the visits are shown on the browse screen

- Make some basic changes to the app

- Test the app functionality

## Prerequisites

- Completion of **Module 1 Lab 0 - Validate lab environment**

## Exercise 1: Create Visits Canvas app

**Objective:** In this exercise, you will create a canvas app by connecting the Visits table you created earlier.


### Task \#1: Create the Visits app

1.  Navigate to `https://make.powerapps.com`

2.  You may need to reauthenticate - select **Sign in** and follow instructions, if needed.

3.  Select the **Dev One** environment at the top right, if it is not already selected.

4.  Select **+ Create** from the left navigation of the screen. Under the **Start from** section, select **Dataverse**.

5.  Select your Dataverse connection.

    > **Note:** *If a Dataverse connection does not exist:*
    > - Select **+New connection**
    > - Locate **Microsoft Dataverse**
    > - Select **Create**
    > - **Sign in** and select **Allow access**

6.  Locate and select the **Visits** table you created in the previous lab.

7.  Select the **Connect** button in the bottom right corner.

8.  After your app is created, on the Welcome to Power Apps Studio screen, select **Don’t show me this again**, and then select **Skip**.

9.  After creation has completed, the Canvas app should look like the image below:

    ![Canvas app created from Visit data.](media/2-canvas-app-from-data.png)

10.  In the app designer, select the **Preview the app** button (Play icon) on the command bar. *(You can also preview the app by pressing F5.)* Take a look around and see how your app looks out-of-the-box.

11. Close the app preview by selecting the **X** in the upper right of the screen.

Congratulations, you have successfully created a Power App from a Dataverse table. The next step in the process is to tailor the app to match your Bellows College branding. The next series of steps will walk you through providing some extra customization to the app.


### Task \#2: Modify and theme the newly created app

In this task, you will customize the header text on each of the three screens for your app (Browse, Detail, and Edit) and change the app theme. 

1.  You are on the Browse screen. Select the **Visits** label on the screen.

1.  On the right side of the screen, under the Properties tab, update the **Text** control property to `Bellows College Visits`

1.  In the **Properties** tab, change the **Font size** to **24**. 

1.  Select the blank background of the screen to see the updated text on your Browse screen. 

1.  Using the **Tree view** in the left navigation, select **DetailScreen1**. 

1.  Select the **Visits** label on the screen.

1.  On the right side of the screen, under the **Properties** tab, update the **Text** control property to `Visit Details`

1.  Click in the blank background of the screen to see the updated text on your Details screen.

1.  Using the **Tree view** in the left navigation, select **EditScreen1** (You may need to scroll down to see this on the Tree view).

1.  Select the **Visits** label on the screen.

1.  On the right side of the screen, on the **Properties** tab, replace the text in the **Text** control property with `Edit Details`

1.  Click in the blank background of the screen to see the updated text on your Edit screen.

1.  Using the **Tree view**, in the left navigation, select **BrowseScreen1**.

1.  On the command toolbar, select the **Theme** button and from the list that appears, select the **Red** theme color.


### Task \#3: Test your Visits app

In this task, you will test out your new app.

1.  With your application open in the App Designer, select **Settings**, in the **General** section update the name of your app to `Visits App` select the **X** to close the settings screen and then select **Save**.

2.  Using the navigation on the left, select **BrowseScreen1**.

3.  In the app designer, select the **Preview the app** button (Play icon) on the command bar. *(You can also preview the app by pressing F5.)*

4.  Once the app opens, in the **Search items** field, enter the text `Maria`
    *(Notice how the items in the gallery filter based on what is typed in the
    search field).*

5.  Once the **Contoso Suites** record for **Maria Campbell** is displayed,
    select a row to navigate and open the Details screen for that visit. (**Note**: *If more than one Contoso Suites Maria Campbell record is
    displayed, select any of them.*)

6.  To edit the record, select the **Pencil Icon** in the upper right corner of the app.

7.  You can edit the **Visit Name** here and select the **Checkmark** icon in the top right to save the change.

8.  On the top right of the screen, select the **X** icon to close preview mode and return to the canvas app editor.

Congratulations! You have created and configured your first canvas app.

