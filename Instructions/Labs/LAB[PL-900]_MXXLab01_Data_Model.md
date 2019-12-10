---
lab:
    title: 'Lab 01: Data Modeling'
    module: 'TBD'
---

# PL-900: Microsoft-Power-Platform-Fundamentals
## Module X, Lab 1 – Data Modeling


Scenario
========

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently and there are no means to collect and analyze data about the visits across the entire campus. 

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus. 

In this lab, you will set up an environment, create Common Data Service database, and create a solution to track your changes. You will also create a data model to support the following requirements:

-   R1 – Track the locations (buildings) of the campus visits
    
-   R2 – Record basic information to identify and track the visitors 
    
-   R3 – Schedule, record, and manage visits 
    

High-level lab steps
======================

To prepare your learning environments you will create a solution and publisher, and add both new and existing components that are necessary to meet the application requirements. ~~Refer to the data model document for the metadata description (entities, field types and relationships)~~. Your solution will contain several entities upon completion of all the customizations:

-   Contact
-   Building
-   Visit

## Prerequisites



Things to consider before you begin
-----------------------------------



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

6.  Enter the **Purpose** for creating this environment (Optional). 
    
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
    This will add the Contact entity to the newly created solution. 
21.  Your solution should now have one entity: Contact.

Exercise \#2: Create Entities and Relationships
========================================

**Objective:** In this exercise, you will create entities and add relationships
between entities.

Task #1: Create Building Entity and Fields
-----------------------------------------

1.  Continuing in your development environment, open the Campus Management
    solution
    * Sign in to <https://make.powerapps.com> (if you are not already signed in)
    * Select **Solutions** and click to open the **Campus Management**
          solution you just created (if you are not already in this Solution)
2.  Create Building entity

    -   Click **New** and select **Entity**.
    -   Enter **Building** for **Display Name** and click **Create**. This will
            start provisioning the entity in background while you can start adding
            other entities and fields.

## Task #2: Create Visit Entity and Fields

**Visit** entity will contain information about the campus visits including the building, visitor, scheduled and actual time of each visit. 

We would like to assign each visit a unique number that can be easily entered and interpreted by a visitor when asked during the visit check-in process.

> [!NOTE]
> We use **Time zone independent** behavior to record date and time information because time of a visit is *always* local to the location of the building and should not change when viewed from a different time zone. 

1.  Select **Campus Management** solution
2. Create Visit entity

   * Click **New** and select **Entity**.
   * Enter **Visit** for **Display Name** and click **Create**. This will start provisioning the entity in background while you can start adding other fields.

3. Create Scheduled Start field

   * Make sure you have the **Fields** tab selected and click **Add Field**.
   * Enter **Scheduled Start** for **Display Name**.
   * Select **Date and Time** for **Data Type**.
   * Check the **Required** checkbox.
   * Expand **Advanced** section.
   * Select **Time zone independent** for **Behavior**.
   * Click **Done**.

4.  Create Scheduled End field

    * Click **Add Field**.
    * Enter **Scheduled End** for **Display Name**.
    * Select **Date and Time** for **Data Type**.
    * Check the **Required** checkbox.
    * Expand **Advanced** section.
    * Select **Time zone independent** for **Behavior**.
    * Click **Done**.
6.  Create Actual Start field
    * Click **Add Field**.
    * Enter **Actual Start** for **Display Name**.
    * Select **Date and Time** for **Data Type**.
    * Expand **Advanced** section.
    * Select **Time zone independent** for **Behavior**.
    * Click **Done**.
7.  Create Actual End field
    * Click **Add Field**.
    * Enter **Actual End** for **Display Name**.
    * Select **Date and Time** for **Data Type**.
    * Expand **Advanced** section.
    * Select **Time zone independent** for **Behavior**.
    * Click **Done**.
7.  Create Code field
    * Click **Add Field**.
    * Enter **Code** for **Display Name**.
    * Select **Autonumber** for **Data Type**.
    * Select **Date prefixed number** for **Autonumber type**.
    * Click **Done**.
8.  Click **Save Entity**

Task #3: Create Relationships
------------------------------

1.  Select the **Campus Management** solution.
4.  Create Visit to Contact relationship
    * Click to open the **Visit** entity.
    * Select the **Relationships** tab.
    * Click **Add Relationship** and select **Many-to-one**
    * Select Contact for **Related (One)** 
    * Enter **Visitor** for **Lookup field display name** 
    * Click **Done**.
3.  Create Visit to Building relationship
    * Click to open the **Visit** entity.
    * Select the **Relationships** tab.
    * Click **Add Relationship** and select **Many-to-one**
    * Select Building for **Related (One)** 
    * Click **Done**.
4.  Click **Save Entity**.
5.  Select **Solutions** from the top menu and click **Publish All
    Customizations.**

# Exercise \#3: Import Data

In this exercise you will import sample data into the Common Data Service

TBC

