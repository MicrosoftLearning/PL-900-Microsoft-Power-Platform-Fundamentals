---
lab:
    title: 'Lab 7: Create a Power Pages site'
    learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Pages'
    module: 'Module 2: Create a Microsoft Power Pages site'
---
## Learning Objective

In this exercise, learners will be using Copilot to build a Power Pages site. Once the site is created, you will be using Power Pages Design Studio to perform tasks such as adding and modifying content, as well as changing themes.

### Scenario

Throughout the year, Contoso Consulting hosts many different types of events. They range from in person events, to webinars, Instructor led trainings and more. They are looking to use Microsoft Power Platform to manage the different events that they put on. They want to use Power Pages to create an event management site that will display the different events that they host.

Upon successful completion of this exercise, you will:

-   Use Copilot to build an Event Management website.
-   Add new content to your site.
-   Preview your new Power Pages site of different types of devices.

**Lab Details:**

Before beginning this exercise, required that you have completed the following lab:

- **Lab 3 – Create a data model**

> [!IMPORTANT]
> This lab uses AI to build out the components. Since AI results can vary, it’s important to note that your results may be different (but similar) to what is defined in the lab. The basic concepts outlined in the lab will be the same no matter what was created or what it was named. If the tables and columns do not match exactly, you may need to adjust to what was created for you.

The estimated time to complete this exercise is **30 to 45** minutes.

## Task 1: Use Copilot to create a new Power pages site.

1.  If necessary, navigate to <https://make.powerpages.microsoft.com>
2.  On the **Power Pages design studio** home page, enter the following text: “*Build a site to manage events our organization hosts.”*
3.  Select the **Send** button.
4.  In the **Check the basic site details** screen, configure as follows:
    - **Give your site a name:** Contoso Event Management
    - **Create a web address:** Accept the default address provided
    - **Site Language:** English

![Screenshot showing basic site details](media/9a5bc928349720c1da2f112bf1baf562.png)

5.  Select the **Next** button.
6.  In the **Choose a layout** screen, review the suggested layout provided. If you would like additional layout suggestions, select **Try again** to have **Copilot** suggest another layout.
7.  Once you have identified the template you want to use, select **Next.**
8.  In the **Add common pages** section, select the following pages:
    - About Us
    - Contact Us
    - FAQ
    - Select any additional pages, as desired.
9.  Once you have selected your pages, select **Done**.

Your new site will be created in the background, which can take several minutes.

10.  After your site is created, open the it (If not already taken there.)

> [!NOTE:]
> Sometimes when your site loads for the first time, you might see a Liquid object not found message. If this happens, Refresh (F5) the browser window to reload the site. The site should appear.

## Task 2: Modify the contents of your site

Now that you initial site is created, you can use the design studio to modify you site by adding pages, text, images, forms, and more.

1.  **Main navigation**, select **Home** to open the **Home** page.
2.  Hover over the **Contoso Event management Site** text in the site header and select **Edit site header**.
3.  Change the **Site title** to **Contoso Consulting**.
4.  Select the **Upload image** button.
5.  On the **Add an image** screen, select **Upload** image, choose the **Contoso Logo** from you class files, and choose **Open**.
6.  With the **Contoso Logo** image selected, select **OK**.
7.  After you are finished with you changes, select the **X** to leave the **Edit site header** screen.
8.  To change the site background image, click anywhere in the background image.
9.  From the menu that appears, choose **Edit background**.
10. Select the **Change Image** button.
11. Select **Media library** and choose **Upload Image**.
12. Select the **Site_Background** image from your class files and choose **Open**.
13. With the Site_Background selected, choose **OK**.
14. Select the text **Welcome to Contoso Events** and change the text to **Contoso Consulting**.
15. On the toolbar that appears, select the **Design** *(Paint brush)* button.
16. Select the arrow next to the **Text Shadow** property and set the **H-Offset** to **2**.
17. Select the **X** to close the **Text Design** window.
18. Select the text below Contoso Consulting, *(Might say something similar to Your Partner in Event Management)* and change it to **Your partner for today and tomorrow.**

Now that we have made some basic changes to the home page, we are going to update the theme of the site to better match Contoso’s branding.

19.  Using the navigation on the left, select the **Styling** button.
20.  Select the **Bright Blue** theme.
21.  Under **brand colors**, select the **Gray** color circle.
22.  Change the **Hex** color**: 101E2B**
23.  Select **OK**.
24.  Select the **White** circle, and change the color to **Hex** code **e8e8e8**
25.  Select **OK**
26.  Select the **Black** circle and change the color to **White**. (ffffff)
27.  Select **OK**.
28. Make any additional theming changes that you want. Once you are finished with your theming change, select the **Save** button.

## Task 3: Connect your site to your business data

One of the primary advantages of Power Pages is the ability to connect a Power Pages to your business data that is in Dataverse. Before we can bring the data in, we need to build out some elements that will be used.

1.  Using the navigation on the left, select the **Data** icon.
2.  In the **Search** field, enter **Event**.
3.  Select the **Event** table.

First, we are going to create a form that will be used when we want to add a new event.

4.  Select the **Forms** tab, then choose **New Form**.
5.  Set the **Form name** to **Create Event**, then select the **Create** button.
6.  We are not going to make any modifications to the layout. Select the **Save and Publish** button.
7.  Press the **Back arrow** to return to the designer.

Next, we are going to create a form that will be used for viewing and editing existing events

8.  Select the **New Form** button.
9.  Name the form **View Event** and select the **Create** button.
10.  On the **Command bar**, select **Add Component**, and select **Subgrid**.
11.  Configure the Subgrid as follows:
    -   **Show Related Records:** Yes
    -   **Table:** Event Sessions
    -   **Default:** Active Sessions
12.  Select **Done**.
13.  Select the **Save and Publish** button.
14.  Select the **Back** button to return to the **Design Studio**.

## Task 4: Create necessary web page forms

Now that we have defined forms for the Event table, we are going to create pages that include those forms so site users will be able to work with Event records. We are going to create pages for viewing, creating, and editing events.

1.  Using the navigation on the left, select the **Pages** icon.
2.  Select the **+ Page** button.
3.  In **Copilot**, enter the following text: *“Add a new blank page.”* Select the **Send** button.
4.  Select the **Keep it** button.
5.  At the top of the new page, select the **Add a Section** button.
6.  Select **1 Column**.
7.  In **Choose a component to add to this section**, select **Form**.
8.  Select **+ New form**.
9.  On the **Add a form** screen, configure as follows:
    - **Choose a table:** Event
    - **Select a form:** Create Event
    - **Name your copy of selected form:** Create Event
10. Select the **Data** tab and verify that the **Data for this form** is set to **Create a new record**.
11. Select the **On submit** tab. In the **Display this message** field, enter *“Your event has been successfully submitted.”*
12. Select the **OK** button.

Let’s remove any additional sections on the page as we do not need them.

13. Select the **Section** below the **Form** you just added. On the toolbar that appears, select More **(…)** and choose **Delete**.
14. Repeat the previous step to remove the remaining two sections from the page.

Once completed, the only items that should remain are the form you created and the footer at the bottom of the page.

15. Under **Main navigation** on the left, select the Ellipsis next to the **New Page** you created.
16. From the menu that appears, select **Page Settings**.
17. Configure the page settings as follows:
    - **Name:** New Event
    - **Partial URL:** New-Events
18. Select the **OK** button.

Next, we will add an additional page that can be used for viewing an individual event.

19.  Make sure you still have **Pages** selected and click the **+ Page** button.
20.  In the **Describe a page to create it** screen, enter: “*Add a Blank Page named View Event.*” Select the **Send** button.
21.  Select the **Keep it** button to accept the new page.
22.  At the top of the new page, select the **Add a Section** button.
23.  Select **1 Column**.
24.  In **Choose a component to add to this section**, select **Form**.
25.  Select **+ New form**.
26.  On the **Add a form** screen, configure as follows:
    - **Choose a table:** Event
    - **Select a form:** View Event
    - **Name your copy of selected form:** View Event
27.  Select the **Data** tab and set the **Data for this form** field to **Is read-only**.
28. Select the **OK** button.

Let’s remove any additional sections on the page as we do not need them.

29. Select the **Section** below the **Form** you just added. On the toolbar that appears, select More **(…)** and choose **Delete**.
30. Repeat the previous step to remove the remaining section from the page.
31. Under **Main navigation** on the left, select the **Ellipsis** next to the new page you created.
32. From the menu that appears, select **Page Settings**.
33. Configure the page settings as follows:
    - **Name:** View Event
    - **Partial URL:** View-Events
34. Select the **OK** button.

Finally, let’s create one more webpage form that we can use to edit an event.

35.  Make sure you still have **Pages** selected and click the **+ Page** button.
36.  In the **Describe a page to create it** screen, enter: “*Add a Blank Page named Edit Event.*” Select the **Send** button.
37.  Select the **Keep it** button to accept the new page.
38.  At the top of the new page, select the **Add a Section** button.
39.  Select **1 Column**.
40.  In **Choose a component to add to this section**, select **Form**.
41.  Select **+ New form**.
42.  On the **Add a form** screen, configure as follows:
    - **Choose a table:** Event
    - **Select a form:** Create Event
    - **Name your copy of selected form:** Edit Event
43.  Select the **Data** tab and set the **Data for this form** to **Updates an existing record**.
44. Select the **OK** button.

Let’s remove any additional sections on the page as we do not need them.

45. Select the **Section** below the **Form** you just added. On the toolbar that appears, select More **(…)** and choose **Delete**.
46. Repeat the previous step to remove the remaining section(s) from the page.
47. Select the **OK** button.

## Task 5: Create a page that displays a list of events

Now that we have defined the necessary forms we are going to use for managing records, we are going to create a page view to display those records.

1.  Select the **+ New Page** button.
2.  In the **Describe a page to create it** screen, enter: *“Add a blank page called events.”* Select the **Send** button.
3.  Select **Keep it** to accept the new page.
4.  At the top of the new page, select the **Add a Section** button.
5.  Select **1 Column**.
6.  In **Choose a component to add to this section**, select **Form**.
7.  Select the **More** button *(…)*. Under the **Connected data** group, select **List**.
8.  In the **Add a list** screen, select the **Setup** tab, and configure as follows:
    - **Choose a Table:** Event
    - **Select the data views:** Active Events, Inactive Events
    - **Name you list:** Events
9.  Select the **Actions** tab and configure as follows:
    1.  **Create a new record:** On
        1. **Target Type:** Form
        2. **Form:** Create Event
        3. **Display label:** Create New Event
    2.  **View details:** On
        1.  **Target Type:** Form
        2.  **Form:** View Event
        3.  **Display label:** See Event Details
    3.  **Edit record:** On
        1.  **Target Type:** Form
        2.  **Form:** Edit Event
        3.  **Display label:** Edit Event
    4.  Select **Done**.

## Task 6: Update Permissions

To ensure that users are only seeing data relevant to them organizations can specify table permissions. In this task we are going to create very basic permissions that provide access to anyone.

1.  Under **Main Navigation**, select the **Events** page.
2.  Select the **Events** list and click the **+ New permission** button.
3.  Configure the permission as follows:
    -   **Name:** Events
    -   **Table:** Event
    -   **Access Type:** Global access
4.  Set the **Permission** to **Read**.
5.  Select **Add roles**, and choose the **Administrators**, **Anonymous Users**, and **Authenticated Users** roles.
6.  Select the **Save** button.
7.  A screen that says **The data can be seen by anyone** appears, select **Save**.

Let’s repeat that process for the event form pages. We’ll start with the **New Event** page

8.  Under **Main Navigation**, select the **New Event** page.
9.  Select the **Update permission** button.
10.  Configure the permission as follows:
    -   **Name:** Create Events
    -   **Table:** Event
    -   **Access Type:** Global access
11.  Set the **Permission** to **Read** and **Create**.
12.  Select **Add roles**, and choose the **Administrators**, **Anonymous Users**, and **Authenticated Users** roles.
13.  Select the **Save** button and select **Save** again on the popup screen.

Next, we will set for the **Edit Event** screen.

14.  Under **Main Navigation**, select the **Edit Event** page.
15.  Select the **Update permission** button.
16.  Configure the permission as follows:
    -   **Name:** Create Events
    -   **Table:** Event
    -   **Access Type:** Global access
17.  Set the **Permission** to **Read** and **Update**.
18.  Select **Add roles**, and choose the **Administrators**, **Anonymous Users**, and **Authenticated Users** roles.
19.  Select the **Save** button and select **Save** again on the popup screen.

## Task 7: Update site navigation

Now that we have our pages and Items formatted the way we want, we are going to adjust the site navigation accordingly.

1.  Under **Main Navigation**, select the **Ellipsis** next to the **Event** page.
2.  From the menu that appears, select **Move up**.
3.  Repeat step until the **Event** page located below the **Contact Us** page.
4.  Make sure the **New Event** page is located directly under the **Events** page. *(If not, move the New Event page until it is.)*
5.  On the **New Event** page, select the **Ellipsis** button.
6.  From the menu that appears, select **Make this a sub-page**.
7.  Select the Ellipsis next to **View Event** and select **Move to Other Pages**.
8.  Select the Ellipsis next to **Edit Event** and select **Move to Other Pages**.
9.  On the **Command bar**, select the **Sync** button.

## Task 8: Preview and refine your site

Once your site is created, you will want to review it to ensure it meets your business needs and requirements so you can determine any refinements that are necessary. Sites can be previewed in Desktop and Mobile mode

1.  In the design studio, select the **Home** page button.
2.  Slick **Preview** from the command bar.
3.  Select **Desktop** to preview your site in a browser.
4.  While viewing in **Desktop** mode, review the following aspects of your site such as:
    -   Layout and navigation.
    -   Branding elements such as colors, fonts, and logos.
5.  Once you have finished testing the site, close the **Browser tab** to return to the site editor.

Next, we will preview the site as it would appear on mobile devices.

6.  Select the **Preview** button again.
7.  Scan the **QR code** displayed with your mobile device.
8.  The site will open on your mobile device *(Note: you might be prompted to login, If so provide your login credentials.)*
9.  As you did while in Desktop mode, review the following aspects of your site such as:
    - Layout and navigation.
    - Branding elements such as colors, fonts, and logos.
10. Once you have finished testing, close the browser tab to return to the site.
