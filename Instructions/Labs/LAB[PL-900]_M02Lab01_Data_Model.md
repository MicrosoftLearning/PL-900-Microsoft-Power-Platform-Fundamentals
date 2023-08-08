---
lab:
    title: 'Lab 1: Data Modeling'
    module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Lab 1: Data Modeling

**WWL Tenants - Terms of Use**
If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training. 
Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and are not eligible for extension. 
Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time. 

## Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus.

In this lab you will create a data model to support the following requirements:

- R1 – Track information for scheduled campus visits.

- R2 – Record basic information to identify and track the visitors.

- R3 – Schedule, record, and manage visits.

Finally, you will import sample data into Microsoft Dataverse.

High-level lab steps

To prepare your learning environments you will:

- Refer to the [data model document](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) for the metadata description (tables and relationships). You can hold ctrl + left-click or right-click the link to open the data model document in a new window.
- Create Visit table
- Import Visit data using an Excel spreadsheet


## Prerequisites

- Completion of **Module 0 Lab 0 - Validate lab environment**

Things to consider before you begin

- Naming conventions - type names carefully.

Exercise 1: Create New Table

**Objective:** In this exercise, you will create new custom table for Visits.

Task #1: Create Visit Table and Columns

The **Visit** table will contain information about the campus visits including the visitor, scheduled times and actual times of each visit.

We would like to assign each visit a unique number that can be easily entered and interpreted by a visitor when asked during the visit check-in process.

1.  If you are not already signed in, sign into <https://make.powerapps.com> 

1.  From the **Environment** menu in the top right, ensure your **Practice** environment is selected. 

1.  Using the navigation on the left, select **Tables**.

1.  Select **+ New table** and choose **+ New table**. 

1.  For **Display name**, enter `Visit`

1.  Select **Save**. 

1.  Under the **Schema** section, select **Columns**. 

# Create Scheduled Start column

1.  Select **+ New column**. 

1.  Enter `Scheduled Start` for **Display name**. 

1.  Select **Date and time** for **Data type**. 

1.  Change **Required**, to **Business required**. 

1.  Expand **Advanced options**. 

1.  In **Time zone adjustment**, select **Time zone independent**. 

    > **Note:** We use **Time zone independent** behavior to record date and time information, because the time of a visit is always local to the location of the building and should not change when viewed from a different time zone. 

1.  Select **Save**. 

# Create Scheduled End column

1.  Select **+ New column**. 

1.  Enter `Scheduled End` for **Display name**.

1.  Select **Date and time** for **Data type**.

1.  In **Required**, select **Business required**.

1.  Expand **Advanced options**.

1.  In **Time zone adjustment**, select **Time zone independent**.

1.  Select **Save**. 

# Create Actual Start column

1.  Select **+ New column**. 

1.  Enter `Actual Start` for **Display name**.

1.  Select **Date and Time** for **Data type**.

1.  In **Required**, leave this as **Optional**.

1.  Expand **Advanced options**.

1.  In **Time zone adjustment**, select **Time zone independent**. 

1.  Select **Save**. 

# Create Actual End column

1.  Select **+ New column**.

1.  Enter **Actual End** for **Display name**.

1.  Select **Date and Time** for **Data type**.

1.  In **Required**, leave this as **Optional**.

1.  Expand **Advanced options**.

1.  In **Time zone adjustment**, select **Time zone independent**.

1.  Select **Save**.

# Create Code column

1.  Select **+ New column**.

1.  Enter `Code` for **Display name**.

1.  Select **Autonumber** for **Data type**.

1.  Select **Date prefixed number** for **Autonumber type**.

1.  Select **Save**. 

# Create Visitor lookup column

1.  Select **+ New column**.

1.  Enter `Visitor` for **Display name**.

1.  Select **Lookup** for **Data type**. 

1.  Select **Contact** for the **Related Table**. 

1.  Expand **Advanced options**. 

1.  Enter `visitor_id` for **Relationship name**. 

1.  Select **Save**.


Exercise 2: Import Data

**Objective:** In this exercise you will import sample data into the Dataverse database.

### Task \#1: Load Excel file to OneDrive

1.  You should have the **Visits.xlsx** file stored on your virtual machine in **C:/LabFiles**. Download [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) if you do not.

2.  If not already signed in, sign in to [https://make.powerapps.com](https://make.powerapps.com/). 

3.  Select your **[my initials] Practice** environment at the top right if it is not already selected.

4.  Select the Waffle button in the upper left corner to change applications and select **OneDrive**. (It may take a moment for your OneDrive to be set up. Select **Your OneDrive is ready** when you see it on the screen.)

5.  Select **Upload** from the top menu and select **Files**.

6.  Locate and select the **Visits.xlsx** file and select **Open**.

    > **Note:** This file is located in the **All Files** folder on your machine.


### Task \#2: Create a dataflow

1.  If you are not already signed in, sign into <https://make.powerapps.com> 

2.  From the **Environment** menu in the top right, ensure your **Practice** environment is selected. 

3.  Using the navigation on the left, select **Tables**. 

4.  Open the **Visit** table created in the previous exercise. 

5.  Using the menu at the top, select **Import** > **Import data**.

6.  In the **Choose data source** dialog, select **Excel workbook**.

7.  Select **Link to File** option. Select **Browse OneDrive**. If prompted, sign in with your Microsoft 365 credentials. Configure the browser to always allow pop-ups. 

8.  Select the **Visits.xlsx** file which was uploaded to OneDrive in the previous task. 

9.  Select **Next**. 

10. On the **Power query** > **Choose data** screen, check the **Visits** Excel workbook. 

11. Select **Next**. Do not navigate away from this page.

12. Select **Next**. 

13. On the **Map tables** section, under **Load settings**, select **Load to existing table**. 

14. On the **Destination table** drop-down menu, select the table **crXXX_Visit** (Where XXX is a random set of letters and numbers)

15. On the **Column Mapping** section, map the Columns to their corresponding destination columns:

    | Destination columns  | Source values   |
    |:---------------------|:----------------|
    | crxxx_ActualEnd      | actual end      |
    | crxxx_ActualStart    | actual start    |
    | crxxx_Code           | code            |
    | crxxx_Name           | name            |
    | crxxx_ScheduledEnd   | scheduled end   |
    | crxxx_ScheduledStart | scheduled start |

16. Select **Next**. 

17. Select **Refresh manually**. 

18. Select **Publish**. 

    > **Note:** It can take several minutes for your data to import into your table. Don’t worry if you get a few errors, that is normal, and will not impact the rest of the course.


Task #3: Verify Data Import

1.  After your data has been imported, use the navigation at the left of the screen to select **Tables** and open the **Visit** table.

2.  Verify that you see the imported data under the **Visit columns and data** section.

Congratulations, you have successfully created a new table and imported data.

