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

-   Install Power Apps inside Teams

-   add both new and existing components required to meet the application
    requirements. Refer to the [data model
    document](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png)
    for the metadata description (tables and relationships). You can hold
    CTRL+click or right click the link to open the data model document in a new
    window.

Your solution will contain several tables upon completion of all the
customizations:

-   Contact

-   Building

-   Visit

## Prerequisites:

-   Completion of **Module 0 Lab 0 - Validate lab environment**

## Things to consider before you begin:

-   Naming convention

-   Data types, restrictions (e.g. max length of a name)

-   Datetime formatting to support easy localization

# Exercise \#1: Create a new Team in Microsoft Teams

## Task \#1: Create a Team

1.  In a browser, navigate to <https://Teams.microsoft.com> and sign in with
    your student credentials.

2.  In the lower left corner of the **Microsoft Teams** app, select **Join or
    create a Team**.

3.  In the **Join or create a team** screen, select **Create a Team**

4.  In the **Create** a team screen, select **From Scratch**

5.  In the **What kind of team will this be** screen, select **Public**

6.  In the **Name** screen, enter your initials followed by **Bellows College**.
    For example, it will look something like **DB Bellows College**.

7.  Select the **Create** button.

8.  On the **Add members** screen, select the **Skip** button

# Provision your first Dataverse Environment

## Task \#1: Add the Power Apps app to your Teams instance

1.  In a browser, navigate to <https://Teams.microsoft.com> and sign in with
    your student credentials.

2.  In the lower left corner of the screen, select the **Apps** Icon.

3.  On the **App Marketplace** Screen, use the search box to find and select
    **Power Apps**.

4.  Select the **Add** button to add the Power Apps application to your Teams
    Client.

## Task \#2: Provision Dataverse for Teams to Create a table

1.  If you are not already logged into Microsoft Teams with you student
    credentials, open your web browser, navigate to
    <https://Teams.microsoft.com> and sign in with your student credentials.

2.  Using the navigation on the left, select the **Ellipsis** icon **(More Added
    Apps)**.

3.  In the **Find an App** Screen, enter **Power Apps**, and select **Power
    Apps** to open it.

4.  To start creating an application, select **Start** Now

5.  On the **Select a Team for this app** screen, select the **Your Initials
    Bellows College** team that you created in a previous exercise.

6.  Select the **Create** button

NOTE: It can take several minutes for the application to be created. When your
environment is provisioned, a pop-up window will display in the lower-right
corner of your screen, letting you know that the process has finished.

1.  After the **Power Apps Editor** appears, name your app **Bellows College
    visit tracker “Your Initials”**.

2.  Select **Save**.

# Exercise \#2: Create tables to store data

**Objective:** In this exercise, you will add the standard Contact table and
create new custom tables for Buildings and Visits in the solution.

1.  With your **Visit tracker** open, select the **Data** icon on the left side
    of the screen.

2.  Select **Create** n**ew table** button.

3.  On the Create a table screen, enter **Contact** and select the **Create**
    button

4.  On the **Name** column, select the drop-down arrow next to name. From the
    menu that appear, choose **Edit Column**.

5.  Change the name to First Name, select **Save**.

6.  At the top of the screen select the **+ New Column** button.

7.  Configure the column as follows:

    1.  **Name:** Last Name

    2.  **Type:** Text

8.  Select the **Create** button.

9.  At the top of the screen select the **+ New Column** button again.

10. Configure the column as follows:

    1.  **Name:** Email

    2.  **Type:** Email

11. Select the **Create** button.

12. At the top of the screen select the **+ New Column** button again.

13. Configure the column as follows:

    1.  **Name:** Phone

    2.  **Type:** Phone

14. Select the **Create** button.

15. You Contacts table should resemble the Image below:

    ![](media/d838dda08873583d0e7156a2752e17b1.png)

16. Select the Close button in the lower right corner of the screen.

The **Visit** table will contain information about the campus visits including
the building, visitor, scheduled and actual time of each visit. We would like to
assign each visit a unique number that can be easily entered and interpreted by

## Task \#2: Create visit table

1.  You should still have your power app open from the previous exercise.

2.  Under the Data section, select the down arrow next to **Add Data**.

3.  From the menu that appears, select **Create new table**.

4.  In the create a table box, set the table name to **Visit**, and select
    **Create.**

5.  Once your Visit table is created, at the top of the screen select the **+
    New Column** button.

6.  Configure the column as follows:

    1.  **Name:** Data Scheduled

    2.  **Type:** Date

7.  Select the **Create** button.

8.  At the top of the screen select the **+ New Column** button again.

9.  Configure the column as follows:

    1.  **Name:** Actual Visit Data

    2.  **Type:** Date

10. Select the **Create** button.

11. At the top of the screen select the **+ New Column** button again.

12. Configure the column as follows:

    1.  **Name:** Visitor

    2.  **Type:** Lookup

    3.  **Related table:** Contact

13. Select the **Create** button.

14. At the top of the screen select the **+ New Column** button again.

15. Configure the column as follows:

    1.  **Name:** Code

    2.  **Type:** Auto number

16. Select the **Create** button.

17. Your completed Visit Table, should resemble the Image below:

    ![](media/16bd1bb3fd33f67c7545e96326f70028.png)

18. Select the Close button to save your table.

# Exercise \#3: Build a simple app

**Objective:** In this exercise, you will add relationships between the tables.

## Task \#1: Create Relationships

1.  One the screen, select **Build from Data**.

2.  Select the **Visit** table.

3.  Using the commands at the top left of the screen, select the **Save**
    button.

4.  Select the **Play** button.

5.  Using the navigation on the left, select **+ New Record**.

6.  Fill in the data as needed.

7.  Select the Check button on the right to save your changes.
