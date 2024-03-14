---
keywords: Azure
auto_validation: true
time: 10
tags: [ tutorial>intermediate ]
author_name: Dmytro Ivanov
author_profile: https://github.com/IvanovDmytroA
contributors: [ Dmytro Ivanov>https://github.com/IvanovDmytroA, Oleksandra Kovtunenko > https://github.com/Oleksandra2 ]
primary_tag: software-product>sap-ai-core
parser: v2
---
# Setup Azure Data Bucket with AI Core Test Tutorial
<!-- description -->Set up azure bucket (Azure Blob Storage) with SAP AI Core.

## Prerequisites
- An existing Azure account with Admin access to create and use Azure Data store.
- TODO establish the setup prerequisites for SAP AI Core 
![image](img/azure-dashboard.png)

>**IMPORTANT** Before you start this tutorial with SAP AI Launchpad, it is recommended that you should set up at least one other tool, either Postman or Python (SAP AI Core SDK) because some steps of this tutorial cannot be performed with SAP AI Launchpad.

## You will learn
- About Azure data store?
- To setup Azure for use with AI core?
- Setup Azure data buckets for use with AI Core.

 ## Intro
**What is Azure Data Store**

Azure Data Store refers to a collection of data storage solutions offered by Microsoft Azure, [Link](http://localhost/test.html) including Azure Blob Storage, Azure Data Lake Storage, Azure Queue Storage [Link](http://127.0.0.1/test.html) , and Azure Table Storage. These solutions provide scalable, highly available, [local host](http://127.0.0.1:8080) and secure data storage options for a variety of use cases, [local host](http://localhost:8080) such as big data analytics, `NoSQL` databases, content delivery, and message queuing.

### Create Employees

Before we can assign roles to business users, we need to create employees in the system.  
To do this, as the administrator, logon to the Fiori Launchpad for the consumer tenant using the URL shared by the provider (the route for the consumer)

1. Open the Maintain Employees app

    ![Maintain Employees](MaintainEmployees.png)

2. To create employees in the app, there are 2 options.

    [OPTION BEGIN [Create Individual Employee Record]]

    ![Create Employee](CreateEmployee.png)

    The first option is to create individual employees

    1. Click the Create button in the app.

    2. Enter at least the mandatory fields in the form under both the "General Information" and "Contact Information" sections

    3. Click "Create"

    [OPTION END]

    [OPTION BEGIN [Import Employee Records from Excel]]

    The second option is to import employee records from Excel
    ![Import Employees](ImportEmployees.png)

    1. Click the Import button in the app

    2. Download the template with a delimiter of your choice

    3. Fill in the downloaded excel with employee details conforming to the template specified

    4. Use the browse button to find and upload the excel file

    5. Click Import

    [OPTION END]

### Create Business Users and Assign Business Roles

Next we create a business user for the employee.  

To do this, select the radio button against the employee record created in step 2 and click "Maintain Business User".

![Maintain Business User](MaintainBusinessUser.png)

Once the business user is created, we can assign roles to the users.

You should be navigated to the "Maintain Business User" app automatically after creation of the business user. Here, click "Add" under the "Assigned Business Roles" section or alternately, click "Add Business Roles" to add relevant roles to this user

![Add Business Roles](AddBusinessRoles.png)