# Building a Multimodal RAG Solution with Copilot Studio

### Overall Estimated Duration : 4 Hours

## Overview

This hands-on lab guides participants through building and automating a Retrieval-Augmented Generation (RAG) solution using Copilot Studio. Participants will explore how to ingest diverse data sources while leveraging AI models like text embeddings, language models, and generative AI capabilities. The lab will cover customizing topics, automating workflows. Additionally, participants will learn to publish the solution to custom channels as websites. 

## Objective

Learn to build and automate a Retrieval-Augmented Generation (RAG) solution using Copilot Studio, leveraging AI models like text embeddings, language models, and generative AI. By the end of this lab, you will get insights on these concepts:

- **Introduction to Retrieval-Augmented Generation (RAG) Automation and Copilot Studio :** Understanding foundational concepts and practical applications of Retrieval-Augmented Generation (RAG).

- **Data Ingestion and Preprocessing :** Learn to ingest data into a system powered by Azure AI tools and preprocess it using GPT-4 Turbo and text embedding models.

- **Integrating AI Search with Copilot Studio :** Understand how to integrate AI Search with Copilot Studio to enhance your AI-powered workflows.

- **Deployment and Publishing Options :** Learn integrating Retrieval-Augmented Generation (RAG) with custom platforms, with an emphasis on deploying the solution to a public demo website.

## Pre-requisites

Participants should have the following prerequisites:

- **Familiarity with Azure Resources:** Basic understanding of Azure services and the Azure portal for managing cloud resources.

- **Knowledge of Copilot Studio:** Familiarity with Copilot Studio and its capabilities for building AI-driven solutions.

- **Understanding of RAG Concepts:** Basic knowledge of Retrieval-Augmented Generation (RAG) and its applications in AI workflows.

## Architecture

The architecture facilitates the seamless ingestion and retrieval of data for user interactions in Copilot Studio. Documents are stored in Azure Blob Storage, which serves as the source for data ingestion. AI Studio processes these documents using models from Azure AI Services via the chat playground. The processed data is indexed using AI Search, allowing efficient retrieval. Finally, Copilot Studio enables user interactions, including Q&A, by leveraging the indexed data for intuitive and responsive workflows.

## Architecture Diagram

![](../media/rag-archi.png)

## Explanation of Components

The architecture for this lab involves several key components:

- **Azure Blob Storage:** Serves as the primary data repository, storing documents that will be ingested into the system. This ensures secure and scalable storage for unprocessed data.

- **AI Studio:** Acts as the ingestion layer where documents from Azure Blob Storage are processed. It leverages Azure AI Services to apply language models for extracting relevant information and preparing it for indexing.

- **Azure AI Services:** Provides the advanced AI models, including language understanding and generative capabilities, used by AI Studio to extract data and process user interactions efficiently.

- **Azure AI Search:** Creates semantic indexes from the processed data, enabling efficient and meaningful retrieval of information. This component supports enhanced search capabilities by understanding user queries contextually.

- **Copilot Studio:** Facilitates user interaction by connecting to Azure AI Search for Q&A and other workflows. It provides an intuitive interface for leveraging indexed data and AI capabilities in real-time.

## Getting Started with Lab

Welcome to Building a Multimodal RAG Solution with Copilot Studio Hands-On-Lab! , We've prepared a seamless environment for you to explore and learn. Let's begin by making the most of this experience.

>**Note:** If a PowerShell window appears once the environment is active, please don't close it. Minimize it instead of closing it and proceed with the tasks.

### Accessing Your Lab Environment

Once you're ready to dive in, your virtual machine and Lab guide will be right at your fingertips within your web browser.

![](../media/gs-1.png)

### Exploring Your Lab Resources

To get a better understanding of your Lab resources and credentials, navigate to the Environment tab.

![](../media/gs-2.png)

### Utilizing the Split Window Feature

For convenience, you can open the Lab guide in a separate window by selecting the Split Window button from the Top right corner

![](../media/gs-3.png)

### Managing Your Virtual Machine

Feel free to start, stop, or restart your virtual machine as needed from the Resources tab. Your experience is in your hands!

![](../media/gs-4.png)

## Let's Get Started with Azure Portal

1. In the JumpVM, click on **Azure portal** shortcut of Microsoft Edge browser which is created on desktop.

   ![](../media/gs-8.png)

1. On the **Sign into Microsoft Azure** tab, you will see the login screen. Enter the provided email or username, and click **Next** to proceed.

   - Email/Username: <inject key="AzureAdUserEmail"></inject>

     ![](../media/gs-6.png)

1. Now, enter the following password and click on **Sign in**.

   - Password: <inject key="AzureAdUserPassword"></inject>

     ![](../media/gs-7.png)

1. If an **Action required** pop-up window appears, click on **Next**.

   ![Ask Later](../media/ask-later.png)

1. On **Start by getting the app** page, click on **Next**.

1. Click on **Next** twice.

1. In **Android**, go to the Play Store, search for **Microsoft Authenticator,** and tap on **Install**.

   ![Install](../media/mobile.jpg)

   >Note: For **iOS**, open the App Store and repeat the steps.

   >Note: Skip If already installed.
   
1. Open the app and click on **Scan a QR code**.

1. Scan the **QR code (1)** visible on the screen and click on **Next (2)**.

   ![QR code](../media/demo001.png)

1. Enter the digit displayed on the screen in the Authenticator app on mobile and tap on **Yes**.
1. Once the notification is approved, click on **Next (1)**.

   ![Approved](../media/demo002.png)

1. Click on **Done**.
1. If prompted to stay signed in, you can click **"Yes."**

1. Tap on **Finish** in the mobile device.

   >NOTE: While logging in again, enter the digits displayed on the screen in the **Authenticator app** and click on Yes.

1. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **"Cancel"** to skip the tour.

1. You can use the **Previous (1)** and **Next (2)** buttons to navigate through the lab guide.

   ![](../media/lc-image(3).png)



## Creating Environment in Power Platform

1. From your browser, navigate to **Power Platform Admin Center** using this link [Power Platform](https://admin.powerplatform.microsoft.com/)

1. If the **Sign in** page is prompted, use the provided credentials to sign in to Power Platform and click **Next**.

   - Email/Username: <inject key="AzureAdUserEmail"></inject>

     ![alt text](image.png)

1. Now, enter the following password and click on **Sign in**.

   - Password: <inject key="AzureAdUserPassword"></inject>

     ![alt text](image-1.png)
   
1. On the **Stay signed in** pane, click on **No**.

   ![alt text](image-2.png)

1. Once signed in, toggle **Try the new admin center** button to use new experience.

   ![alt text](image-3.png)

1. Once you are in the **Power Platform Admin center** page, select **Manage (1)** from left menu and click on **+ New (2)**, to create a new environment.

   ![alt text](image-5.png)

1. In the **New environment** page, provide the following details and click on **Next (5)** :

   - **Name**: provide as **odl_user_<inject key="DeploymentID" enableCopy="false" />_env** **(1)**.

   - **Get new features early**: Toggle this option to **No (2)**.

   - **Type**: Select **Developer (3)** from dropdown.

   - **Add a Dataverse data store**: Toggle this option to **Yes (4)**.

     ![](../media/image-6.png)

1. Once configurations are done, click on **Save**.

      ![](../media/getstart1.png)

1. Now the environment creation will start, please wait till the **State** changes from **Preparing** to **Ready**.

   ![alt text](image-10.png)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on the **Next** from lower right corner to move on next page.

![](../media/gs-5.png)

## Happy Learning!!

