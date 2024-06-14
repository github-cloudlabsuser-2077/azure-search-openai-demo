# ChatGPT-like app with your data using Azure OpenAI and Azure AI Search (Python)

This repository contains the backend code for a ChatGPT-like application written in Python. There are also JavaScript, .NET, and Java samples available based on this code. To learn more about developing AI apps using Azure AI Services, visit the [Azure AI Services documentation](https://aka.ms/azai).

## Table of Contents

- [Features](#features)
- [Azure account requirements](#azure-account-requirements)
- [Azure deployment](#azure-deployment)
- [Sharing environments](#sharing-environments)
- [Using the app](#using-the-app)
- [Running locally](#running-locally)
- [Monitoring with Application Insights](#monitoring-with-application-insights)
- [Customizing the UI and data](#customizing-the-ui-and-data)
- [Productionizing](#productionizing)
- [Clean up](#clean-up)
- [Troubleshooting](#troubleshooting)
- [Resources](#resources)

## Features

- Chat (multi-turn) and Q&A (single turn) interfaces
- Renders citations and thought process for each answer
- Includes settings directly in the UI to tweak the behavior and experiment with options
- Integrates Azure AI Search for indexing and retrieval of documents, with support for various document formats
- Optional usage of GPT-4 with vision to reason over image-heavy documents
- Optional addition of speech input/output for accessibility
- Optional automation of user login and data access via Microsoft Entra
- Performance tracing and monitoring with Application Insights

## Azure account requirements

To deploy and run this example, you'll need the following:

- Azure account: If you're new to Azure, you can [get an Azure account for free](https://azure.microsoft.com/free/cognitive-search/) and receive free Azure credits to get started.
- Azure subscription with access enabled for the Azure OpenAI service: You can request access using [this form](https://aka.ms/oaiapply). If you don't have access to the Azure OpenAI service, you can use the [OpenAI public API](https://platform.openai.com/docs/api-reference/introduction) instead.
- Azure account permissions: Your Azure account must have the necessary permissions, such as `Microsoft.Authorization/roleAssignments/write` and `Microsoft.Resources/deployments/write` on the subscription level.

## Azure deployment

To deploy the application to Azure, follow these steps:

1. Estimate the costs using the [Azure pricing calculator](https://azure.com/e/d18187516e9e421e925b3b311eec8aae).
2. Set up the project using one of the available options: GitHub Codespaces, VS Code Dev Containers, or a local environment.
3. Run the `azd up` command to provision Azure resources and deploy the application code.
4. After the deployment is complete, you can access the application using the provided URL.

## Sharing environments

To give someone else access to a deployed environment, follow these steps:

1. Install the Azure CLI.
2. Run `azd init -t azure-search-openai-demo` or clone this repository.
3. Run `azd env refresh -e {environment name}` and provide the necessary information.
4. Set the `AZURE_PRINCIPAL_ID` environment variable to the Azure ID of the user.
5. Run the `./scripts/roles.ps1` or `.scripts/roles.sh` script to assign the necessary roles to the user.

## Using the app

Once the app is deployed, you can access it either in Azure or by running it locally. The app provides chat and Q&A interfaces, and you can customize its behavior and options through the UI.

## Running locally

To run the app locally, follow these steps:

1. Run `azd auth login` to log in to your Azure account.
2. Change to the `app` directory.
3. Run the `./start.ps1` or `./start.sh` script to start the project locally.

## Monitoring with Application Insights

The deployed app uses Application Insights for performance tracing and error logging. You can view the performance data and exceptions in the Azure portal.

## Customizing the UI and data

Once the app is deployed, you can customize it by changing the text, prompts, and data. Refer to the app customization guide and data ingestion guide for more details.

## Productionizing

Before deploying the app to production, make sure to review the security and performance aspects. Refer to the productionizing guide for more details.

## Clean up

To clean up the resources created by this sample, run the `azd down` command and confirm the deletion of the resources.

## Troubleshooting

If you encounter any issues, refer to the troubleshooting section or post in the GitHub Issues for assistance.

## Resources

- Additional documentation for this app
- [Revolutionize your Enterprise Data with ChatGPT: Next-gen Apps w/ Azure OpenAI and AI Search](https://aka.ms/entgptsearchblog)
- [Azure AI Search documentation](https://learn.microsoft.com/azure/search/search-what-is-azure-search)
- [Azure OpenAI Service documentation](https://learn.microsoft.com/azure/cognitive-services/openai/overview)
- [Comparing Azure OpenAI and OpenAI](https://learn.microsoft.com/azure/cognitive-services/openai/overview#comparing-azure-openai-and-openai/)
- [Access Control in Generative AI applications with Azure Cognitive Search](https://techcommunity.microsoft.com/t5/ai-azure-ai-services-blog/access-control-in-generative-ai-applications-with-azure/ba-p/3956408)
- [Video overview of the app](https://www.youtube.com/watch?v=3acB0OWmLvM)
- [AI Chat App Hack series](https://www.youtube.com/playlist?list=PL5lwDBUC0ag6_dGZst5m3G72ewfwXLcXV)
