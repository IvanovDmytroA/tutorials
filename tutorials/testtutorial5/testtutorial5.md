---
keywords: Azure
auto_validation: true
time: 10
tags: tags: [ tutorial>intermediate, topic>cloud, software-product>sap-business-technology-platform, software-product>sap-build, software-product>sap-build-work-zone--advanced-edition,
software-product>sap-build-apps, software-product>sap-build-process-automation ]
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

### Create a Development Package

Create your own ABAP development package, which will serve as the basis for the development artifacts to be created.

1. Open Eclipse and connect to your system.

2. Right click the main package `ZLOCAL` and choose **New > ABAP Package**.

3. Create your own ABAP development package as a sub package of `ZLOCAL` using Software Component `ZLOCAL`. Create a new Transport Request for this purpose.
    <ol type="a"><li>Name: `ZBPA2X`
    </li><li>Description: `BP A2X Outbound Call Tutorial`</li></ol>

### Create an Outbound Service

Create an outbound service object, which models the outbound call that will be implemented. The outbound service will be part of a custom communication scenario.

1. Mark the created package under `ZLOCAL` or in Favorite Packages and click on **File** and choose **New > Other... > Outbound Service**:

    ![Create Outbound Service](create_outbound_service.png)

2. Provide:
    <ol type="a"><li>Outbound Service: `ZBPA2X_OBS_BUPA`
    </li><li>Description: `Business Partner Outbound Service`
    </li><li>Service Type: `HTTP Service`

      ![Create Outbound Service 2](create_outbound_service_2.png)</li></ol>

3. Choose **Next**

4. Use the transport request created before and choose **Finish**.

### Create a Communication Scenario

Create a communication scenario and assign the outbound service to it. This will be the basis for the outbound communication arrangement, which will be configured by an administrator at a later point. Keep in mind that the developer defines which authentication methods are supported, while the administrator decides which authentication method is ultimately used at runtime.

1. In ADT, mark the created package under `ZLOCAL` or in Favorite Packages and click on **File** and choose **New > Other... > Communication Scenario**:

    ![Create Communication Scenario](create_communication_scenario.png)

2. Provide:
    <ol type="a"><li>Name: `ZBPA2X_CS_BUPA`
    </li><li>Description: `Business Partner Outbound Service Call`

    ![Create Communication Scenario 2](create_communication_scenario_2.png)</li></ol>

3. Use the transport request created before and choose **Finish**

4. Select "One instance per client" from the **Allowed Instances** dropdown list

    ![Create Communication Scenario 3](create_communication_scenario_3.png)

5. Choose Tab **Outbound** and Add the Outbound Service created before: `ZBPA2X_OBS_BUPA_REST`

6. Verify that the Authentication Methods **Basic** and **OAuth 2.0** are selected and choose **SAML 2.0 Bearer Assertion** from the dropdown list of the **OAuth 2.0 Grant Type**

    ![Create Communication Scenario 4](create_communication_scenario_4_2.png)

7. Save the communication scenario.

8. Choose **Publish Locally**.

### Download Service Metadata File

Obtain the service metadata file to be able to create the service consumption model in the next step.

1. In the browser access the business Partner API directly in the SAP Business Accelerator Hub. Use [Business Partner (A2X)](https://api.sap.com/api/API_BUSINESS_PARTNER/overview)

2. Choose API Specification

3. Choose to download the EDMX file

### Create a Service Consumption Model

Create a service consumption model for the targeted OData service from the metadata file. This generates a number of proxy objects and greatly simplifies the remote service call in your ABAP code.

1. In ADTs, marks the package created in the previous tutorial of this tutorial group (`ZBPA2X`) under `ZLOCAL` or in Favorite Packages and click on **File** and choose and **New > Other... > Service Consumption Model**:

2. Provide:
    <ol type="a"><li>Name: `ZBPA2X_SCM_BUPA`  
    </li><li>Description: `Service Consumption Model Business Partner`
    </li><li>Remote Consumption Mode: `OData`

    ![Create Service Consumption Model 2](create_service_consumption_model_2.png)</li></ol>

3. Choose **Next**

4. Provide the Service Metadata File of the OData service, that you downloaded in the previous step

    ![Create Service Consumption Model 3](create_service_consumption_model_3.png)

5. Choose **Next**

6. On the **Components of OData Service** screen, Choose **Next**

7. On the **ETag Support** screen, choose **Next**

8. Select a transport request and choose **Finish**

The creation of the Service Consumption Model can take a few seconds. Save and activate the Service Consumption Model

### Next Step

We believe that community is for everyone, and we welcome you to ours! We are here to help you on your learning journey!