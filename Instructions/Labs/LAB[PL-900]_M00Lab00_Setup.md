---
lab:
    title: 'Lab: Validate lab environment'
    module: 'Module 0: Course introduction'
---

Module 0: Course introduction
=================================

Scenario
--------

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus.

In this Module 0 lab, you will acquire a Power Platform trial tenant and access the Power Platform admin center. In the admin center, you will then create your **Practice** environment that you will do the majority of your lab work in.

## Exercise 1 – Setup

### Task 1 - Acquire your Microsoft Power Platform trial tenant

1. Copy your **Microsoft 365 credentials** from the Authorized Lab Hoster.

2. Navigate to <https://powerapps.microsoft.com> and click **Start free.**

3. Under **Get started**, enter the email address from your Microsoft 365 credentials in the text box that says **Enter your work email address.**

4. You see a prompt that you have an existing account with Microsoft. Select **Sign in.**

5. Enter the password provided by the Authorized Lab Hoster. 

6. Select **Yes** to stay signed in.

7. Complete your account info and select **Get started** to sign up for your Microsoft Power Platform trial.  

### Task \#2 – Create environment

1. Access <https://admin.powerplatform.microsoft.com> and log in with your Microsoft 365 credentials if prompted again.

2. Select **Environments** and click **+New.**

    - For **Name**, enter **[My Initials] Practice.** (Example: AJ Practice.)
    
    - For **Type**, select **Trial** (do not select the Trial (subscription-based) option).
    
    - Change the toggle on **Create a database for this environment?** to **Yes.**
    
    - Leave all other selections as default and click **Next.**
    
    - On the next tab, leave all selections to default and click **Save.**

3. Your **Practice** environment should now show in the list of Environments. 

    > Your environment may take a few minutes to provision. Refresh the page if needed.

# Exercise \#2: Provision a Power Apps portal

**Objective:** Provisioning a Power Apps portal can take some time. In this exercise, you will create your Power Apps portal in your environment so that the provisioning process can be initiated. You will use this portal in a later lab.

## Task \#1: Create Power Apps portal

1.  Sign in to <https://make.powerapps.com>

2.  If the **Environment** displayed in the top right is not your Practice environment, click to select your Environment.

3.  On the Home page, click on the **Portal from blank** panel under **Make your own app**

    > If you do not see this option, try zooming out.

4.  Provide new portal details

    -   Enter **```Bellows College Visitors```** as the portal **Name**

    -   Provide a unique URL; **something**.powerappsportals.com (if the name has been taken, choose a different one)

    -   Select a base portal **Language**

    -   Click **Create**

    > The Portal provisioning process will run anywhere from 30 to 45 minutes. You do not have to wait, as this will continue while moving on to the next module.
