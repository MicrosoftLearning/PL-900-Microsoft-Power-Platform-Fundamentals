---
lab:
    title: 'Lab 1: Data Modeling'
    module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Module 2: Introduction to Microsoft Dataverse

# Scenario

Bellows College is an educational organization with multiple buildings on
campus. Campus visits are currently recorded in paper journals. The information
is not captured consistently, and there are no means to collect and analyze data
about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system
where access to the buildings is controlled by security personnel and all visits
are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to
enable the Bellows College administration and security personnel to manage and
control access to the buildings on campus.

In this lab you will access your environment, create a Microsoft Dataverse
database, and create a solution to track your changes. You will also create a
data model to support the following requirements:

-   R1 – Track the locations (buildings) of the campus visits

-   R2 – Record basic information to identify and track the visitors

-   R3 – Schedule, record, and manage visits

Finally, you will import sample data into Microsoft Dataverse.

# High-level lab steps

To prepare your learning environments you will:

* create a solution and publisher
* add both new and existing components required to meet the application requirements. Refer to the [data model document](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) for the metadata description (tables and relationships). You can hold CTRL+click or right click the link to open the data model document in a new window.
* create Building and Visit tables
* import Visit data using an Excel spreadsheet

## Prerequisites:

-   Completion of **Module 0 Lab 0 - Validate lab environment**

## Things to consider before you begin:

-   Naming conventions - type names carefully.

# Exercise \#1: Create New Table

**Objective:** In this exercise, you will create new custom table Visits. 

## Task \# 1: Create Visit Table and Columns

The **Visit** table will contain information about the campus visits including
the building, visitor, scheduled and actual time of each visit.

We would like to assign each visit a unique number that can be easily entered
and interpreted by a visitor when asked during the visit check-in process.

>   We use **Time zone independent** behavior to record date and time
>   information, because time of a visit is always local to the location of the
>   building and should not change when viewed from a different time zone.

1.  Sign into <https://make.powerapps.com> (if you are not already signed in)

2.  Select your **[my initials] Practice** environment at the top right if it is
    not already selected.

3.  Using the navigation on the left, expand Dataverse, and select Tables.

4.  Click **New table**.

5.  Enter **Visit** for **Display Name**.

6.  Click **Create**. This will start provisioning the table in background while
    you can start adding other columns.

7.  Create Scheduled Start column

    1.  You should be on the Visit table columns page.

    2.  Make sure you have the **Columns** tab selected and click **Add
        column**.

    3.  Enter **Scheduled Start** for **Display name**.

    4.  Select **Date and Time** for **Data type**.

    5.  In **Required**, select **Required**.

    6.  Expand **Advanced options** section.

    7.  In **Behavior**, select **Time zone independent**.

    8.  Click **Done**.

8.  Create Scheduled End column

    1.  Click **Add column**.

    2.  Enter **Scheduled End** for **Display name**.

    3.  Select **Date and Time** for **Data type**.

    4.  In **Required**, select **Required**.

    5.  Expand **Advanced options** section.

    6.  In **Behavior**, select **Time zone independent**.

    7.  Click **Done**.

9.  Create Actual Start column

    1.  Click **Add column**.

    2.  Enter **Actual Start** for **Display name**.

    3.  Select **Date and Time** for **Data type**.

    4.  In **Required**, leave this as **Optional**.

    5.  Expand **Advanced options** section.

    6.  In **Behavior**, select **Time zone independent**.

    7.  Click **Done**.

10. Create Actual End column

    1.  Click **Add column**.

    2.  Enter **Actual End** for **Display name**.

    3.  Select **Date and Time** for **Data type**.

    4.  In **Required**, leave this as **Optional**.

    5.  Expand **Advanced options** section.

    6.  In **Behavior**, select **Time zone independent**.

    7.  Click **Done**.

11. Create Code column

    1.  Click **Add column**.

    2.  Enter **Code** for **Display name**.

    3.  Select **Autonumber** for **Data type**.
    
    4.  Select **Date prefixed number** for **Autonumber type**.

    5.  Click **Done**.

12. Create Visitor lookup column

    1.  Click **Add column**.

    2.  Enter **Visitor** for **Display name**.

    3.  Select **Lookup** for **Data type**.

    4.  Select **Contact** for the **Related Table.**

    5.  Click **Done**.

13. Click **Save Table** in the bottom right.

# Exercise \#2: Import Data

**Objective:** In this exercise you will import sample data into the Dataverse
database.

## Task \#1: Import the Visits.xls file.

In this task you will import a solution that contains the Power Automate flow
required to complete data import.

1.  You should have the **Visits.xls** file stored on your Desktop. Download
    [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/majorupdate_april2022/Allfiles/Visits.xlsx)
    if you do not.

2.  If not already signed in, sign in to <https://make.powerapps.com>.

3.  Select your **[my initials] Practice** environment at the top right if it is
    not already selected.

4.  Using the navigation on the left, expand **Dataverse**, and select tables.

5.  Locate and open the **Visit** table, you created in the
    previous exercise.

6.  Using the menu at the top, select the drop-down arrow next to **Data**, select the arrow next to **Get data**, and then select **Get data from Excel**.

7.  From the menu that appears, select the **Upload** button.

8.  Locate and select the **Visits.xls** file you downloaded earlier. *(Note it
    can take a minute or two for the file to upload. Do not worry if you get a
    message that mapping errors exist, we will fix those next.)*

9. Select **Map columns.**

10. Map the Columns as noted below:

    | Visit Db columns | Source Values   |
    |------------------|-----------------|
    | Actual End       | Actual end      |
    | Actual Start     | Actual start    |
    | Code             | Code            |
    | Name             | Name            |
    | Scheduled End    | Scheduled end   |
    | Scheduled Start  | Scheduled start |

11. Leave all the rest of the fields to **Not Set**.

12. In the upper right corner of the screen, select **Save changes**.

13. On the **Import data** screen, verify that the mapping status says, Mapping
    was successful, and select the **Import** button.

**Note:** *It can take several minutes for your data to import into your table.
Don’t worry if you get a few errors, that is normal, and will not impact the
rest of the course.*

## Task \#2: Verify Data Import

1.  After your data has been imported, use the navigation at the left of the
    screen to select the **Visit** table again.

2.  Using the tabs on the top, select the Data tab.

3.  Verify that there are records in your table.

Congratulations, you have successfully created new tables and
imported data.
