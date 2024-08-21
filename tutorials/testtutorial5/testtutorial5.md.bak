---
keywords: Azure
auto_validation: true
time: 10
tags: [ tutorial>intermediate, agreements:business_network_privacy_statement/nps, thismytag>mytagisgreat ]
author_name: Dmytro Ivanov
author_profile: https://github.com/IvanovDmytroA
contributors: [ Dmytro Ivanov>https://github.com/IvanovDmytroA, Oleksandra Kovtunenko > https://github.com/Oleksandra2 ]
primary_tag: software-product>sap-build
parser: v2
---
# Setup Azure Data Bucket with AI Core Test Tutorial
<!-- description --> For key user extensibility connect SAP Business Application Studio and an SAP S/4HANA Cloud system using SAML assertion authentication to develop custom UIs. If you want to create a custom SAP Fiori app with developer extensibility check out [Develop an SAP Fiori App to Trigger Purchase Requisitions API](https://developers.sap.com/group.sap-fiori-app-purchase-req.html)

## Prerequisites
- An existing Azure account with Admin access to create and use Azure Data store.
- TODO establish the setup prerequisites for SAP AI Core ??
![image](img/azure-dashboard.png)

>**IMPORTANT** Before you start this tutorial with SAP AI Launchpad, it is recommended that you should set up at least one other tool, either Postman or Python (SAP AI Core SDK) because some steps of this tutorial cannot be performed with SAP AI Launchpad.

## You will learn
- About Azure data store ???
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

<!-- description --> For key user extensibility connect SAP Business Application Studio and an SAP S/4HANA Cloud system using SAML assertion authentication to develop custom UIs. If you want to create a custom SAP Fiori app with developer extensibility check out [Develop an SAP Fiori App to Trigger Purchase Requisitions API](https://developers.sap.com/group.sap-fiori-app-purchase-req.html)

### Create Business Users and Assign Business Roles

Next we create a business user for the employee.  

YouTube

<iframe width="560" height="315" src="https://www.youtube.com/embed/ucZFrONCVZ4" frameborder="0" allowfullscreen></iframe>

DGL First

<iframe width="560" height="315" src="https://www.sap.com/dam/site/sapcom/multimedia/2024/05/3e00d7f2-be7e-0010-bca6-c68f7e60039b.mp4" frameborder="0" allowfullscreen></iframe>


To do this, select the radio button against the employee record created in step 2 and click "Maintain Business User".

![Maintain Business User](MaintainBusinessUser.png)

Once the business user is created, we can assign roles to the users.

You should be navigated to the "Maintain Business User" app automatically after creation of the business user. Here, click "Add" under the "Assigned Business Roles" section or alternately, click "Add Business Roles" to add relevant roles to this user

![Add Business Roles](AddBusinessRoles.png)

### Create Role From Template for Business Configurations

To handle business configuration entries, we have apps provided under the "Business Configuration" group on the Fiori Launchpad. To gain access to this group, a user needs to have the "BPC\_EXPERT" role assigned.

1. As administrator in the Fiori Launchpad for the consumer, open the "Maintain Business Roles" app
2. Click the "Create from Template" button and use the value help for template selection to choose "SAP\_BR\_BPC\_EXPERT"
![Business Process Configuration Export](BPCExpert.png)
3. This creates a new role with the required catalogs already assigned. Add the relevant business users to whom this role shall be assigned under the "Assigned Business Users" tab
![Users for BPC Expert](UsersForBPCExpert.png)
4. Maintain relevant restrictions for read/write using the "Maintain Restrictions" button
5. Save the role

### Custom Business Configurations

The users with assigned  SAP\_BR\_BPC\_EXPERT rsole should now be able to see the applications under the "Business Configuration" group of the Fiori Launchpad.

 ![Business Configuration](CustomBusinessConfig.png)

[OPTION BEGIN [Custom Business Configurations]]

The "Custom Business Configurations app" can be used to maintain data for configuration tables in the SaaS application if a business configuration maintenance object is registered. Refer [documentation](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/508d406ac92043dba95f694144803c26.html?locale=en-US) for more details

[OPTION END]

[OPTION BEGIN  [Upload Business Configuration]]

The "Upload Business Configuration" app can be used to upload data via excel import for various configuration tables of the SaaS application.

1. Open the "Upload Business Configuration" app.
2. Use the value help to select the object for which data has to be maintained.
3. Under the "Upload File" section, download the file template.
4. Fill in the downloaded template with suitable data conforming to the provided template.
5. Add attachment, review the data and confirm deployment.

![Upload Business Configuration](UploadBC.png)

[OPTION END]
