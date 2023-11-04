---
lab:
    title: 'Lab 0: Validate lab environment'
    module: 'Module 0: Course introduction'
---

# Lab 0: Validate lab environment

**WWL Tenants - Terms of Use**
If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training. 
Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and are not eligible for extension. 
Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time. 

## Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts. 

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus.

In this Module 0 lab, you will acquire a Power Platform trial and access the Power Platform admin center. In the admin center, you will then create a **Practice** environment that you will perform the majority of your lab work in.


## Exercise 1 – Setup

Task #1 - Acquire your Microsoft Power Platform trial tenant

1.  Copy your **Microsoft 365 credentials** from the Authorized Lab Hoster. 

1.  Navigate to <https://powerapps.microsoft.com> and select **Start free**.

1.  Under **Let's get started**, enter the email address provided by the Authorized Lab Hoster and select **Start your free trial**. 

1.  If an extra page appears with **Start building apps** and **Start using apps** buttons, then click **Start using apps** - not Start building apps.

1.  If you see a prompt that you have an existing account with Microsoft. Select **Sign in**. 

1.  Enter the password provided by the Authorized Lab Hoster and select **Sign in**. 

1.  Select **Yes** to stay signed in. 


Task #2 – Create environment

1.  Navigate to <https://admin.powerplatform.microsoft.com> and log in with your Microsoft 365 credentials, if prompted. 

1.  If you see a Welcome pop-up, select **Get Started**. 

1.  Select **Environments** and select **+ New**.

    1. For **Name**, enter **[My Initials] Practice** (Example: AJ Practice).

    1. For **Type**, choose **Trial** (Do not select the *Trial (subscription-based)* option).

    1. Change the toggle for **Add a Dataverse data store?** to **Yes**. 

    1. Leave all other selections as default and select **Next**. 

    1. Under the the **Security group** heading, use the **+ Select** button.

    1. Select the checkbox for the **None** item, under the **Open access** heading and then select **Done**.

    1. Leave the remaining options at their defaults and select **Save**. 

1.  Your **Practice** environment should now appear in the list of Environments. 

    > Your environment may take a few minutes to provision. Refresh the page if needed.

