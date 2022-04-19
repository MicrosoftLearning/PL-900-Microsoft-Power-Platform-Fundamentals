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

-   Create a Power App from an existing Microsoft Excel File

-   Configure how the visits are shown on the browse screen

-   Make some basic changes to the app

-   Test the app functionality

## Prerequisites

-   Completion of **Module 0 Lab 0 - Validate lab environment**

## Things to consider before you begin

-   What is the most prevalent form factor for the target audience?

-   Estimate the number of records in the system

-   How to narrow the records selected to improve app performance and user
    adoption

## Before you begin

Prior to completing the items in this exercise, you will need to ensure that you
have the data files used throughout this exercise uploaded to OneDrive for
business.

1.  Navigate to **https://onedrive.live.com** and login with your student
    credentials.

2.  Upload the visits.xlsx file from your student files to your OneDrive.

# Exercise \#1: Create Staff Canvas App

**Objective:** In this exercise, you will create a canvas app for an existing
Excel Spreadsheet, and then perform some basic modifications.

## Task \#1: Create a visits app form an Excel spreadsheet

1.  Navigate to [](https://make.powerapps.com) and login with your credentials.

2.  In necessary, click the **Home** icon on the right side of the screen. Under
    the **Start from** section, select **Excel**.

3.  Select the OneDrive for business connection where you saved the Visits.xlsx
    file earlier.

**NOTE:** *If a OneDrive for Business connection does not exist:*

-   Select **New Connection**

-   Locate **OneDrive for Business**

-   Click **Create**

![](media/f209482a7870ebad7fab30ad9877f971.png)

1.  Locate and select the **Visits.xlsx** spreadsheet you copied over earlier.

2.  In the **Choose a table** window, select **Table1**, then click **Connect**.

3.  After your app is created, On the Welcome to Power Apps Studio screen, check
    the **Don’t show me this again** box, and then select **Skip**.

4.  After creation has completed, is should look like the image below.

    ![](media/e0267b361b91ba92ed7dc9fb09f5137c.png)

Congratulations, you have successfully created a Power App from an Excel file.
The next step in the process is to tailor the app to match a customer’s
branding. The next series of steps, will walk you through providing some extra
customization to the app.

## Task \#2: Modify and theme the newly created app

1.  On the left side of the screen, use the **Tree View** to select the
    **BrowseGallery1** control. *(This will select the gallery that is used to
    display the list of visits.)*

2.  After the Gallery is selected, click the **Edit** (Pencil) **Icon** on the
    gallery itself. *(This will enable the gallery to be edited at a record
    level.)*

3.  In the selected record (**Should be first record in list**), Select the
    **Title1** field, and resize it to be half of its original size.

4.  Select the **Subtitle1** field and resize it to be half its original size.

5.  Move the **Subtitle1** field to the right of the **Title1** field.

6.  Your Browsegallery1 field should resemble the image below.

    ![](media/8fc08beca956f8633e8d6c8fb5c2ddfc.png)

7.  Once completed, click anywhere in the gray background to deselect all items.

8.  On the **BrowseScreen1**, select the **LblAppName1** label control in the
    upper left side of the screen that displays the text **Table1**.

9.  On the right side of the screen, under the properties tab, replace the text
    Table1 in the **Text** control property with **“Visits”**.

10. Using the navigation on the left, select the **DetailsScreen1**.

11. Select the **LblAppName2** label control in the upper left side of the
    screen that displays the text **Table1**.

12. On the right side of the screen, under the properties tab, replace the text
    Table1 in the **Text** control property with **“Visit Details”**.

13. Using the navigation on the left, select the **EditScreen1**.

14. Select the **LblAppName2** label control in the upper left side of the
    screen that displays the text **Table1**.

15. On the right side of the screen, under the properties tab, replace the text
    Table1 in the **Text** control property with **“Edit Details”**.

16. Using the navigation on the left, select the **BrowseScreen1**.

17. On the command toolbar, select the **Theme** button and from the list that
    appears select the **Red** theme color.

18. Your completed app should resemble the image below.

![](media/29575f236bd6b9ab9bd5f885da65bca9.png)

## Task \#3: Test your Visits app

In this task, you will configure a form to edit information about individual
visit rows.

1.  With your application open in the App Designer, select **File** \> **Save**,
    and save your app with the name **Visits from xls**.

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

-   Calendar view of all visits and filtering by date range

-   Ability to create and manage contacts as part of the app

-   How to display multiple meetings during a single visit
