---
lab:
    title: 'Lab 5: How to build a simple dashboard'
    module: 'Module 5: Get Started with Power BI'
---

## Lab 5: How to build a simple dashboard

**WWL Tenants - Terms of Use**
If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training. 
Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and is not eligible for extension. 
Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time. 

## Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

In this lab, you will build a Power BI report and dashboard that visualizes data about campus visits.

**High-level lab steps**

We will follow the below steps to design and create a Power BI dashboard:

- Create a report with various visualizations of the campus visits information

- Utilize a user natural language query to build additional visualizations

### Prerequisites

- Completion of **Module 1 Lab 0 - Validate lab environment**

**Things to consider before you begin**

- Who is the target audience of the report?

- How will the audience consume the report? Typical device? Location?

- Do you have sufficient data to visualize?

- What are the possible characteristics you can use to analyze data about the visits?

## Exercise #1: Create Power BI Report

**Objective:** In this exercise, you will create a Power BI report based on data the Excel spreadsheet we leveraged in a previous exercise.

### Task #1: Prepare Power BI service

1. You should have a visits.pbix file stored on your virtual machine in the AllFiles folder on the Desktop. Download [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) and save to your computer, if it's not already there.

1. Open a new tab and navigate to https://app.powerbi.com and sign in, if needed.

1. Select **My workspace** from the left side navigation.

1. Select **Upload** then **Browse**.

1. Locate and select the **visits.pbix** file you have downloaded earlier.

1. Once the data load is complete, select the **visits** report.

    >**Note:** The Type is set to **Report**, do not select the Dataset.

1. Select **Edit**.

If the **Edit** menu item is not visible, select the ellipsis **...** and then select **Edit**.

You have now setup Power BI service to use for your labs.

### Task #2: Create Chart and Time Visualizations

1. Select the **Pie chart** icon in the **Visualizations** panel to insert a chart.

1. Expand **bc_Visit** in the **Fields** pane. Drag the **Building** field and drop it into the **Legend** box.

1. Drag the **Visit** field and drop it into the **Values** box.

1. Resize the pie chart using corner handles so that all chart components are visible.

1. Click on the report outside of the pie chart to deselect it and select the **Stacked column chart** icon in the **Visualizations** pane.

1. Expand **bc_Visit** in the **Fields** pane if it is not already expanded. Drag the **Visit** field and drop it into **Y-axis** box.

1. Drag **Start** field and drop it into **X-axis** box.

1. In the **Visualizations** pane, select the **x** next to **Year** and **Quarter** to leave only **Month** and **Day** totals for the X-axis.

1. Resize the chart as desired using the corner handles.

1. Test the report interactivity:

	- Select different building slices on the pie chart and observe changes on the Stacked column chart.

	- Select the Stacked column chart. Select the up arrow, to **Drill up**. Select the down arrow to turn on **Drill down** mode, then select a column to drill down to the next level (days).

	- Drill up and down and select various bars on the Stacked column chart to observe changes on the pie report.

1. Save work in progress by selecting **Save this report**.

## Exercise 2: Create Power BI Dashboard

### Task #1: Create Power BI Dashboard

1. You should have the report open from the previous task.

1. Select **Pin to a dashboard** on the menu. Depending on the layout you may need to select the ellipsis menu **...** to show more options.

1. Select **New dashboard** on **Pin to dashboard** prompt.

1. Enter Campus Management as **Dashboard name** and select **Pin live**.

1. A pop-up will prompt you that the dashboard has been created. Select **Go to dashboard**.

1. Test interactivity of the pie and bar charts displayed.

### Task #2: Add Visualizations Using Natural Language

1. Within your **Campus Management** dashboard, select **Ask a question about your data** bar at the top.

1. Enter buildings by number of visits in Q&A area. A bar chart will be displayed.

1. Select **Pin visual**.

1. Select **Existing dashboard**, select the **Campus Management** dashboard, select **Pin**.

1. Select **Exit Q&amp;A**.

Your **Campus Management** dashboard should be displayed with three visuals on it. You may have to scroll down to see the new Q&A visual.

Your dashboard should look similar to the following:

[![Screenshot of the dashboard just created](media/lab-5-power-bi-01.png)](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Instructions/Labs/media/5-powerbi-result.png)

 
