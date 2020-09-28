---
lab:
    title: 'Lab 5: Introduction to Power Apps portals'
    module: 'Module 3: Get started with Power Apps'
---

# Module 3: Get started with Power Apps

## Lab 5: Introduction to Power Apps portals

# Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Campus administration would like to provide the visitors with the information about the buildings on campus. The visitors will be able to view the buildings list on a website, which will be built using a Power Apps portal.

In this lab, you will provision a Power Apps portal and create a portals webpage that will show a listing of the buildings on campus.

# High-level lab steps

You will follow the below outline to design the Power Apps portal:

* A Power Apps portal needs to be provisioned in the Common Data Service environment.
* A webpage will be configured to show a list of the buildings.

## Prerequisites

* Completion of **Module 0 Lab 0 - Validate lab environment**
* Completion of **Module 2 Lab 1 - Introduction to Common Data Service**

## Things to consider before you begin

* Power Apps portals apps are always started from a template instead of a blank application. Once you provision a portal, it will already have pages, menus and a default theme.

# Exercise \#1: Provision a Power Apps portal

**Objective:** In this exercise, you will provision a Power Apps portal in your environment that will be accessible anywhere on the world wide web.

## Task \#1: Provision Power Apps portal

1.  Create new portal app.

    -   Sign in to <https://make.powerapps.com>

    -   If the **Environment** displayed in the top right is not your Practice environment, select your Environment.

    -   Click on the **Portal from blank** panel under **Make your own app**

2.  Provide new portal details

    -   Enter **Bellows College Visitors** as the portal **Name**

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

Exercise \#2: Create a Portal Webpage
===============================

**Objective:** In this exercise, you will create a new webpage that will display some static content as well as a list of buildings from the Common Data Service.

Task #1: Create a Webpage
--------------------------------

1.  Open Power Apps portals Studio

    -   Sign in to <https://make.powerapps.com> (you may still have this open in your tabs)

    -   Locate the app that has the **Type** of **Portal**

    -   Click on the ellipses (**...**) and choose **Edit**

2.  You are now in the Power Apps portals Studio. This is where you can modify and create portal content.

3.  Create a new page

    -   From the command bar, select **New page**

    -   Mouse over **Fixed layouts** and choose **Page with title**

4.  Modify the page properties

    -   In the properties pane, under **Display** change the **Name** from **New page (1)** to **Building Directory**, press the Tab key (to initiate auto-save)

    -   The title of the page should now read **Building Directory**

    -   In the **Partial URL** change the value to **building-directory**, press the Tab key (to initiate auto-save)

Task #2: Add Static Content
--------------------------------

1.  Add a section to the webpage

    -   On the canvas (area showing webpage), select the **Page Copy** section. This is the large box around the 2 sentences of text in the middle of your page.

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **Two columns section** from the **Section layout** area

2.  Add Static Text

    -   On the canvas (area showing webpage), select the left column

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **Text** from the **Portal components** area

    -   In the new text area, enter the following text:
          ```
          The following is the building directory.
          ```
    -   Select the text box above the one you just edited, and click **Delete** on the command bar to remove the default text.

3. Add an Image

    -   On the canvas (area showing webpage), select the right column

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **Image** from the **Portal components** area

    -   In the properties pane, click **Select an image**. Locate and select the **Product A.png**

4.  Click **Browse website** to view the page so far.  Notice that there is **Building Directory** option on the main menu.

Task #3: Add a List Component
--------------------------------

1.  Open Power Apps portals Studio

    -   Sign in to <https://make.powerapps.com> (you may still have this open in your tabs)

    -   Locate the app that has the **Type** of **Portal**

    -   Click on the ellipses (**...**) and choose **Edit**
    
2.  Edit the existing page you created earlier

    -   On the toolbelt (left hand side), choose the **Pages** option 

    -   Locate and select the **Building Directory** page you created earlier
    
3.  Add a list component

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **One column section** from the **Section layout** area (a section will appear below the image and text on the webpage)

    -   Select the new column section on the canvas

    -   On the toolbelt (left side), select the **Components** icon

    -   Choose **List** from the **Portal Components** area (a list component will appear in the new section)
    
4.  Configure the list component

    -   Select the list component on the canvas

    -   In the properties pane (right side), enter in **Buildings List** in the **Name** field

    -   In the **Entity** field, choose **Buildings** from the drop-down list

    -   In the **Views**, choose **Active Buildings**

    -   Leave the remaining default settings
    
5.  Click **Browse website** to view the page. You should see the list of Buildings from the Common Data Service appear on the webpage.

Exercise \#3: Change the Portal Theme
===============================

**Objective:** In this exercise, you will create a new theme that will alter the color scheme of your portal. 

Task #1: Create a Webpage
--------------------------------

1.  Open Power Apps portals Studio

    -   Sign in to <https://make.powerapps.com> (you may still have this open in your tabs)

    -   Locate the app that has the **Type** of **Portal**

    -   Click on the ellipses (**...**) and choose **Edit**
    
2.  Apply and customize a basic theme

    -   On the toolbelt (left side), select the **Components** icon
    
    -   Click the toggle for **Enable basic theme** to turn this feature on.
    
    -   On one of presets, click the ellipses (**...**) and choose **Customize**
    
    -   A copy of the basic theme has been created. 
    
    -   On the properties pane, play around with changing the colors and exploring the impact of these changes to your portal.
    
    -   Rename your theme
    
3.  Save your changes

    -   On the command bar, click **Sync Configuration**

Your app layout should look similar to the following structure:

![Sample buildings list](media/9-portallabresult.jpg)

# Challenges

* Create a different view of Buildings (changing filtering options and fields). You will need to select **Browse** from the Portal studio to see the changes.
* In the Portal studio, select the Source Code Editor icon `</>` to view the page source. If you are comfortable with HTML, make some modifications and view the results.
* On the toolbelt, click on the **Themes** icon and edit the CSS of your custom theme.
* Create a page with the **Form** component and modify a **List** component to add or edit Common Data Service records with the form.
* Enable **Entity Permissions** in a **List** component **Settings**, what happens to the data?
