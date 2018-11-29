
# Anypoint Template: API Led Connectivity System API for SAP

<!-- Header (start) -->

This template helps you design an Account System API. It provides a means of hiding the complexity of the SAP APIs implementation from a user while exposing data in a canonical format. The template abstracts account data from a SAP system into canonical objects that are defined within a CRM System API. This API uses JSON as an exchange format and translates calls into the semantic data structure required by SAP.

![7db56754-7c0e-4567-a42b-1942acbedc33-image.png](https://exchange2-file-upload-service-kprod.s3.us-east-1.amazonaws.com:443/7db56754-7c0e-4567-a42b-1942acbedc33-image.png)

![93a34b7c-749d-4816-9eb5-46c09891bbe4-image.png](https://exchange2-file-upload-service-kprod.s3.us-east-1.amazonaws.com:443/93a34b7c-749d-4816-9eb5-46c09891bbe4-image.png)

![b2a9eef7-9ea2-4eec-97cd-242ebd2334ca-image.png](https://exchange2-file-upload-service-kprod.s3.us-east-1.amazonaws.com:443/b2a9eef7-9ea2-4eec-97cd-242ebd2334ca-image.png)

![ff8e425f-35e6-4e69-bb74-6178ea12acc3-image.png](https://exchange2-file-upload-service-kprod.s3.us-east-1.amazonaws.com:443/ff8e425f-35e6-4e69-bb74-6178ea12acc3-image.png)

![15f732f9-a475-4aac-997b-b0ef7f308b41-image.png](https://exchange2-file-upload-service-kprod.s3.us-east-1.amazonaws.com:443/15f732f9-a475-4aac-997b-b0ef7f308b41-image.png)

![d249895f-a29b-4004-8399-853826dda8ca-image.png](https://exchange2-file-upload-service-kprod.s3.us-east-1.amazonaws.com:443/d249895f-a29b-4004-8399-853826dda8ca-image.png)


## Operations

The CRM System API supports the following operations:

GET/accounts
POST/accounts
GET/account/{id}
PUT/accounts/{id}
DELETE/accounts/{id}

### License Agreement

Using this template is subject to the conditions of this <a href="https://github.com/mulesoft/template-sfdc2nets-opportunity-aggregation/blob/4.1/AnypointTemplateLicense.pdf">License Agreement</a>. Review the terms of the license before downloading and using this template. In short, you are allowed to use the template for free with Mule Enterprise Edition, CloudHub, or as a trial in Anypoint Studio.

## Use Case

<!-- Use Case (start) -->

This template serves as a foundation for the API led connectivity approach of running an enterprise.
The template is a system API to an underlying SAP system.

This template is a REST API implemented using APIkit and RAML definition. The basic CRUD operations are implemented for an account object (customer). The API uses JSON as an exchange format. Included are example requests and responses.

The sections that follow provide the endpoints for this template.

### GET /accounts

Retrieves accounts from an SAP system based on the combination of query parameters. Set at least one of `modifiedAfter` or `name` to retrieve the results. See the included RAML definition to learn more about the implemented query parameters.

### POST /accounts

Inserts a new account into the SAP system (customer).

### GET /accounts/{id}

Retrieves a customer account based on an SAP native identifier.

### PUT /accounts/{id}

Updates a customer account with the data in the HTTP request. All fields are overwritten.

### DELETE /accounts/{id}

Deletes a customer account based on an SAP native identifier.

See the included self-descriptive RAML definition and the corresponding flows to learn more about the application.

# Considerations

<!-- Default Considerations (start) -->

<!-- Default Considerations (end) -->

<!-- Considerations (start) -->

To make this template run, there are certain preconditions that must be considered. All of them deal with the preparations, that must be made in order for all to run smoothly. Failing to do so could lead to unexpected behavior of the template.


# Run it!

Simple steps to get this template running. To run this template with Maven, you need extra dependencies
to the pom.xml file for SAP.


## Running On Premises

In this section we detail the way you should run your template on your computer.

<!-- Running on premise (end) -->

### Where to Download Anypoint Studio and the Mule Runtime

If you are new to Mule, download this software:

- [Download Anypoint Studio](https://www.mulesoft.com/platform/studio)
- [Download Mule runtime](https://www.mulesoft.com/lp/dl/mule-esb-enterprise)


<!-- Where to download (end) -->

### Importing a Template into Studio

In Studio, click the Exchange X icon in the upper left of the taskbar, log in with your Anypoint Platform credentials, search for the template, and click Open.

<!-- Importing into Studio (end) -->

### Running on Studio

After you import your template into Anypoint Studio, follow these steps to run it:

- Locate the properties file `mule.dev.properties`, in src/main/resources.
- Complete all the properties required as per the examples in the "Properties to Configure" section.
- Right click the template project folder.
- Hover your mouse over `Run as`.
- Click `Mule Application (configure)`.
- Inside the dialog, select Environment and set the variable `mule.env` to the value `dev`.
- Click `Run`.

See [Configure the SAP connector in Studio 7](https://docs.mulesoft.com/connectors/sap/sap-connector#configure-in-studio)

<!-- Running on Studio (end) -->

### Running on Mule Standalone

Update the properties in one of the property files, for example in the mule.prod.properties file, and run your app with a corresponding environment variable. In this example, use `mule.env=prod`. 

## Running on CloudHub

When creating your application in CloudHub, go to Runtime Manager > Manage Application > Properties to set the environment variables listed in "Properties to Configure" as well as the mule.env value.

Once your app is all set and started, there is no need to do anything else. Every time a lead is created or modified, the template automatically synchronizes to Salesforce Org B as long as it has an email address.

### Deploying a Template in CloudHub

In Studio, right click your project name in Package Explorer and select Anypoint Platform > Deploy on CloudHub.

<!-- Deploying on Cloudhub (end) -->


## Properties to Configure

To use this template, you need to configure properties (Credentials, configurations, etc.) either in properties file or in CloudHub as Environment Variables. Detail list with examples:

### Application Configuration

**Common Configuration**

+ http.port `9090`

**SAP Connector Configuration**

+ sap.jco.ashost `your.sap.address.com`
+ sap.jco.user `SAP_USER`
+ sap.jco.passwd `SAP_PASS`
+ sap.jco.sysnr `14`
+ sap.jco.client `800`
+ sap.jco.lang `EN`
+ sap.default.accountGroup `ZAG1`

**API Configuration**

+ api.domain `your-sap-api.cloudhub.io`
+ api.basePath `/api`

# Customize It!

This brief guide provides a high level understanding of how this template is built and how you can change it according to your needs. As Mule applications are based on XML files, this page describes the XML files used with this template. More files are available such as test classes and Mule application files, but to keep it simple, we focus on this XML file:

* template-apiled-system-account-sap.xml

<!-- Customize it (end) -->

## template-apiled-system-account-sap.xml

A functional aspect of this template implemented in this XML is to create or update objects in the destination system for a represented use case. You can customize and extend the logic of this Anypoint Template in this XML to more specifically meet your needs.

Configuration for connectors and properties place holders are also set in this file. Even though you can change the configuration here, all parameters that can be modified are in a properties file, and this is the recommended place to do it so. If you want to do core changes to the logic you need to modify this file.

In the visual editor the parameters in this file can be found on the *Global Element* tab.

<!-- Config XML (start) -->
<!-- Config XML (end) -->
<!-- Default Config XML (start) -->
<!-- Default Business Logic XML (start) -->
<!-- Business Logic XML (start) -->
<!-- Business Logic XML (end) -->
<!-- Default Endpoints XML (start) -->
<!-- Endpoints XML (start) -->
<!-- Endpoints XML (end) -->
<!-- Default Error Handling XML (start) -->
<!-- Error Handling XML (start) -->
<!-- Error Handling XML (end) -->
<!-- Extras (start) -->
<!-- Extras (end) -->


