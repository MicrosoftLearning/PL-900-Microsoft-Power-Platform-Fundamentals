---
lab:
    title: 'Lab 01: Data Modeling'
    module: 'TBD'
---

# PL-900: Microsoft-Power-Platform-Fundamentals
## Module X, Lab 1 – Data Modeling


Scenario
========

Bellows College is a large educational organization with facilities spread across multiple regions. College staff, students, and visitors need to access buildings on various campuses depending on their scheduled meetings and allocated workstations. 

Throughout this course you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the facilities across campuses and buildings. 

In this lab, you will set up an environment and create a solution to track your changes. You will also create a data model to support the following requirements:

-   R1 – Track the status of permits issued for new buildings and existing
    building modifications

-   R2 – Associate permits with a Build Site, which represents the building
    or land being modified

-   R3 – Track permit type to indicate the type of permit, any inspections, or other data
    that might be required on a permit

-   R4 – Track inspections completed on the permit for the
    entire process (i.e., from request of inspection to the pass or fail of the
    inspection)

-   R5 – Track the permit requestor 

High-level lab steps
======================

To prepare your learning environments you will create a solution and publisher, and add both new and existing components that are necessary to meet the application requirements. ~~Refer to the data model document for the metadata description (entities, field types and relationships)~~. Your solution will contain several entities upon completion of all the customizations:

-   Contact
-   Building
-   Appointment
-   User

Things to consider before you begin
-----------------------------------

* 

Exercise \#1: Create Environment and Solution
==================================================

**Objective:** In this exercise, you will create a working environment.

Task \#1: Create Environment
-----------------------------

1.  Sign in to <https://aka.ms/ppac>

2.  Select **Environments** and click **New** from the top menu. This will open
    a menu on the right-hand side of the window.

3.  Enter **Bellows College [Your Last Name]** for **Name**.

4.  Select **Production** in the dropdown for **Type.**

5.  Select your **Region**

6.  Enter the **Purpose** for creating this environment (Optional). Now, either
    follow (g) or (h) to configure the environment.

7.  Turn on the **toggle** to **create a database for this environment** if you
    wish to create the database along with this, otherwise this can be done once
    the environment is configured.

8.  Click **Next.**

9.  Select **Language** and **Currency**. For the purposes of these labs, the
    environments have **English** and **US dollars** (USD) selected.

10. Leave the **Enable Dynamics 365 apps** disabled for the purpose of these
    labs.

11. Leave the **Deploy Sample apps and data** disabled for the purpose of these
    labs.

12. Click **Save**.

13. Your environment may take a few minutes to provision. You can click the **Refresh** button to refresh the list. When the environment is provisioned, the **State** will change to Ready.

14. If you did not previously create your database, select your environment and click **Create my database**. Otherwise, skip this step.

    - Select **Currency** and **Language**. For the purposes of these labs, the
    environments have **US dollars** (USD) and **English** selected.

    - Click **Create my Database**.

Task \#2: Create Solution and Publisher
---------------------------------------

1.  Create Solution

    -   Sign in to <https://make.powerapps.com>

    -   Select your environment from the top drop-down menu.

    -   Select **Solutions** from the left menu and click **New Solution**.

    -   Enter **Campus Management** for **Display Name**.

2.  Create Publisher

    -   Click on the **Publisher** dropdown and select **+ Publisher**.

    -   Enter **Bellows College** for **Display Name** and **bc** for **Prefix**

    -   Click **Save and Close**.

3.  Complete the solution creation.

    -   Now, click on the **Publisher** dropdown and select the **Bellows College**
        publisher you just created.

    -   Enter **1.0.0.0** for **Version** and click **Create**.

Task \#3: Add Existing Entity
-----------------------------

1.  Click to open the **Campus Management** solution you just created.
2.  Click **Add Existing** and select **Entity**.
3.  Search for **Contact** and select it.
4.  Click **Next**.
5.  Click **Select Components**.
6.  Select the **Views** tab and select the **Active Contacts** view. Click
    **Add**.
7.  Click **Select Components** again.
8.  Select the **Forms** tab and select the **Contact** form.
9.  Click **Add**.
10. You should have **1 View** and **1 Form** selected. Click **Add** again.
    This will add the Contact entity to the newly created solution. Next, we
    will add the Appointment entity.
11.  Click **Add Existing** and select **Entity**.
12.  Search for **Appointment** and select it.
13.  Select the **Forms** tab and select the **Appointment** form.
14.  Click **Add**.
15.  You should have **1 Form** selected. Click **Add** again.
     This will add the Appointment entity to the newly created solution. Next, we
     will add the User entity.
16.  Click **Add Existing** and select **Entity**.
17.  Click **Select Components**.
18.  Search for **User** and select it.
19.  Click **Next**.
20.  **DO NOT** select any components. Click **Add**.
21.  Your solution should now have three entities: Appointment, Contact and User.

Exercise \#2: Create Entities and Relationships
========================================

**Objective:** In this exercise, you will create entities and add relationships
between entities.

Task #1: Create Building Entity and Fields
-----------------------------------------

1.  Continuing in your development environment, open the Campus Management
    solution
-   Sign in to <https://make.powerapps.com> (if you are not already signed in)
    
-   Select **Solutions** and click to open the **Permit Management**
        solution you just created (if you are not already in this Solution)
2.  Create Building entity

    -   Click **New** and select **Entity**.
-   Enter **Building** for **Display Name** and click **Create**. This will
        start provisioning the entity in background while you can start adding
        other fields.
3.  Click **Relationships**
4.  Click  **Add relationship** then select **One-to-many**
5.  Select Appointment as the entity in **Related (Many)** section
6.  Click **Done**
7.  Click **Save Entity**

Task #2: Create Relationships
------------------------------

1.  Sign in to <https://make.powerapps.com> if you are not already signed in.
2.  Select **Solutions**.
3.  Open the **Campus Management** solution.
4.  Create Appointment to Building relationship
    * Click to open the **Building** entity.
    * Select the **Relationships** tab.
    * Click **Add Relationship** and select **One-to-many**
    * Select Appointment for **Related (Many)** and click **Done**.
5. Click **Save Entity**.
6. Select **Solutions** from the top menu and click **Publish All
    Customizations.**

# Exercise \#3: Import Data

In this exercise you will import sample data into the Common Data Service



