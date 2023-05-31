# Project: Azure Cloud resume Challenge

This README file provides an overview and instructions for setting up and hosting a static website on Azure storage using various technologies and services, including GitHub, Terraform, Azure Blob Storage, Azure CosmosDB, TableAPI, HTTPS, Azure CDN, Azure Functions, Python, JavaScript, and CI/CD.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
  - [Step 1: Clone the Repository](#step-1-clone-the-repository)
  - [Step 2: Configure Azure Resources](#step-2-configure-azure-resources)
  - [Step 3: Code the Website in HTML and CSS](#step-3-code-the-website-in-html-and-css)
  - [Step 4: Upload Website Files to Azure Blob Storage](#step-4-upload-website-files-to-azure-blob-storage)
  - [Step 4.5: Add Visitor Count using JavaScript](#step-45-add-visitor-count-using-javascript)
  - [Step 5: Set up Azure CDN](#step-5-set-up-azure-cdn)
  - [Step 6: Configure Azure Functions](#step-6-configure-azure-functions)
  - [Step 7: Enable HTTPS](#step-7-enable-https)
  - [Step 7.5: Deploy Azure CosmosDB and TableAPI](#step-75-deploy-azure-cosmosdb-and-tableapi)
  - [Step 8: Continuous Integration and Deployment (CI/CD)](#step-8-continuous-integration-and-deployment-cicd)
- [Conclusion](#conclusion)

## Introduction

This project aims to host a static website on Azure storage using various technologies and services. The project utilizes the following features:

- GitHub: Source code version control and collaboration platform.
- Terraform: Infrastructure as Code tool for provisioning and managing Azure resources.
- Azure Blob Storage: A scalable storage solution for storing website files.
- Azure CosmosDB: A globally distributed, multi-model database service for storing data.
- TableAPI: A service within Azure CosmosDB that provides a table-like data storage option.
- HTTPS: Secure communication protocol for encrypting data between clients and servers.
- Azure CDN: Content Delivery Network for efficient content delivery across the globe.
- Azure Functions: Serverless compute service for running event-driven code.
- Python: A programming language used for backend logic.
- JavaScript: A programming language used for frontend development.
- CI/CD: Continuous Integration and Deployment for automated build and deployment processes.

## Prerequisites

Before starting with the setup, ensure that you have the following prerequisites in place:

1. Azure account: Sign up for a free Azure account at https://azure.microsoft.com/.
2. Azure CLI: Install the Azure CLI on your local machine. You can find installation instructions at https://docs.microsoft.com/cli/azure/install-azure-cli.
3. GitHub account: Create a GitHub account at https://github.com/.

## Setup Instructions

Follow the step-by-step instructions to set up and host your static website on Azure storage:

### Step 1: Clone the Repository

1. Clone the project repository from GitHub to your local machine:

```shell
git clone https://github.com/your-username/your-repository.git
```

2. Change your working directory to the cloned repository:

```shell
cd your-repository
```

### Step 2: Configure Azure Resources

1. Open the

 Azure CLI and sign in to your Azure account:

```shell
az login
```

2. Set the desired subscription where you want to create the resources:

```shell
az account set --subscription <subscription-id>
```

3. Modify the Terraform configuration files (`*.tf`) in the repository to match your desired Azure resource configuration. You may need to specify the resource group, storage account name, function app name, etc.

4. Initialize Terraform within the repository directory:

```shell
terraform init
```

5. Create the Azure resources using Terraform:

```shell
terraform apply
```

### Step 3: Code the Website in HTML and CSS

1. Create an HTML file (e.g., `index.html`) in your local repository.

2. Add the necessary HTML structure, including `<html>`, `<head>`, and `<body>` tags.

3. Design and layout your website using HTML elements and CSS styles within the `<body>` section. You can use CSS styles inline or link an external CSS file.

4. Create additional HTML files for other pages if needed, following the same structure and adding unique content for each page.

### Step 4: Upload Website Files to Azure Blob Storage

1. Create a container within your Azure Blob Storage account to store the website files.

2. Upload your static website files to the created container using Azure Storage Explorer or any Azure Blob Storage client tool.

### Step 4.5: Add Visitor Count using JavaScript

1. In your HTML file(s), add a placeholder element (e.g., `<span id="visitorCount"></span>`) where you want the visitor count to be displayed.

2. Create a JavaScript file (e.g., `visitorCount.js`) in your local repository.

3. In the JavaScript file, use the following code to increment the visitor count and update the placeholder element:

```javascript
// Get the visitor count from Azure CosmosDB TableAPI or initialize it to 0
let visitorCount = 0;

// Function to update the visitor count element
function updateVisitorCount() {
  const visitorCountElement = document.getElementById('visitorCount');
  visitorCountElement.textContent = visitorCount;
}

// Function to increment the visitor count
function incrementVisitorCount() {
  visitorCount++;
  updateVisitorCount();
}

// Call the incrementVisitorCount function when the page loads or on specific events
window.addEventListener('DOMContentLoaded', incrementVisitorCount);
```

4. Link the JavaScript file in your HTML file(s) by adding the following line within the `<head>` or `<body>` section:

```html
<script src="visitorCount.js"></script>
```

### Step 5: Set up Azure CDN

1. Create a new Azure CDN profile and configure it to use the Azure Blob Storage container as the origin.

2. Enable the CDN endpoint and configure custom domain mappings if required.

### Step 6: Configure Azure Functions

1. Create a new Azure Functions app in the Azure portal.

2. Implement your desired serverless logic using Python or JavaScript within the Functions app.

### Step 7: Enable HTTPS

1. Obtain an SSL certificate for your custom domain using a certificate authority or a service like Let's Encrypt.

2. Configure the Azure CDN endpoint to use the obtained SSL certificate.

### Step 7.5: Deploy Azure CosmosDB and TableAPI

1. Create an Azure CosmosDB account in the Azure portal.

2. Create a new TableAPI within the CosmosDB account to store your table-like data, including the visitor count.

3. Connect your application or functions to the CosmosDB TableAPI and perform necessary CRUD operations to store and retrieve the visitor count.

### Step 8: Continuous Integration and Deployment (CI/CD)

1. Set up a CI/CD pipeline

 using Azure DevOps, GitHub Actions, or any other preferred CI/CD tool.

2. Configure the pipeline to trigger on code changes and automatically build, test, and deploy your static website and serverless functions to Azure.

## Conclusion

By following the above setup instructions, you can successfully host your static website on Azure storage, leveraging various Azure services such as Blob Storage, Azure CDN, Azure Functions, and Azure CosmosDB TableAPI. Additionally, the use of GitHub, Terraform, Python, JavaScript, and CI/CD enables efficient development, deployment, and management of your website and related resources. The visitor count is stored and retrieved using Azure CosmosDB TableAPI, ensuring accurate and persistent tracking of visitors on your website.
