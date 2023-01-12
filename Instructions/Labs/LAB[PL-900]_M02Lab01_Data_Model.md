---
lab:
    title: 'Lab 1: Data Modeling'
    module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Lab 1: Data Modeling

## Scenario

Bellows College is an educational organization with multiple buildings on
campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus.

In this lab you will access your environment, create a Microsoft Dataverse
database, and create a solution to track your changes. You will also create a data model to support the following requirements:

- R1 – Track information for scheduled campus visits

- R2 – Record basic information to identify and track the visitors

- R3 – Schedule, record, and manage visits

Finally, you will import sample data into Microsoft Dataverse.

## High-level lab steps

To prepare your learning environments you will:

- Refer to the [data model document](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) for the metadata description (tables and relationships). You can hold CTRL+click or right click the link to open the data model document in a new window.
- create Visit table
- import Visit data using an Excel spreadsheet

## Prerequisites

- Completion of **Module 0 Lab 0 - Validate lab environment**

## Things to consider before you begin

- Naming conventions - type names carefully.

## Exercise 1: Create New Table

**Objective:** In this exercise, you will create new custom table for Visits.

### Task \#1: Create Visit Table and Columns

The **Visit** table will contain information about the campus visits including the visitor, scheduled times and actual times of each visit.

We would like to assign each visit a unique number that can be easily entered and interpreted by a visitor when asked during the visit check-in process.

> We use **Time zone independent** behavior to record date and time information, because time of a visit is always local to the location of the  building and should not change when viewed from a different time zone.

1. Sign into [https://make.powerapps.com](https://make.powerapps.com/) (if you are not already signed in)

1. Select your **[my initials] Practice** environment at the top right if it is not already selected.

1. Using the navigation on the left, expand **Dataverse**, and select **Tables**.

1. Click **+ New table**.

1. Enter **Visit** for **Display Name**.

1. Click **Save**.

1. Under the **Schema** section, select **Columns**.

1. Create  Scheduled Start column

	- Select **+ New column**.

	- Enter **Scheduled Start** for **Display name**.

	- Select **Date and Time** for **Data type**.

	- In **Required**, select **Business required**.

	- Expand **Advanced options**.

	- In **Time zone adjustment**, select **Time zone independent**.

	- Click **Save**.

1. Create Scheduled End column

	- Click **+ New column**.

	- Enter **Scheduled End** for **Display name**.

	- Select **Date and Time** for **Data type**.

	- In **Required**, select **Business required**.

	- Expand **Advanced options**.

	- In **Time zone adjustment**, select **Time zone independent**.

	- Click **Save**.

1. Create Actual Start column

	- Click **+ New column**.

	- Enter **Actual Start** for **Display name**.

	- Select **Date and Time** for **Data type**.

	- In **Required**, leave this as **Optional.**

	- Expand **Advanced options**.

	- In **Time zone adjustment**, select **Time zone independent**.

	- Click **Save**.

1. Create Actual End column

	- Click **+ New column**.

	- Enter **Actual End** for **Display name**.

	- Select **Date and Time** for **Data type**.

	- In **Required**, leave this as **Optional**.

	- Expand **Advanced options**.

	- In **Time zone adjustment**, select **Time zone independent**.

	- Click **Save**.

1. Create Code column

	- Click **+ New column**.

	- Enter **Code** for **Display name**.

	- Select **Autonumber** for **Data type**.

	- Select **Date prefixed number** for **Autonumber type**.

	- Click **Save**.

1. Create Visitor lookup column

	- Click **+ New column**.

	- Enter **Visitor** for **Display name**.

	- Select **Lookup** for **Data type**.

	- Select **Contact** for the **Related Table**.

	- Expand **Advanced options**.

	- Enter **visitor_id** for **Relationship name**.

	- Click **Save**.

## Exercise 2: Import Data

**Objective:** In this exercise you will import sample data into the Dataverse database.

### Task \#1.1: Load Excel file to OneDrive

1. You should have the **Visits.xlsx** file stored on your virtual machine in **C:/LabFiles**. Download [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) if you do not.

2. If not already signed in, sign in to [https://make.powerapps.com](https://make.powerapps.com/).

3. Select your **[my initials] Practice** environment at the top right if it is not already selected.

4. Click on the Waffle button in the upper left corner to change applications and select **OneDrive**. (It may take a moment for your OneDrive to be set up. Click **Your OneDrive is ready** when you see it on the screen.)

5. Click **Upload** from the top menu and select **Files**.

6. Locate and select the **Visits.xlsx** file and click **Open**.

 **Note:** This file is located in the **All Files** folder on your machine.
 
### Task \#1.2: Create a dataflow

1. If not already signed in, sign in to [https://make.powerapps.com](https://make.powerapps.com/).

2. Select your **[my initials] Practice** environment at the top right if it is not already selected.

3. Using the navigation on the left, expand **Dataverse**, and select **Tables**.

4. Locate and open the **Visit** table you created in the previous exercise.

5. Using the menu at the top, select the drop-down arrow next to **Import**, select the **Import data**.

6. In the **Choose data source** dialog, select **Excel workbook**.

7. Select **Link to File** option. Click **Browse OneDrive**. If prompted, sign in with your Microsoft 365 credentials.

8. Select the **Visits.xlsx** file which has been uploaded in OneDrive and click **Select**.

9. Click **Next**.

10. Under **Choose Data** check the box next to the **Visits** Excel workbook.

11. Click **Next**. Do not navigate away from this page.

12. Click **Next**.

13. On the **Map tables** section, select **Load to existing table** under the **Load settings**.

14. On the **Destination table** drop-down menu, Select the table name starts with **crXXX_visit** (where XXX is a random set of letters and numbers)

15. On the **Column Mapping**. Map the Columns to their corresponding destination columns.

| Destination columns| Source values |
| - | - |
| crxxx_ActualEnd| actual end |
| crxxx_ActualStart| actual start |
| crxxx_Code| code |
| crxxx_Name| name |
| crxxx_ScheduledEnd| scheduled end |
| crxxx_ScheduledStart| scheduled start |

16. Click **Next**.

17. Select **Refresh manually**.

18. Click **Publish**.

**Note:** It can take several minutes for your data to import into your table. Don’t worry if you get a few errors, that is normal, and will not impact the rest of the course.

### Task \#3: Verify Data Import

1. After your data has been imported, use the navigation at the left of the screen to select the **Visit** table again.

2. Verify that you see the imported data under the **Visit columns and data** section.

Congratulations, you have successfully created a new table and imported data.
