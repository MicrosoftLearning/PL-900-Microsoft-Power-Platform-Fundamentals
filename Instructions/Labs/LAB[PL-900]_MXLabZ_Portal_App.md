---
lab:
    title: 'Lab: Power Apps portals'
    module: 'Module X: Introduction to Power Apps portals'
---

# Module Z: Introduction to Power Apps portals

## Lab: Power Apps portals

# Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently and there are no means to collect and analyze data about the visits across the entire campus. 

Campus administration would like to provide the visitors with the information about the buildings on campus.  The visitors will be able to view the building list on a website, which will be built using a Power Apps portal.

In this lab, you will provision a Power Apps portal and create a portals web page that will show a listing of the buildings on campus.

# High-level lab steps

The following have been identified as requirements you must implement to complete the project.

* A Power Apps portal needs to be provisioned in the Common Data Service environment.
* A web page must show a listing of the Buildings.

## Prerequisites

* Completion of **Module 0 Lab 0 - Validate lab environment**
* Completion of **Module 2 Lab 1 - Data Modeling**

## Things to consider before you begin

-   Power Apps portals apps are always started from a template instead of a blank application.  Once you provision a portal, it will already have pages, menus and a default theme.

# Exercise \#1: Provision a Power Apps portal

**Objective:** In this exercise, you will provision a Power Apps portal on your environment that will be accessible anywhere on the world wide web.

## Task \#1: Provision Power Apps portal

1.  Create new portal app.

    -   Sign in to <https://make.powerapps.com>

    -   Select your **environment**

    -   Click on the **Portal from blank** panel under **Make your own app**

2.  Provide new portal details

    -   Give the portal a name (it can be anything you want)

    -   Provide a unique URL; **something**.powerappsportals.com (if the name has been taken, choose a different one)

    -   Select a base portal **Language**

    -   Click **Create**

3. The Portal provisioning process will run anywhere from 30 to 45 minutes.  Please be patient.

Task \#2: Navigate to Portal
--------------------------------

1.  You will get a notification in <https://make.powerapps.com> when the portal has been provisioned
2.  Open the new portal

    -   Click on **Apps**

    -   Locate the app that has the **Type** of **Portal**

    -   Click on the app name

3.  You should be redirected to a portal website with the landing page with a welcome message

Exercise \#2: Create a Portal Web Page
===============================

**Objective:** In this exercise, you will create a new web page that will display some static content as well as a list of buildings from the Common Data Service.

Task #1: Create a Page
--------------------------------

1.  Open the Portal studio

    -   Sign in to <https://make.powerapps.com>

    -   Locate the app that has the **Type** of **Portal**

    -   click on the ellipses (...) and choose **Edit**

2.  You are now in the Portals Studio.  This is where you can modify and create portal content

3.  Create a new page

    -   From the command bar, select **New page**

    -   Mouse over **Fixed layouts** and choose **Page with title**

4.  Modify the page properties

    -   In the properties pane, under **Display** change the **Name** from **New page (1)** to **Building Directory**, press the Tab key (to initiate auto-save)

    -   The title of the page should now read **Building Directory**

    -   In the **Partial URL** change the value to **building-directory**, press the Tab key (to initiate auto-save)

Task #2: Add Static Content
--------------------------------

1.  Add a section to the web page

    -   On the canvas (area showing web page), select the **Page Copy** section

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **Two columns section** from the **Section layout** area

2.  Add Static Text

    -   On the canvas (area showing web page), select the left column

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **Text** from the **Portal components** area

    -   In the new text area, enter in or paste in some text

3. Add an Image

    -   On the canvas (area showing web page), select the right column

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **Image** from the **Portal components** area

    -   Select the new image area

    -   In the properties pane, choose an existing **Image** and locate and select the **Product A.png**

4.  Click **Browse website** to view the page so far.  Notice that there is **Building Directory** option on the main menu.

Task #3: Add a List Component
--------------------------------

1.  Open the Portal studio

    -   Sign in to <https://make.powerapps.com>

    -   Locate the app that has the **Type** of **Portal**

    -   click on the ellipses (...) and choose **Edit**
2.  Edit the existing page you created earlier

    -   On the toolbelt (left hand side), choose the **Pages** option 

    -   Locate the **Building Directory** page you created earlier
3.  Add a the list component

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **One column section** from the **Section layout** area (a section will appear below the image and text on the web page)

    -   Select the new column section on the canvas

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **List** from the **Portal Components** area (a list component will appear in the new section)
4.  Configure the list component

    -   Select the list component on the canvas

    -   In the properties pane (right side), enter in **Buildings List** in the **Name** field

    -   In the **Entity** field, choose **Buildings** from the drop-down list

    -   In the **Views**, choose **Active Buildings**

    -   Leave the remaining default settings
5.  Click **Browse website** to view the page.  You should see the list of Buildings from the Common Data Service appear on the web page.

![Sample buildings list](media/9-portallabresult.jpg)

# Challenges

* Create a different view of Buildings (changing filtering options and fields).  You will need to select **Browse** from the Portal studio to see the changes.
* In the Portal studio, select the Source Code Editor icon `</>` to view the page source.  If you are comfortable with HTML, make some modifications and view the results.
* On the toolbelt, click on the Themes icon and play with different theme options.
* Create a page with the **Form** component, modify a **List** component to add or edit Common Data Service records.
* Enable **Entity Permissions** in a **List** component **Settings**, what happens to the data?