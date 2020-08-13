---
lab:
    title: 'Lab: Data Modeling'
    module: 'Module 2: Introduction to the Common Data Service'
---

# Module 2: Introduction to the Common Data Service
## Lab: Data Modeling


Scenario
========
    
Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus. 

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus. 

In this lab, you will access your Practice environment from the previous lab, create a Common Data Service (CDS) database, and create a solution to track your changes. You will also create a data model to support the following requirements:

-   R1 – Track the locations (buildings) of the campus visits
-   R2 – Record basic information to identify and track the visitors 
-   R3 – Schedule, record, and manage visits 

Finally, you will import sample data into Common Data Service.

High-level lab steps
======================

To prepare your learning environments you will:

* create a solution and publisher
* add both new and existing components required to meet the application requirements. Refer to the [data model document](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Labs/Campus%20Management.png) for the metadata description (entities and relationships). You can hold CTRL+click or right click the link to open the data model document in a new window.

Your solution will contain several entities upon completion of all the customizations:

-   Contact
-   Building
-   Visit

## Prerequisites:

* Completion of **Module 0 Lab 0 - Validate lab environment**

Things to consider before you begin:
-----------------------------------

* Naming convention
* Data types, restrictions (e.g. max length of a name)
* Datetime formatting to support easy localization
* Record the characters before the "@" symbol in your email address - it should be a first name and a last initial. These characters will become your "alias" throughout the course. Write them down somewhere you will be able to access throughout the course. 
* **Important:** Please be aware that this tenant and the Dynamics 365 organization will be shared with the other students in your classroom, like employees would share a tenant when using the Dynamics 365 instance belonging to their organization. Do not use any PII (personally identifiable information) when creating records. It is also good practice to use your username prefix (ex., **mollyc**) in front of all records, data, apps, workflows, etc. you create. 

Exercise \#1: Create Solution
==================================================

Task \#1: Create Solution and Publisher
---------------------------------------

1.  Create Solution

    -   Navigate to <https://make.powerapps.com>. You may need to reauthenticate - click **Sign in** and follow instructions if needed.

    -   Select your environment by clicking on **Environment** on the upper right corner of the screen and choosing your environment from the drop-down menu.

    -   Select **Solutions** from the left menu and click **New Solution**.

    -   Enter **[Your Last Name] Campus Management** for **Display Name**.

2.  Create Publisher

    -   Click on the **Publisher** dropdown and select **+ Publisher**.

    -   In the window that pops up, enter **Bellows College** for **Display Name** and **bc** for **Prefix**

    -   Click **Save and Close**. 
    
    -   Click **Done** in the pop-up window.

3.  Complete the solution creation.

    -   Now, click on the **Publisher** dropdown and select the **Bellows College**
        publisher you just created.

    -   Validate that **Version** is set to **1.0.0.0** 
    
    -   Click **Create**.

Task \#2: Add Existing Entity
-----------------------------

1.  Click to open your **Campus Management** solution you just created.
2.  Click **Add Existing** and select **Entity**.
3.  Locate **Contact** and select it.
4.  Click **Next**.
5.  Click **Select Components**.
6.  Select the **Views** tab and select the **Active Contacts** view. Click
    **Add**.
7.  Click **Select Components** again.
8.  Select the **Forms** tab and select the **Contact** form.
9.  Click **Add**.
10. You should have **1 View** and **1 Form** selected. Click **Add**.
    This will add the Contact entity with the selected View and Form to the newly created solution. 
11.  Your solution should now have one entity: Contact.

Exercise \#2: Create Entities and Relationships
========================================

**Objective:** In this exercise, you will create entities and add relationships
between the entities.

Task #1: Create Building Entity and Fields
-----------------------------------------

1.  You should still have your browser open to your Campus Management solution. If not, open the Campus Management solution by following these steps:
    * Sign in to <https://make.powerapps.com> (if you are not already signed in)
    * Select **Solutions** and click to open the **[Your Last Name] Campus Management**
          solution you just created.
2.  Create Building entity

    -   Click **New** and select **Entity**.
    -   Enter **Building** for **Display Name** 
    -   Click **Done**. This will
            start provisioning the entity in background while you can start adding
            other entities and fields.

## Task #2: Create Visit Entity and Fields

The **Visit** entity will contain information about the campus visits including the building, visitor, scheduled and actual time of each visit. 

We would like to assign each visit a unique number that can be easily entered and interpreted by a visitor when asked during the visit check-in process.

> [NOTE]
> We use **Time zone independent** behavior to record date and time information because time of a visit is *always* local to the location of the building and should not change when viewed from a different time zone. 

1.  Select your **Campus Management** solution
2. Create Visit entity

   * Click **New** and select **Entity**.
   * Enter **Visit** for **Display Name** 
   * Click **Done**. This will start provisioning the entity in background while you can start adding other fields.

3. Create Scheduled Start field

   * Make sure you have the **Fields** tab selected and click **Add Field**.
   * Enter **Scheduled Start** for **Display Name**.
   * Select **Date and Time** for **Data Type**.
   * In the **Required** field, select **Required**.
   * Expand **Advanced options** section.
   * In the **Behavior** field, select **Time zone independent**.
   * Click **Done**.

4.  Create Scheduled End field

    * Click **Add Field**.
    * Enter **Scheduled End** for **Display Name**.
    * Select **Date and Time** for **Data Type**.
    * In the **Required** field, select **Required**.
    * Expand **Advanced options** section.
    * In the **Behavior** field, select **Time zone independent**.
    * Click **Done**.
    
6.  Create Actual Start field

    * Click **Add Field**.
    * Enter **Actual Start** for **Display Name**.
    * Select **Date and Time** for **Data Type**.
    * Expand **Advanced options** section.
    * In the **Behavior** field, select **Time zone independent**.
    * Click **Done**.
    
7.  Create Actual End field

    * Click **Add Field**.
    * Enter **Actual End** for **Display Name**.
    * Select **Date and Time** for **Data Type**.
    * Expand **Advanced options** section.
    * In the **Behavior** field, select **Time zone independent**.
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

1.  Ensure that you are still viewing the **Visit** entity of your **Campus Management** solution. If not, navigate there.
2.  Create Visit to Contact relationship
    * Select the **Relationships** tab.
    * Click **Add Relationship** and select **Many-to-one**
    * Select **Contact** for **Related (One)** 
    * Enter **Visitor** for **Lookup field display name** 
    * Click **Done**.
3.  Create Visit to Building relationship
    * Click **Add Relationship** and select **Many-to-one**
    * Select **Building** for **Related (One)** 
    * Click **Done**.
4.  Click **Save Entity**.
5.  Select **Solutions** from the top menu and click **Publish all customizations.**

# Exercise \#3: Import Data

**Objective:** In this exercise you will import sample data into the Common Data Service database.

## Task #1: Import Data Map

1. Download [CampusDataMap.xml](../../Allfiles/Labs/CampusDataMap.xml) if you have not already.
2. Navigate to Power Platform Admin Center at <https://admin.powerplatform.microsoft.com> and sign in.
3. Select your Bellows College environment.
4. Click **Settings** at the top.
5. Expand **Data Management** section, then select **Data Maps**. This will open import map screen in a new browser tab.
6. Click **Import**, then click **Choose File**. Locate and select **CampusDataMap.xml** downloaded earlier, and then press **OK**. 
7. The Campus Data Map file should successfully be imported. If you encounter an error, please go back and validate that you have created all of the required entities and fields from the previous tasks.
8. Navigate back to the browser window with <https://make.powerapps.com> open. Click **Solutions** from the top menu and click **Publish all customizations.**

## Task #2: Import Data  

1. Download [CampusData.zip](../../Allfiles/Labs/CampusData.zip).
2. Navigate to Power Platform Admin Center at <https://admin.powerplatform.microsoft.com>.
3. Select your Bellows College environment.
4. Click **Settings** at the top.
5. Expand **Data Management** section, then select **Data import wizard**.
6. Click **IMPORT DATA**.
7. Click **Choose File**, then locate and select **CampusData.zip** downloaded earlier.
8. Press **Next**, then press **Next** again.
9. Select **CampusImportDataMap**, press **Next**.
10. Review mapping summary, then press **Next**, and then press **Submit**.
11. Press **Finish**.
12. The data import will now begin. You can now use the Refresh button on the right side of the My Imports screen to refresh the table until all four imports have a **Status Reason** of **Completed**. This may take a few minutes.

## Task #3: Verify Data Import

1. Select the **Campus Management** solution. If you do not still have this open, navigate to <https://make.powerapps.com> and click Solutions on the left pane to locate your solution.
2. Click to open the **Visit** entity, then select the **Data** tab.
3. Click **Active Visits** in the top right-hand corner to display the view selector, then select **All fields**
4. If the import was successful, you should see a list of visit entries.
5. Click on any value in the **Building** column, confirm that the Building form opens in a separate window. Close this window.
6. Click on any value in the **Visitor** column (you may need to scroll the view to the right), confirm that the Contact form opens in a separate window. Close this window.

# Challenges

* Would you consider using *appointment* activity as part of the solution? What would it change?
* How could you enforce the scheduled end to be after the scheduled start? 
* How could you add support for multiple meetings during a single visit?
* How could you secure the building access not only for external contacts but for internal staff member as well?
* How could you make visits to certain buildings require management approval? What would the approval process change in the data model?

