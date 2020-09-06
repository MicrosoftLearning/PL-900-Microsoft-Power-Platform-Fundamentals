---
lab:
    title: 'Trainer Guide'
    module: 'Module 1: Introduction to Power Platform'
---

# PL-900: Microsoft-Power-Platform-Fundamentals
## Trainer Guide

<!-- TODO -->

# TODO

* [x] Include delivery outline
* [ ] Align numbering and mentioning of modules and labs with the new module numbering 
* [ ] Explain why we're using custom Visits and not appointments (complexity of activity parties; not everything was working with activities and activity parties at the time of writing in canvas power apps and power automate; whatever else :D )
* [ ] Add discussions for power bi and pva


## Module outline

1. Intro to Power Platform 

2. Intro to Common Data Service 

   * Lab 1

3. Intro to Power Apps 

4. How to build a canvas app (formerly How to build an app solution)

   * Lab 2
   * Lab 3

5. How to build a model-driven app/Intro to model-driven apps

   * Lab 4

6. Intro to Power Apps portals 

   * Lab 5

7. Intro to Power Automate 

8. How to build an automated solution 

   * Lab 6

9. Intro to Power BI 

10. How to build a simple dashboard 

    * Lab 7

11. Intro to Power Virtual Agents 

12. How to build a basic chatbot

    * Lab 8

<!-- END OF TODO -->

# Environments

Students will need one Common Data Service (CDS) environment each to complete the course work. Environments can be provisioned by the students during class or they can be provisioned prior to the delivery with credentials handed over to the students prior to the first exercise.

The environments need no specific configuration considerations, a plain CDS *without any sample data* is all that is needed.

We recommend completing the labs as a student prior to the training delivery. 

* Familiarity with the exercises will make the delivery more efficient.
* Solution components built during this exercise can be used as needed for your demos. Demos are not required but some find them useful. Do a few on topics that you feel most comfortable with.

# Overview

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently and there are no means to collect and analyze data about the visits across the entire campus. 

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus. 

Some students may feel excessive to perform all customizations within the solution framework. However, it is vital to building good habits to bring along with them after the course.

> [!IMPORTANT]
> We are building components typical for Power Platform solutions. Dependencies are minimal but **Lab 1** is critical as the rest of the exercises use data model built during this lab. Sample data imported during the lab makes building and testing the apps easier, more realistic, and more relatable.

Apart from the common data model built in Lab 1, there are no dependencies between different labs. Trainers should clearly explain the objective of every lab and outline high-level solution components and techniques. Students then should be encouraged to design and build their own solutions without following step by step instructions for every exercise.

## Components

Completed components are available for *all* exercises. They include canvas apps, model-driven app, power automation flows, Power BI pbix file, sample data and data import map, and complete solution exported as both managed and unmanaged. Components shouldn't be used as a shortcut to exercise completion. Instead, they are useful as a demo tool and as a general point of reference.

Because all labs in the course depend on the data model, the model is available as a standalone solution [CampusDataModel_1_0_0_1.zip](../Allfiles/CampusDataModel_1_0_0_1.zip). It can be imported into a fresh environment followed by the Exercise #3 in Lab 1 (data import). That will create a starting point for the students who were unable to complete the lab. The prebuilt data model gives these students opportunity to catch up and proceed with the rest of the exercises. 

## Challenges

A number of challenges is provided at the end of every lab. The challenges typically include more realistic scenarios as the course exercises are simplified for the sake of time. Challenges also cover more advanced topics which some students may find helpful.

Use the challenges to initiate a discussion about real-world scenarios and how techniques learned during the exercises can be applied to solve the challenges.

Labs
======================

## Lab 01 Data Model

A solid data model is a foundation of the apps built on the platform. In this lab, we will set up an environment and create solutions to track changes. We will also create a data model to support the requirements and import sample data.

Topics to discuss:

* What tools would you use?
* How do you approach modeling?
* Where do you start?
* Relationships 
* Good practices around implementing data model in CDS
* Bringing Common Data Model entities (e.g. contacts) – what to include.
* Dev/test sample data sets – how much is enough. Good practices around building dev/test data sets.

### Challenges

* Would you consider using *appointment* activity as part of the solution? What would it change

  > Appointment or any other activity entity require more advanced understanding of concepts like activity parties, Regarding field, etc. Some of the maker tooling may not be capable of working with these yet and complex workarounds may be required.

* How to enforce the scheduled end to be after the scheduled start? 

  > A good topic to discuss business rules 

* Add support for multiple meetings during a single visit.

  > Many-to-many relationships and associated challenges

* Secure the building access not only for external contacts but for internal staff member as well.

  >  A good introduction to internal vs external data access, users vs contacts, authenticated vs anonymous. Potentially mention Power Apps Portals approach of treating users as contacts as well for the purpose

* Visits to certain buildings require management approval. What would the approval process change in the data model?

  > Discussion of business process flows and power automation approvals as techniques to introduce human factor into the processes

## Lab 02 Canvas app

This lab consists of two parts targeting different user personas.

In part 1 this lab, you will build a Power Apps canvas app that college staff can use to manage visits for their guests.

In part 2 of this lab, you will create build a Power Apps canvas app that the security personnel will use at the building entrances to quickly validate and register the visitors.

Topics to discuss

- Tablet vs phone form factor. Responsive layouts (available soon in canvas).
- How does the target audience impact the app design.
- How knowledge of Excel can benefit app makers (traditional procedural programming vs properties and expression syntax of Power Apps)

- Which connector to use. How CDS connector is now internal to canvas Power Apps.

- App checker – new metrics every day. Make sure to retest the app.

- Accessibility – what makes a good accessible app

### Challenges

**Part 1**

* Calendar view of all visits and filtering by date range

  > Components, third-party controls discussion, effective data filtering

* Ability to create and manage contacts as part of the app

  > Multiple screens, navigation between them

* How to display multiple meetings during a single visit

  > How to navigate relationships and properties

**Part 2**

* How to avoid manual entry of the visit code?

  > Use mobile device scanning capabilities if visitor can display a barcode with the code. Good discussion of how and when to generate barcodes for the visitors.

* Add building validation for the visit

  > Add building information to the barcode. Potentially use GPS capabilities. 

* Add validation of the visit actual time vs visit scheduled time (too early, too late, etc)

  > Manipulating date/time in formulas, more complex logic.

* Add detailed status of the visit, e.g. email display and validation for the visitor, reason for denying building access, etc

  > Access to the properties of related entities, building engaging UI

* How would you handle the requirement of multiple buildings/meetings/checkings during the single campus visit. For example, someone may visit campus for a day and during that day they will meet staff members in multiple buildings at different time of the day. What about single meeting with multiple external participants? Would you consider bringing *appointment* entity into the solution? 

  > This is a good but potentially complex and lengthy topic to discuss. Consider initiating a discussion and giving students some form of "home work". Discuss how Power Apps enable iterative approach to building apps, i.e. start simple and enhance as you go.

## Lab 03 Power Automate

In this lab, you will create Power Automate flows to automate various parts of the campus management. This lab requires, in addition to Lab 1, an app built in Part 1 of Lab 2. This is necessary so that the testing of automation can be performed (triggering processes by entering new data)

Topics to discuss

* Flows in solutions
* CDS connectors (standard vs current environment)
* Other automation means in Power Platform (real-time workflow, UI automation)
* Human interaction with flows - approval processes
* Testing the processes during the build
* Sharing the flows
* Monitoring running processes

### Challenges

* Add building information and map to the notification flow.

  > Potentially using images, maps, external services to deliver this information.

* Can you generate barcode for the visit code? When will that be useful?

  > Barcodes can include additional information like building name and can be scanned by another app eliminating manual data entry. How to generate the barcodes? Using barcode fonts? Images? External service?

* How to ensure user-friendly date formatting in the email body?

  > Localization in Power Apps including locale-specific formatting, currencies, timezones.

* Is it possible to generate a table with overstay information and send only single email?

  > Using variables, building more complex expressions, manipulating email format.

## Lab 04 Power BI

In this lab, you will build a Power BI dashboard that visualizes data about the campus visits.

Topics to discuss

-   Who is the target audience of the report?
-   How will the audience consume the report? Typical device? Location?
-   How to start the design; how to move beyond the blank canvas
-   Connect to data sources, build and refine data model 
-   Do you have sufficient data to visualise?
-   What are the possible characteristics you can use to analyse data about the visits?
-   Publishing and sharing the reports
-   Accessibility in Power BI when building interactive reports

### Challenges

* Dashboards and reports to include campus and building plans.

  > Bring maps, images, external data into the reports

* Report and analyze visiting patterns and trends.

  > Discussion of Power BI analytical and data processing capabilities.

* Visualization of overstayed visitors.

  > How to make reports more engaging. Talk about embedding Power Apps into Power BI to add data manipulation capabilities in response to the reports presented.

* Streaming Power BI for near real-time processing for a large campus.

  > This is a complex topic and the solutions most likely would be out of reach for most of the students but it's important to discuss data ageing, snapshots vs streams, frequency of data refreshes, stale data in general.

## Lab 05 Model-driven app

In this lab, you will build a Power Apps model-driven app to allow the backoffice campus staff to manage visit records across the entire campus.

Topics to discuss:

* Model-driven apps as part of a solution
* Model-driven vs canvas Power Apps. Target audience and app objectives.
* What makes a good sitemap?
* What to include into an app for a given entity?
* Apps & roles, security in CDS, UI trimming in model-driven apps
* Adjusting data model vs adjusting the model-driven app

### Challenges

* Select specific views and forms for Visits and Buildings

  > Fine-tuning the app for the target audience. Creating useful views and forms

* Security personnel typically work in a single building. How would you provide an easy way for them to display visits only for a selected building?

  > Personalization in model-driven apps, e.g. personal views. Grids and filtering. Pre-building fixed views if number of buildings is small. Subgrids (on Building form)

* How would you restrict access to specific entities, e.g. Buildings should be read-only for all staff members except the administrators?

  > Security roles, UI trimming. Potentially talk about reference data (user-owned vs organization-owned entities)

* What Dashboards would you consider adding to the app?

  > Built-in dashboards, embedded canvas, embedded Power BI