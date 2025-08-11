---
lab:
    title: 'Lab 4: Create a canvas app'
    learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
    module: 'Module 2: Build a canvas app'
---
## Learning Objective

In this exercise, you will use Copilot to create a canvas application that employees can use for requesting and managing time off and equipment checkout requests. Once the app is created, you will use Copilot and Power Apps designer to amend the app.

Upon successful completion of this lab, you will:

- Use Copilot to aid you in creating a data model to support your app.
- Modify a canvas application.

### Scenario

Contoso Consulting is a professional services organization specializing in IT and AI consulting services. They are looking to create a time off application that employees can use to request time off.

### Lab Details

Before beginning this exercise, required that you have completed the following lab:

- **Lab 2 – Create a data model**

> **Important**
This lab uses AI to build out the components. Since AI results can vary, it’s important to note that your results may be different (but similar) to what is defined in the lab. The basic concepts outlined in the lab will be the same no matter what was created or what it was named. If the tables and columns do not match exactly, you may need to adjust to what was created for you.

The estimated time to complete this exercise is **60 to 75** minutes.

## Task 1: Sign in to Power Apps and explore the interface

1.  Open a web browser and navigate to the [Power Apps](https://make.powerapps.com/) maker portal.
1.  Using the navigation on the left, select **Create**.
1.  Under **Create your apps**, choose **Start with Copilot**.
1.  In the **Describe the tables you want copilot to build** screen, type: *` I want to store time off requests sent by employees. The table should identify the start and end times of the request.`*
1.  Select the **Table options** button. From the menu that appears, select **One Table**.

    ![Screenshot of getting started with Copilot screen](media/60a2ec72988f48c91df7c370532cb331.png)

1.  Select the **Generate** button.

    Copilot should have created a **Time Off Request** table. Next, we will add more columns to the table.

    **Note**: If necessary, please add  Table name to prompt.

1.  In the **Copilot** pane, enter: *`Add a choice column called Time Off Reason.`*
1.  In the **Copilot** pane, individually add the following prompts.
    - *`Add a choice column named Time off Type.`*
    - *`Add a Date column called Submission Date.`*
    - *`Add a choice column to the Time Off request table called Approval Status.`*
    - *`Add a multi-line text column called Request Details.`*

    Your time off table should resemble the image:

    ![Screenshot of completed Time Off Request table ](media/2ac256daafe1853e5367852467690c76.png)

    Next, we are going to add the user table to the data model so we can associate time off requests with specific users.

1.  On the **Command bar**, select **+ Existing table**.
1.  Switch from **Recommeded** to **All tables**.
1.  In the **Search** field, enter **User**.
1.  Select the **User** table and click the **Add Selected** button.
1.  On the **Command bar**, select **Create relationships**.
1.  Configure the relationship as follows:

    -   **One:** User
    -   **Many:** Time Off Request
    -   **Display name:** `Requesting Employee`
  
1.  Select **Done**.

    Your completed data model should resemble the image:

    ![Screenshot of completed data model ](media/daa74d51e2ceada8e1e8b004cae9942a.png)

1.  Select the **Save and open app** button.

> [!NOTE]
> It can take several minutes for your new app to be created.

## Task 2: Personalize your new app

Now that your new app has been created we are going to make some modifications to it to best fit our needs. We are going to start by making some modifications to the Welcome screen.

1.  With your new app open, Select the **Image** placeholder above the **Time Off Requests** text.
1.  From the menu that appears, select **Edit** \> **Upload**.
1.  Choose the **Time off** image in the class files folder, and then select **Open**.
1.  Next, select the **Image** placeholder above **Users**.
1.  From the menu that appears, select **Edit** \> **Upload**.
1.  Choose the **Employee** image in the class files folder, and then select **Open**.

    Next, we are going to adjust the size of the images to make them easier for users to read. Additionally, we are going to adjust the text that is displayed for each item.

1.  On the **Command bar**, select the **Properties** button. (*Located just to the right of the Editing button.*)
1.  Select the **Time off** image you add earlier.
1.  In the **Properties** panel, configure the image as follows:
    
    -   **Image Position:** Fill
    -   **Width:** 300
    -   **Height:** 300
      
1.  Repeat the earlier step to set the **Height** and **Width** of the **Employee** image to **300** x **300**.
1.  Select the text below **Time Off Requests**.
1.  In the **Properties** panel, select the **Text** field, and change the text to: *`Create, View, and Manage you time off requests.`*
1.  Select the **Welcome Screen** text in the **Header**.
1.  In the **Properties** pane on the right, select the **Logo** field.
1.  From the menu that appears, select **Upload**.
1. Select the **Contoso Logo** from your class files and select **Open**.
1. In the **Properties** panel under the **Style** and theme group, select the **Fill** color icon.
1. Select the **Custom** tab
1. Change the **Hex** color to: `101E2B`
1. Make sure that you still have the **Header** selected, and change the **Title** to `Contoso Employee Hub`.
1. On the **Command** bar, select the **Save** button to save the app.
1. In the **Save** screen, set the **Name** to `Contoso Employee Hub`, and select **Save.**

    Your app will resemble the image.

    ![Screenshot of Canvas app welcome screen.](media/533c80cc861941b6a353b56bfc0dbc0f.png)

## Task 3: Add a new screen to you app.

As you are building the app, one of your managers reaches you to you and is wondering if employees could also use this app for checking out equipment. Contoso is already storing equipment checkout information in Dataverse, so it is just a matter of making the information available in the app.

1.  With your app still open, expand the **Copilot** pane (if necessary). In Copilot, enter the following: *`Add a new screen called Equipment Checkout.`*
1.  Select **Send**.
1.  Select the **Keep it** button to accept the screen.
1.  A new screen called **Equipment Checkout** is added to your app.
1.  While on the **Equipment Checkout** screen, click **With layout**, and choose the **Sidebar** layout.
1.  Expand the different containers until **SideBarContainer** is visible.

    ![Screenshot of tree view ](media/cde6257402b7a8786e679ab64ee0f882.png)

1.  Right-click **SidebarContainer** and rename to **EquipContainer1**.
1.  With the **EquipContainer1** container selected, click the **Open insert menu** button.
1.  In the **Search** window, enter **Gallery**, and select **Vertical gallery**.
1.  When you are asked troi supply a data source in the **Search** field that appears, enter **Equipments**, and select the **Equipments** table.
1. In **Tree View** on the left side of the screen, select the **Gallery1** control you just added.
1. Right-click the Gallery name, choose **Rename**, and rename to `Equipment List`.
1. Hover over the **Equipment List** gallery, on the toolbar that appears above the gallery, select **Layout**.
1. Select the **Title and subtitle layout** option.
1. With the **Equipment List** gallery selected, in the **Properties** pane, configure as follows:

    -   **Width:** `360`
    -   **Flexible height:** On
    -   **Minimum height:** `287`

    Next, we are going to add an additional container to the **EquipmentContiner1** container to store a search control that we will use to filter the contents of the **Equipment List** gallery.

1.  In **Tree** view, select **EquipContainer1**.
1.  Hover over the container and select the **Copilot** icon.
1.  Enter the following text: *`Insert a Horizontal container.`*

    ![Screenshot of inserting a gallery into a container.](media/b9b784ea5625469c8785650b977f32d1.png)

1.  Select the **Keep it** button.
1.  A new container will be added to the bottom of the **EquipContainer1** container.
1.  In the **Tree View**, click, hold, and drag the new container, and place it above the **Equipment List** gallery.
1.  Rename the container to `EquipSearchContainer`.
1.  With the **EquipSearchContainer** selected, in the **Properties** pane, configure as follows:
    
    -   **Minimum width:** `0`
    -   **Flexible height:** Off
    -   **Height:** `44`
    
1.  With **EquipSearchContainer** selected, select the **Open insert menu** button.
1. In the **Search** field, enter **Text**, and select **Text input**.
1. Rename the **Text Input** field, to `EquipSearchInput`.
1. With **EquipSearchInput** selected, in the **Properties** pane, configure as follows:

    -   **Default:** Blank (nothing)
    -   **Hint text:** Search
    -   **Font:** Open Sans
    -   **Font size:** 14
    -   **Padding** (The values below may already be there.)
        -   **Top:** 5
        -   **Bottom:**5
        -   **Left:** 12
        -   **Right:** 5
    -   **Height:** 44
    -   **Flexible width:** On
    -   **Minimum width:** 0

        ![Screenshot of Search Input properties.](media/b0e092b4795edf58dad1153209639051.png)

1. In **Tree View**, select the **EquipSearchContainer.**
1. Hover over the container, select the **Copilot** icon, and enter *`Add a Search Icon.`*
1. Select **Keep it**.

    > **Note:**
If Copilot happends to add the wrong icon, remove it and insert the magnifying glass manually.

1. With the **Search** icon selected, in the **Properties** pane, configure the control as follows:

    -   **Padding**
        -   **Top:** 10
        -   **Botton:** 10
        -   **Left:** 10
        -   **Right:** 10
    -   **Height:** 44
    -   **Width:** 44

    ![Screenshot of Search Icon properties](media/cb3305731a09bca0bbf166d55d9822a4.png)

1. Using the **Tree view** on the left, select the **EquipSearchContainer.**

    Finally, we are going to configure the **Equipment List** gallery to populate its data based on the text entered in the search control field.

1.  Select the **Equipment List** gallery we created earlier.
1.  In the **Items** property, enter the following formula: `Search([@'Equipments'], EquipSearchInput.Text, 'Equipment Name',Category)`

    ![Screenshot of Items PowerFx Formula.](media/powerfx-formula.png)

1. On the **Command** bar, select the **Save** button to save your app.

> **Important:**
If you copied and pasted the formula into the formula bar, it is possible that the '' are incorrect for Equipment and Equipment Name. If you are getting a formula error, try removing and retyping them.

## Task 4: Build a container to display record operations.

When a user selects a record in the Equipment list, we want to open the record in another container to allow them to edit the selected record.

1.  Select the **MainContainer** and rename it to `DetailsContainer`.
1.  On the **DetailsContainer**, select the **Insert** button.
1.  In the **Search** filed, enter **Container**, and choose **Vertical Container**.
1.  Right-click and **Rename** the container to `RecordDetails`.
1.  On the **RecordDetails** container, select the **Insert** button.
1.  On the **Insert** menu, select **Edit form**.
1.  In the select data source screen, select **Equipments**. *(It can take up to 30 seconds for the data to populate.)*
1.  Right-click the form you just added and **Rename** it to `EquipmentForm`.
1.  In the **Properties** pane, select the **Advanced** tab and set the **Item** property to: `'Equipment List'.Selected` *(This will populate the form with the currently selected record.)*
1. Select the **Display** tab, and configure the form as follows:

    -   **Columns:** 2
    -   **Default Mode:** Edit

    Now we are going to add another container that will be used to control the operations on the form.

1.  Make sure that you have the **DetailsContainer** selected.
1.  Select the **Copilot** icon that appears. Enter the following: *`Insert a horizontal container.`*
1.  Select **Keep it**.
1.  Right-click the container, and **Rename** it to `SelectedRecord1`
1.  Using **Tree** view, move the **SelectedRecord1** container above the **RecordDetails** container.
1.  Configure the **SelectedRecord1** container as follows:
    
    -   **Minimum width:** 250
    -   **Flexible height:** Off
    -   **Height:** 50
    
1.  With the **SelectedRecord1**container selected, select the **Insert** button.
1.  Select **Text Label.**
1.  Rename the label to `SelectedRecordTitle`.
1. Configure the **SelectedRecordTitle** as follows:

    1.  **Padding**
        1.  **Top:** 5
        2.  **Bottom:** 5
        3.  **Left:** 30
        4.  **Right:** 5
    2.  **Flexible width:** On
    3.  **Minimum width:** 150
    4.  **Height:** 40
       
1. Select the **SecondRecord1** container, Select the **Insert** button.
1. In the **Search** field, enter **Save**, and select the **Save** icon.
1. Configure the **Save** button as follows:

    -   **Height:** 40
    -   **Width:** 40
      
1. Select the **OnSelect** property and enter the following formula: `SubmitForm(EquipmentForm)`.

    ![Screenshot of OnSelect PowerFx formula.](media/e5b22c91a437e6918269d65e2616afc8.png)

## Task 5: Modify the Header on the Page

The last step in creating this screen is to populate the reader container with data.

1.  Select the **HeaderContainer** at the top of the app.
1.  Select the **Insert** button.
1.  Select **Text label**.
1.  Configure the **Text label** control as follows:
   
    -   **Text:** `Equipment Checkout`
    -   **Font:** Open Sans
    -   **Font Size:** 16
    -   **Font weight:** Semibold
    -  **Padding**
        -   **Top:** 16
        -   **Bottom:** 16
        -   **Left:** 16
        -   **Right:** 16
    -   **Height:** 40
    -   **Flexible width:** On

        ![Screenshot of text label properties.](media/088cafeec651b099fa49ac1f151cd228.png)

1.  Select the **HeaderContainer**, choose **Insert**, and select the **Home Icon**.
1.  Set the **OnSelect** property of the home button to: `Back()`

    ![Screenshot of the Back navigation command.](media/38d0e5367ee41da58ac9902f8056b1af.png)

## Task 6: Finish configuring the Welcome screen

Upon review, we have decided that we do not need to have the ability to create users in this app, so we are going to change the Welcome Screen to allow you to access equipment checkout.

1.  Using **Tree view**, select the **Welcome Screen**.
1.  Select the **Image** above **Users**.
1.  From the menu that appears, select **Edit**, and choose **Upload**.
1.  Locate the **Equipment** image in your student folder and choose **Open**.
1.  Set the **OnSelect** property of the image to: `Navigate('Equipment Checkout')`
1.  Select the **Users** text and set the **Text** property to `Equipment`.
1.  Select the **Text** below **Equipment** and change the **Text** property to: `Check out equipment and edit reservations`.

    ![A screenshot of a computer AI-generated content may be incorrect.](media/561d1e8cd023541761b6523138c2fde8.png)

1. Select the **Save** button to save your app.

## Task 7: Test your application

1.  On the **Command bar**, select the **Play** button.
1.  Select the **Equipment** image.
1.  In the **Search** field, enter **Electronics**. (*Notice how the list filters*)
1.  Select the **Laptop** record.
1.  Change the **Category** to **Furniture**.
1.  Select the **Save** button.
1.  Notice how the category of the **Laptop** changes to **Furniture**.
1.  Select the **Home** button.
1.  Select the **Purple X** to leave **Preview** mode.

## Task 8: Save and publish the app

**Goal:** Save and publish the app to make it accessible across web browsers, mobile devices, or embedded platforms like SharePoint or Teams.

1.  In Power Apps Studio, select the **Save** button.
1.  Select the **Publish** button.
1.  Choose **Publish this version.**


