---
lab:
    title: 'Lab 3: How to build a canvas app, Part 2'
    module: 'Module 3: Get started with Power Apps'
---

# Module 3: Get started with Power Apps
## Lab 3: How to build a canvas app, Part 2

Scenario
========

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus. 

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus. 

In part 2 of this lab, you will create design and build a Power Apps canvas app that the security personnel will use at the building entrances to quickly confirm and register the visitors.

High-level lab steps
======================

You will follow the below outline to design the canvas app:

-   Create the app using the phone form factor
-   Connect to Common Data Service as a data source
-   Capture the input (visitor code) and locate the visitor record
-   Configure a form viewer control to show the visitor information
-   Use a Common Data Service view to populate the gallery
-   Handle checking-in and checking-out process for a visitor


## Prerequisites

* Completion of **Module 0 Lab 0 - Validate lab environment**
* Completion of **Module 2 Lab 1 - Introduction to Common Data Service**

Things to consider before you begin
-----------------------------------

-   What information would a security officer need quick access to?
-   What should happen if visitor code is invalid
-   What should happen if the visitor arrives outside of the scheduled hours 

Exercise \#1: Create Security Canvas App
===============================

**Objective:** In this exercise, you will create a canvas app.

Task \#1: Create Canvas App
---------------------------

1.  Open your Campus Management solution.

    -   Sign in to <https://make.powerapps.com>

    -   If the Environment displayed in the top right is not your Practice environment, select your **Environment**. 

    -   Select **Solutions**.

    -   Click to open the **Campus Management** solution.
    
2.  Create new canvas application

    -   Click **New** and select **App \| Canvas App \| Phone Form Factor**.
        This will open the App Editor in a New window.
        
    -   Click **Skip** if presented with the Welcome to Power Apps Studio dialogue.
    
    -   Click **File** and select **Save As**.
    
    -   Check if **The cloud** is selected. Enter **[Your Last Name] Campus Security** for Name and
        click **Save**. This will make sure that the changes are not lost if the app closes unexpectedly.
        
    -   Click the back arrow at the top left (below Power Apps) to return to the app.

3.  Connect to data source (Visits)

    1.  Click **View \| Data sources**
    
    2.  Click **See all entities**
    
    3.  Select **Visits** and wait for the Visit entity to display under the Data **In your app** section.
    
4.  To preserve work in progress, click **File \| Save** then press **Save**

Task \#2: Display Visitor information
--------------------------------

1.  Add search box

    -   Select the **Tree View** tab on the left.
    
    -   Select **Screen1**.
    
    -   Go to the **Insert** tab.
    
    -   Click **Text** and select **Text input**.
    
    -   Select the text in the **Default** property and clear the value.
    
    -   Select **HintText** property and enter **"Enter visitor code"** as the value (including double quotes)
    
    -   Click on **...** next to control name in a tree view, select **Rename**, change the name to **textCode**
    
2. Add form view

   -   On **Insert** tab click **Forms**  then select **Display**
   
   -   Using size handles, position the form below the search textbox
   
   -   Select **DataSource** property and enter **Visits**
   
   -   In properties pane select **Horizontal** as **Layout**
   
   -   Click **Edit fields**
   
   -   Click **Add field** and select the following fields: Actual End, Actual Start, Building, Scheduled End, Scheduled Start, Visitor
   
   -   Press **Add**
   
   -   Change the order of the selected fields by dragging the field cards in the list. Recommended order is Visitor, Building, Scheduled Start, Scheduled End, Actual Start, Actual End
   
   -   In the Advanced tab, select **Item** property and enter `LookUp(Visits, Code = textCode.Text)` 

3.  To preserve work in progress, click **File \| Save** then press **Save**. Click the back arrow at the top right (below "Power Apps") to return to the app.

4. Test the app

   -   Switch to the browser tab containing the solution
   
   -   Select **Visit** entity
   
   -   Select **Data** tab
   
   -   Open the View Selector in the top right by clicking the current View name (Active Visits)
   
   -   Change the View to **All fields**
   
   -   Locate a Visit record that does not have an Actual Start or Actual End value. Select and copy the **Code** for this Visit.
   
   -   Switch to the browser tab with the app, press F5 to run the app
   
   -   Paste the copied value into the search textbox, verify that the record is displayed in the form
   
   -   Clear the search textbox contents.
   
5.  Press **ESC** to exit the running app.


Task \#3: Add Check In and Check Out Buttons
---------------------------------------

1. Save search results in a variable to reuse across the control

   * Select **textCode** control
   
   * Select **OnChange** property in the Advanced tab
   
   * Enter the following expression `Set(Visit, LookUp(Visits, Code = textCode.Text))`
     It is the same expression as above except this time we save results in a global variable. That allows us to use the variable *Visit* throughout the app without the need to re-enter the entire lookup expression.

2. Add buttons for checking in and checking out
   
   1. Select **Insert** tab
   
   2. Click **Button**
   
   3. Change the button **Text** property to **"Check In"** (you can type within the existing quotes)
   
   4. Rename the button as **CheckInButton** by clicking the button name (Button1) in the right panel
   
   5. Click **Button** to insert another button
   
   6. Change the button **Text** property to **"Check Out"**
   
   7. Rename the button as **CheckOutButton**
   
   8. Position the buttons side by side below the record form view 
   
3. Enable and disable buttons depending on visit data. 
   We would like to enable **Check In** button when the visit record has been located (not blank), record status is active, and the visit has not started yet, i.e. the actual start value is blank.

   * Select the Check In button and click on the **DisplayMode** property of the button in the Properties tab

   * Enter the expression below in the function bar.

      ```
      If(!IsBlank(Visit) 
      && Visit.Status = 'Status (Visits)'.Active
      && IsBlank(Visit.'Actual Start'),
          DisplayMode.Edit,
          DisplayMode.Disabled
      )
      ```

   The expression can be broken down as following:

   * `!IsBlank(Visit)` - visit record was found
   * `&&` - logical AND operator
   * `Visit.Status = 'Status (Visits)'.Active` status of the record is *Active*
   * `IsBlank(Visit.'Actual Start')` - Active Start field does not have any data in it

4. We would like to enable **Check Out** button when the visit record has been located (not blank), record status is active, and the visit has already started, i.e. the actual start value is not blank.

   * Select the Check Out button and click on the **DisplayMode** property of the button in the Properties tab

   * Enter the expression below in the function bar.

     ```
     If(!IsBlank(Visit) 
     && Visit.Status = 'Status (Visits)'.Active
     && !IsBlank(Visit.'Actual Start'),
         DisplayMode.Edit,
         DisplayMode.Disabled
     )
     ```

5. To preserve work in progress, click **File \| Save** then press **Save**. Click the back arrow at the top right (below "Power Apps") to return to the app.

6. Press **F5** to run the app. Both buttons should be disabled. Enter the code value you copied previously and press **Tab** to move the focus away from the textbox. The **Check In** button should become enabled.

7. Press **ESC** to exit the running app.

## Task #4: Complete Check In and Check Out Process

To perform the check in and check out process we need to update Common Data Service visit data as following:

* When visitor checks in, set *Actual Start* field to the current date and time
* When visitor checks out, set *Actual End* field to the current date and time. 
* After check out, set the record status to inactive, indicating that the visit has been completed

1. Select **Check In** button.

2. Set **OnSelect** property  to the following expression.

   ```
   Patch(
       Visits,
       Visit,
       {'Actual Start': Now()}
   );
   Refresh([@Visits]);
   Set(Visit, LookUp(Visits, Code = textCode.Text));
   ```

   This expression contains the following parts:

   * `Patch(Visits, Visit, {'Actual Start': Now()});`. *Patch* method updates **Visits** entity, the record identified by **Visit** variable (which is the current visit). The expression sets the value of *Actual Start* field to the current date and time (*Now()* method).
   * `Refresh([@Visits]);`. This expression refreshes the visit records as the underlying values have changed
   * `Set(Visit, LookUp(Visits, Code = textCode.Text));` This expression updates the *Visit* variable with fresh data from CDS.

3. Select **Check Out** button.

4. Set **OnSelect** property  to the following expression.

   ```
   Patch(
       [@Visits],
       Visit,
       {
           'Actual End': Now(),
           Status: 'Status (Visits)'.Inactive
       }
   );
   Refresh([@Visits]);
   Set(Visit, LookUp(Visits, Code = textCode.Text));
   ```

   The only difference from check in expression is setting of the *Status* field to *Inactive* value.

5. To preserve work in progress, click **File \| Save** then press **Save**.

6. Press **F5** to run the app. Enter the code value you copied previously and press **Tab** to move the focus away from the textbox. The **Check In** button should become enabled.

7. Press **Check In** button. The following should happen:

   1. *Actual Start* has a current date and time
   
   2. **Check In** button is disabled
   
   3. **Check Out** button is enabled

8. Press **Check Out** button.

   1. *Actual End* has a current date and time
   
   2. Both buttons are disabled

9. Press **ESC** to exit the running app.

Task \#5: Add visual indicators
--------------------------------------

Usability of a mobile app significantly improves when, in addition to the text information, the visual indicators are provided. In this task, we will add an icon indicating if a visitor can be checked in or checked out.

1. Select **Insert** tab

2. Select **Icons \| Add**. At this point it does not matter which icon we select as we want the value to be dynamic.

3. Resize and place the icon in the middle of the screen below the buttons

4. In the Advanced tab for the Icon, select **Icon** property (in the Design section) and enter the following expression

   ```
   If(
      CheckInButton.DisplayMode = DisplayMode.Disabled 
   && CheckOutButton.DisplayMode = DisplayMode.Disabled,
       Icon.EmojiFrown,
       Icon.EmojiSmile
   )
   ```

5. To preserve work in progress, click **File \| Save** then press **Save**.

6. Press **F5** to run the app. Enter the code value you copied previously and press **Tab** to move the focus away from the textbox. Verify the icon displays a frown emoji.

7. Find a different code value that has not been used before (it should not have an Actual Start or Actual End value). At this time, you can run **Campus Staff** app created previously to create new visit records. Verify the icon displays a smile emoji.

8. Press **ESC** to exit the running app.

## Task #6: Publish the app

1. You should still have the Campus Security app open in your browser. If not, select **Campus Security** app and click **Edit**.

2. Select **File \| Publish** 

3. Select **Publish this version**

# Challenges

* Avoid manual entry of the visit code
* Add building validation for the visit
* Add validation of the visit actual time vs visit scheduled time (too early, too late, etc)
* Add detailed status of the visit, e.g. email display and validation for the visitor, reason for denying building access, etc
* Multiple buildings/meetings/checkings during a single campus visit. For example, someone may visit campus for a day and during that day they will meet staff members in multiple buildings at different time of the day. Would you consider bringing *appointment* entity into the soluton?
