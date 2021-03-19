---
lab:
    title: 'Lab 8: How to build a basic chatbot'
    module: 'Module 6: Intro to Power Virtual Agents'
---

# Module 6: Intro to Power Virtual Agents
## Lab: How to build a basic chatbot

# Scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Like most organizations, Bellows College is quickly responding to concerns with misinformation about COVID-19, best practices, schedules, and so on. In this lab, you will build a Power Virtual Agent chatbot that will point to the Center for Disease Control page with questions and answers regarding the current status of the pandemic. The college will want this setup so that it can be embedded on their portal site, as well made available ad hoc as departments make their own planned reopening.

## High level steps

We will follow the below outline to build our Power Virtual Agent:

  - Sign up for a trial of Power Virtual Agent

  - Build a bot using FAQs

  - Test the bot

  - Change the default greeting

  - Publish the bot

  - **Bonus Challenge:** Embed bot in your portal

## Prerequisites

The following have been identified as requirements you must implement to complete the project:

  - Completion of **Module 0 Lab 0 - Validate lab environment**

  - Completion of **Module 2 Lab 1 - Introduction to Microsoft Dataverse**

  - Bonus exercise only: Completion of **Module 6 Lab 4 - Introduction to Power Apps portals** 

## Things to consider before you begin

Bots can be very useful in many different scenarios. Based on what you know so far about Bellows College, consider where else in the organization a bot might be of use.

# Exercise \#1: Sign up for PVA and Create a New Bot

In this exercise, you will sign up for Power Virtual Agents trial.

1.  Navigate to [Power Virtual Agents](https://powerva.microsoft.com/)

2.  Click **Start Free Trial**.

3.  Sign in, if required.

4. The **Create new bot** window should appear.

5. Enter **Crisis Bot** for **Name** and select a language.

6. Select your Practice environment to create the bot in and click **Create**. Wait for the bot to be created. Click **Explore bot** if prompted.

7. Test the bot. Type **Hello** in the message box and click **Send**. The bot should greet you and tell you what it can do.

8. Close the **Chat**.

9. Select **Topics**. The bot comes with some sample user topics and some system topics. The default greeting came from the system topics.

> In the next exercise, you will generate your own topics from the CDC FAQ site. Do not navigate away from this browser window.

# Exercise \#2: Create Topics

In this exercise, you will generate topics from the CDC FAQ site.

1.  In a new tab, navigate to the [CDC FAQ](https://www.cdc.gov/coronavirus/2019-ncov/faq.html) site and examine what is on the site. You will generate your topics from these FAQs.

2.  Copy the URL.

3.  Go back to Power Virtual Agents and make sure you still have **Topics** selected.

4.  Select the **Suggested** tab, below **Topics**.

5.  Click **Get started.**

6.  Paste the URL you copied in the **Link to online content** textbox and click **Add**.

7.  Click **Start** and wait. This can take a few minutes.

8.  You should get some suggested topics created for you. Click to open one of the suggested topics.

9. You should see the trigger phrase and what the bot reply will be. **Click Add to topics.**
    
10. The suggested topic should be added to your topics. Select all the suggested topics and click **Add to topics** 

    > You can select all topics by using the icon to the left of the Name column. If you receive an error message, please try again.

11. Once the Suggested topics have been added, select the **Existing** tab. You should see the new topics with their status set to Off.

12. Use the toggle button in the **Status** column to turn some of the topics to **On**. 

13. Write down the trigger phrase for one of the topics that you have turned on so that you can test with this later.

> Do not navigate away from this browser window.

# Exercise \#3: Test Topics

In this task, you will test the topics you added.

1.  Click **Test your bot** at the bottom left.

2.  Click **Reset**.

3.  Type the trigger phrase that you recorded from the previous task and click **Send**.

4.  The bot should give you the correct information and ask if it answered your question. Click **Yes**.

5.  The bot should ask you the rate how it did. Give it an excellent rating.

6.  The bot should ask if it can help you with anything else. Click **No, thanks**.

7.  The bot should conclude the chat session.

8.  Type **hello** and click **Send**.

9.  The bot should greet you and tell you what it can do. Your bot can now help users with COVID-19 FAQs, so you will need to change the greeting message in the next task. Do not navigate away from this browser window.

# Exercise \#4: Change the Greeting

In this task, you will change the greeting to COVID-19 specific.

1.  Make sure you have **Topics** selected and select the **Existing** tab.

2.  Collapse the **User Topics** section.

3.  Click to open the **Greeting** topic of the System Topics. You can also use the search box to **Search existing topics**.

4.  The greeting topic has 52 trigger phrases, click **Go to authoring canvas**.

5.  Go to the first message and replace it with `Hi, I’m a virtual agent. I can tell you about how COVID-19 spreads, how to protect yourself, preparing your home and family for COVID-19, symptoms, testing, and more.`

6.  Click **Save**.

7.  Click **Test Bot** if your bot is not still open. Click **Reset** to reset the chat.

8.  Type hello and click **Send**.

9.  The bot should now reply with the new greeting.

# Exercise \#5: Publish the Bot

In this exercise, you will publish the bot.

1.  Select **Publish** on the left navigation bar.

2.  Click **Publish**.

3.  Click **Publish** again and wait for the publishing to complete.

4.  Expand **Manage** on the left navigation bar and select **Channels**.

5.  You will get list of available channels you can publish your bot to. Select **Demo website**.

6.  Change the welcome message to `Try my COVID-19 FAQ bot.`

7.  Enter the following in **Conversation starters**:
    ```
     “Who is at higher risk for serious illness from COVID-19”
     “What does more severe illness mean”
     “What is the CDC doing about COVID-19”
    ```
    
8.  Click **Save**.

9.  Copy the **URL**.

> You can share the URL with your colleagues and get feedback from them. 

10.  Start a new browser window or tab and navigate to the URL you copied. The demo website should like the image below.

11. Go ahead and start chatting with the bot.  
    
When completed, your published bot should look similar to this:

![Bot demo website - screenshot](./media/8-image1.png)

# Challenges 
* Embed your chatbot on your Bellows College Visitors portal (more information on how to do this under **Add bot to Power Apps** [here](https://docs.microsoft.com/en-us/power-virtual-agents/publication-connect-bot-to-web-channels).)
