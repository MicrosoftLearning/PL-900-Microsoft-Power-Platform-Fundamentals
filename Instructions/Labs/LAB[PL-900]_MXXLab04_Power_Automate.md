---
lab:
    title: 'Lab 02: Canvas app'
    module: 'Module XX: Power Apps Build'
---

# PL-900: Microsoft-Power-Platform-Fundamentals
## Module X, Lab 2 – Canvas App

Scenario
========

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently and there are no means to collect and analyze data about the visits across the entire campus. 

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus. 

In this lab, you will create we will now design a PowerApps canvas app that the inspectors will use in the field on their mobile devices. Canvas apps are low code apps that can be designed for a tablet or mobile phone layouts. You will build a two-screen canvas app that allows inspectors quickly access and process the inspections.

High-level lab steps
======================

We will follow the below schema to design the canvas app:

-   Create the app using the tablet form factor

-   Connect to Common Data Service as a data source

-   Configure a gallery control to show the pending appointments

-   Use a CDS view to populate the gallery

-   Configure a detail page with appointment info

-   Handle checking-in the inspection results to CDS

-   Export the solution with the data model and apps and import it to the
    “Production” environment

The first screen in the application will show all Pending Inspections for the
logged in Inspector. The second screen lets the inspector update the selected
Inspection.

## Prerequisites



Things to consider before you begin
-----------------------------------

-   What information would a security officer need quick access to?

-   
    

Exercise \#1: Create Canvas App
===============================

**Objective:** In this exercise, you will create a canvas app.

Task \#1: Create Canvas App
---------------------------

1.  Open the Permit Management solution.

    -   Sign in to <https://make.powerapps.com>

    -   Select your **environment.**

    -   Select **Solutions**.

    -   Click to open the **Campus Management** solution.

2.  Create new canvas application

    -   Click **New** and select **App \| Canvas App \| Tablet Form Factor**.
        This will open the App Editor in a New window.

    -   If you are creating your first app, this will ask you to set the
        Country/region for the app. Click **Get Started.**

    -   Click File and select Save As.

    -   Check if **The Cloud** is selected. Enter **Inspector** for Name and
        click **Save**. This will make sure that the changes are not removed if
        the app closes unexpectedly.

3.  Enable Components for the application.

    -   Select **App Settings** and then select **Advanced Settings**.

    -   Scroll down and turn on **Components**.

    -   Click on the app designer back button.

4.  Rename Screen1.

    -   Go to the **Tree View** and double click on **Screen1**.

    -   Rename it MainScreen and press **Enter.**

5.  Import Component.

    -   Select the **Components** tab.

    -   Click on the **… (Component Options)** button and select Import
        **Components**.

    -   Click **Upload File**.

    -   Browser to the lab resources folder, select the **Components** file and
        click **Open**.

    -   Three components should be imported.

6.  Add the Header component to the MainScreen.

    -   Select the **Screens** tab.

    -   Select the **Insert** tab.

    -   Click **Custom** and select **Header**.

    -   Rename **Header_1** to **MainHeader** by double click on Header_1.

7.  Change the MainHeader properties

    -   Select **MainHeader**.

    -   Change the **Text** attribute of the **MainHeader** to **My Pending
        Inspections**. This can be done by selecting “Text” property in the
        dropdown below top menu. Make sure that you have selected the MainHeader
        control while doing this step.

    -   Change the **Width** vale of the **MainHeader** to the formula below.

               Parent.Width

Task \#3: Add Inspection Gallery
--------------------------------

1.  Add Gallery

    -   Select the **Tree View** tab

    -   Select the **MainScreen**.

    -   Go to the **Insert** tab.

    -   Click **Gallery** and select **Vertical**.

    -   Select **Inspections** for **Data Source**. When Inspection is selected,
        this will automatically pick the fields and show them in the gallery
        items.

    -   Rename **Gallery_1** to **InspectionList** by double click on Gallery_1.

2.  Select the inspector view

    -   Make sure you have the **InspectionList** control selected.

    -   Go to the **Properties** pan and select **Inspector View** for **View**.

3.  Change the **InspectionList** control layout

    -   Go to the **Properties** pane and click on the **Layout** dropdown.

    -   Select **Title and Subtitle**.

4.  Verify the selected fields.

    -   Go to the **Properties** pane and click on the **Edit Fields**.

    -   Confirm that Scheduled Date is selected for Subtitle1 and Name is
        selected for Tile1. Close the Data pane.

5.  Change date time to date only.

    -   Expand the **InspectionList** and select **Subtitle1**.

    -   Change the Text property of the control to the formula below.

            DateValue(Text(ThisItem.'Scheduled Date'),"en")

6.  Resize the Gallery

    -   Select the **InspectionList** gallery.

    -   Select **Width** property from the formula dropdown and enter the
        formula below.

            Parent.Width

    -   Select **Height** property and set it to the formula below.

            Parent.Height - (MainHeader.Height*2)

    -   Select the Y property from the dropdown and set it to formula below.

             MainHeader.Height

    -   Select the X property from the dropdown and set it to formula below.

            MainHeader.X

Task \#4: Add Inspection Details Screen
---------------------------------------

1.  Click **New Screen** and select **Blank**.

2.  Rename the new screen **DetailsScreen** by double click on the control in
    Tree View.

3.  Add Header to the DetailsScreen and edit it

    -   Go to the **MainScreen** and copy the **MainHeader**.

    -   Go to the **DetailsScreen** and paste the **Header**.

    -   Rename the Header you **DetailsHeader** by double click on the control
        in Tree View.

    -   Select te **Y** property of the **DetailsHeader** and set to **0**.

    -   Select the **Text** property of the **DetailsHeader** and set it to
        formula below.

               InspectionList.Selected.Name

1.  Add Form to the DetailsScreen.

    -   Select the **DetailsScreen**.

    -   Select the **Insert** tab.

    -   Click **Forms** and select **Edit**.

    -   Rename the form **InspectionForm**.

    -   Resize the Edit form as:

            1.  Select the **InspectionForm** gallery.
            
            2.  Select **Width** property from the formula dropdown and enter the
            formula below.  
            Parent.Width
            
            3.  Select **Height** property and set it to the formula below.  
            Parent.Height - (DetailsHeader.Height\*2)
            
            4.  Select the Y property from the dropdown and set it to formula below.  
            DetailsHeader.Height
            
            5.  Select the X property from the dropdown and set it to formula below.  
            DetailsHeader.X

2.  Set the **InspectionForm** data source

    -   Select the **InspectionForm** and select the DataSource as
        **Inspections** entity.

    -   Set the Item value to the formula below.

               InspectionList.Selected

3.  Edit InspectionForm fields. This adds the data cards for fields by default,
    but you can add/remove the data cards as:

    -   Select the **InspectionForm**.

    -   Go to the **Properties** pane and click **Edit Fields**.

    -   Click **Add Field**.

    -   Select **Name**, **Scheduled Date**, **Status Reason**, and
        **Comments**.

    -   Click **Add**.

    -   The fields should be arranged in the following order: Name, Scheduled Date, Status Reason, Comments. You can
        drag/drop to rearrange the fields.

4.  Go to the **Tree View** and expand the **InspectionForm**.

5.  Select the **Scheduled Date** data card.

6.  Go to the **Properties** pane and select the **Advanced** tab.

6.  Click **Unlock to change Properties**.

7.  Expand the **Scheduled Date** card.

8.  Select **StarVisible**, **ErrorMesage**, **MinuteValue**, **Separator**, and
    **HourValue**.

9.  Delete the selected controls. When the controls are deleted, you will be
    able to see an error message.

10.  Select the **DateValue** control.

11. Select the **Scheduled Date** DataCard.

12. Go to formula bar and select **Update**.

13. Remove everything after the **SelectedDate**. This should remove the error
    message from the app.

14. Select the **InspectionForm**. Then navigate to the **Properties** pane and click **Edit Fields**.

15. Expand the **Name** field.

16. Click on the **Control Type** dropdown and select **View Text**.

17. Expand the **Scheduled Date** field. Observe the change.

18. Notice we cannot change this the same way because we’ve customized it. From
    the Tree View select DateValue control inside the **Scheduled Date**
    Datacard and go to the **Advanced tab** of the **Properties pane**.

19. Search for DisplayMode property and remove the existing formula and place
    the following:

                DisplayMode.View

20. Close the **Fields** pane.

21. Change the Status Reason label.

    -   Select the **Status Reason data card**.

    -   Go to the **Properties** pane and the Advanced tab, click **Unlock to
        Change properties.**

    -   Change the **DisplayName** to **Inspection Result**.

22. Resize the Comments data card.

    -   Select the **Comments** data card.

    -   Click and drag the right edge to the far right of the screen.

    -   Go to the **Advanced** tab of **Properties** pane and click **Unlock to
        change properties**.

    -   Set the **Height** value to **300**.

    -   Select the **DataCardValue** control.

    -   Set the **Height** value to **300**.

    -   Change the **Mode** to the formula below.

               TextMode.MultiLine

23.  Save your work.

Task \#5: Submit the Inspection Result
--------------------------------------

1.  Add submit button to the details screen.

    -   Select the **DetailsScreen**. Make sure that you have not selected the
        Edit Form.

    -   Go to the **Insert** tab and click **Button**.

    -   Rename the button **SubmitButton**.

    -   Change the Text value of the button to **Submit**.

    -   Place the button below the form through drag and drop.

2.  Submit the inspection result.

    -   Select the **SubmitButton.**

    -   Set the **OnSelect** value of the submit button to the formula below.
        Remove the false expression and update it. This formula will submit the
        form and then navigate back to the MainScreen.

              SubmitForm(InspectionForm);Back(ScreenTransition.UnCoverRight)

3.  Add navigation from the main screen to the details screen.

    -   Go to the **MainScreen** and select the **InspectionList**.

    -   Set the **OnSelect** property of the **InspectionList** to the formula
        below. Remove the already existing false expression.

              Navigate(DetailsScreen, ScreenTransition.Cover)

Task \#6: Test Application
--------------------------

1.  Start the application

    -   Select the **MainScreen** and click **Preview the App**.

    -   The application should load and show at least one inspection. Click on
        the inspection.

    -   The application should navigate to the details screen. Change the
        **Inspection Result** to **Passed**, provide a comment in the textbox as
        “Frame Inspection was completed.”, and click **Submit**.

    -   The inspection should be submitted, and the application should navigate
        back to the MainScreen. Click Close.

2.  Save and publish the application

    -   Click **File** and then click **Save**.

    -   Click Publish.

    -   Click **Publish this Version**.

    -   Click **Close**.

    -   Close the **Designer** browser window or tab.

    -   Click **Leave** if prompted when tried to close the browser window.

    -   Navigate back to the previous window and Click **Done**.

3.  Confirm the inspection record was updated

    -   Select **Apps** and click to open the **Permit Management Application**.

    -   Select **Inspections** and click to open the **Framing Inspection**.

    -   The **Status Reason** of the inspection should be **Passed,** and the
        comment should be updated to the comment you provided.

    -   Close the **Permit Management** application.

Exercise \#2: Export/Import Solution
====================================

**Objective:** In this exercise, you will export the solution you created in the
development environment and import it to the production environment.

Task \#1: Export solution.
--------------------------

1.  Sign in to <https://make.powerapps.com>

2.  Make sure you have your **Dev** environment selected.

3.  Select **Solutions** and select the **Permit Management** solution.

4.  Click **Solution Checker** and select **Run**.

5.  **Note**: in some environments, you may be prompted to first install
    Solution checker. When **Install** is selected, this will open a new window.
    Follow the steps. It might take a few minutes to install the Solution
    checker and you will have to refresh the PowerApps page after the
    installation is complete. You should be able to see **Run** option now.

6.  Click on Run and wait for the run to complete.

7.  Click on the More **Commands** of the **Permit Management** solution.

8.  Click Solution Checker and select View Results.

9.  You will see several issues reported.

10. To resolve the issues, follow these steps:

11. Select **Apps**

12. Click … next to **Inspector** app and select **Edit**

13. Click **App checked** icon on the toolbar

14. Select **Recheck All**

15. Expand **Missing accessible label** node

16. Select an issue. This will open the screen with the control and prompt to
    enter **AccessibleLabel** property.

17. Enter text value as appropriate

18. Repeat the process for all controls with missing accessible labels

19. Expand **Missing tab stop** node

20. Select control, enter a value for the **TabIndex**, e.g. 0

21. **Tips** node may contain the following message:
    “Use another method instead of HTML, or remove the HTML from this element.”

22. This message is related to Map component we imported as part of the
    component bundle. This component can be safely deleted as it’s not used by
    the app.

23. Fix other app issues as appropriate

24. Click **File** and then click **Save**.

25. Click **Publish**.

26. Switch to <https://make.powerapps.com/>

27. Select **Solutions** then select **Permit Management** solution

28. Click **Solution checker** then select **Run** and wait for the run to
    complete.

29. There should be zero issues.

30. Select **Solutions** and click to open the **Permit Management** solution.

31. Click **Export**.

32. Click **Publish** and wait for the publishing to complete.

33. Click **Next**.

34. Select **Managed** and click **Export**.

35. Click **Save** and select **Save as**.

36. Save the solution on your machine.

37. Click **Export** again.

38. Click **Next**.

39. Edit the version number to match the Managed solution you just exported,
    select **Unmanaged** and click **Export**.

40. Save the unmanaged solution on your machine.

Task \#2: Import solution.
--------------------------

1.  Sign in to <https://make.powerapps.com>

2.  Make sure you have your **Prod** environment selected.

3.  Select **Solutions** and click **Import**.

4.  Click **Browse**.

5.  Select the **Managed** solution you exported and click **Open**.

6.  Click **Next**.

7.  Click **Import** and this will open a new window to track the import status.

8.  Wait for import to complete and click **Close**.

9.  Navigate to both the model driven and canvas apps you’ve created and add a
    few records, test the apps.