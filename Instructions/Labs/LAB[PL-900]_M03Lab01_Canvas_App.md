---
lab:
    title: 'Lab 3: How to build a canvas app'
    module: 'Module 3: Get started with Power Apps'
---

# Module 3: Get started with Power Apps
## Lab 1: How to build a canvas app

# Scenario

Bellows College is an educational organization with multiple buildings on
campus. Campus visits are currently recorded in paper journals. The information
is not captured consistently, and there are no means to collect and analyze data
about the visits across the entire campus.

Currently, campus administration is leveraging an excel spreadsheet, to track
visitor registration. They would like to modernize their visitor registration
system where access to the buildings is controlled by security personnel and all
visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to
enable the Bellows College administration and security personnel to manage and
control access to the buildings on campus.

# High-level lab steps

We will follow the below outline to design the canvas app:

-   Create a canvas app from data in the Visit table

-   Configure how the visits are shown on the browse screen

-   Make some basic changes to the app

-   Test the app functionality

## Prerequisites

-   Completion of **Module 0 Lab 0 - Validate lab environment**

# Exercise \#1: Create Visits App

**Objective:** In this exercise, you will create a canvas app by connecting your
Visits Initials table you created earlier.

## Task \#1: Create a Visits App

1.  Navigate to <https://make.powerapps.com>. You may need to reauthenticate - click **Sign in** and follow instructions if needed.

2.  Select your **[my initials] Practice** environment at the top right if it is
    not already selected.

3.  In necessary, click the **Home** icon on the right side of the screen. Under
    the **Start from** section, select **Dataverse**.

4.  Select the OneDrive for business connection where you saved the Visits.xlsx
    file earlier.

>   **NOTE:** *If a Dataverse connection does not exist:*
>   -   Select **New Connection**
>   -   Locate **Microsoft Dataverse**
>   -   Click **Create**

5.  Locate and select the **Visits your initials** table you created in the
    previous lab.

6.  Select the **Connect** button.

7.  After your app is created, On the Welcome to Power Apps Studio screen, check
    the **Don’t show me this again** box, and then select **Skip**.

8.  After creation has completed, is should look like the image below.

Congratulations, you have successfully created a Power App from an a Dataverse
table. The next step in the process is to tailor the app to match a customer’s
branding. The next series of steps, will walk you through providing some extra
customization to the app.

## Task \#2: Modify and theme the newly created app

1.  On the left side of the screen, use the **Tree View** to select the
    **BrowseGallery1** control. *(This will select the gallery that is used to
    display the list of visits.)*

2.  On the **BrowseScreen1**, select the **LblAppName1** label control in the
    upper left side of the screen that displays the text **Visit your
    Initials**.

3.  On the right side of the screen, under the properties tab, replace the text
    Table1 in the **Text** control property with **“Visits”**.

4.  Using the navigation on the left, select the **DetailsScreen1**.

5.  Select the **LblAppName2** label control in the upper left side of the
    screen that displays the text **Visit your Initials**.

6.  On the right side of the screen, under the properties tab, replace the text
    Table1 in the **Text** control property with **“Visit Details”**.

7.  Using the navigation on the left, select the **EditScreen1**.

8.  Select the **LblAppName2** label control in the upper left side of the
    screen that displays the text **Visit your Initials**.

9.  On the right side of the screen, under the properties tab, replace the text
    Table1 in the **Text** control property with **“Edit Details”**.

10. Using the navigation on the left, select the **BrowseScreen1**.

11. On the command toolbar, select the **Theme** button and from the list that
    appears select the **Red** theme color.

## Task \#3: Test your Visits app

In this task, you will configure a form to edit information about individual
visit rows.

1.  With your application open in the App Designer, select **File** \> **Save**,
    and save your app with the name **Visits App**.

2.  Once the app is saved, use the **back** arrow to return to your app.

3.  In the app designer, select the **preview your app** button on the command
    bar. *(You can also preview the app by pressing F5 on your keyboard.)*

4.  Once the app opens, in the **Search Items** field, enter the text **Maria**
    *(Notice how the items in the gallery filter based on what is typed in the
    search field).*

5.  Once the **Contoso Suites** record for **Maria Campbell** is displayed,
    click the **right arrow** on the record to navigate to the **Visit Details**
    screen. (**Note**: *If more than one Contoso Suites Maria Campbell record is
    displayed, select any of them*)

6.  To edit the record, select the **Pencil Icon** in the upper right corner of
    the app.

7.  On the top of the screen, click the **X** Icon to return to the **Property
    Details** Screen

8.  Click the **Left Arrow** to return to the Browse screen.


# Challenges

-   Create a view of all visits filtered by date range

-   Add the ability to create and manage contacts as part of the app
