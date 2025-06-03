# Challenge: Develop a Health Symptom and Disease Identification Copilot agent using Azure OpenAI and Copilot Studio

### Estimated Time: 4 Hours
  
## Problem Statement

Develop an intelligent health symptom identification bot that helps individuals to assess potential diseases based on the symptoms they experience. The system will allow users to input their symptoms, which will then be matched against a database of diseases. The system will return a list of possible diseases associated with the provided symptoms, including their severity level, a brief yet informative description of each disease, and tailored precautionary steps or recommendations to manage or prevent further complications.

## Goals

- Match the input symptoms to a list of diseases.

- Display a brief description of each disease.

## Datasets 

- Download and extract the datasets for this challenge using the [symptoms_datasets](https://github.com/CloudLabsAI-Azure/Building-a-Multimodal-RAG-Solution-with-Copilot-Studio-/archive/refs/heads/health-Dataset.zip) link. Please make sure you extract these files inside `C:\LabFiles`.

## Challenge Objectives  

1. **Azure Blob Storage Deployment:**

   - Set up an Azure Blob Storage account with SKU size **Standard_LRS**.

   - Deploy it in the existing resource group named **rag-hack**.

   - Ensure to provide the Azure Blob Storage account name as **blobstorage<inject key="Deployment ID" enableCopy="false"/>**.

   - Create a container named **datasets**, upload the datasets that you have downloaded earlier.

<validation step="7f1b4150-b57b-4e7b-9166-bd595f0a3d67" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.

2. **Azure AI Search Resource Deployment:**

   - Set up an Azure AI Search resource with **Standard** tier.

   - Deploy it in the existing resource group named **rag-hack**.

   -  Ensure to provide the Azure AI Search resource name as: **aisearch-<inject key="Deployment ID" enableCopy="false"/>**.

   - Copy the **URL** and **API Key** from the portal.

<validation step="3cec0c47-4ff7-4f1d-bc56-408a726ec7a9" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.

3. **Azure OpenAI Service Deployment :**

   - Set up an Azure OpenAI Service instance with SKU size **Standard S0**.

   - Deploy it in the existing resource group named **rag-hack**.

   -  Ensure to provide the Azure OpenAI Service name as: **OpenAI-<inject key="Deployment ID" enableCopy="false"/>**.

   - Navigate to  **OpenAI Studio** and deploy two models using the deployments option.

   - Deploy the **GPT-4 model** and the **Text-Embedding** model within the Azure OpenAI Service from OpenAI Studio.

   - From the Chat Playground in OpenAI Studio, use the **Add Data Source** option to select Blob Storage as the source. Then, connect it with Azure AI Search to create **vectorized indexes** and provide index name as **sym-index**.

<validation step="d6035f5d-cc07-4e66-8271-37cf195e8637" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.

4. **Copilot Studio Setup and Agent Creation:**

   - Access the Copilot Studio which you had opened earlier.

   - Create New Agent and provide the necessary details and name as **DiseaseIdentification Agent**.

<validation step="6d13fe0f-eed0-4d55-86d5-9f88bf2abeef" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.

5. **Topic Creation and Knowledge Base Integration:**

   -  Create new topic and name the topic as **sym-topic**.

   - Setup trigger phrases and configure the workflow.

   - In the newly created topic, add a Generative Answers node and configure it to pull answers from the Knowledge Base.

   - Add previously created **AI Search** resource as Knowledge base.

   - Make sure the responses are retrived only from the selected **Knowledge Base**.

   - Test the agent with some prompts like:

     - `I'm feeling chest pain and difficulty breathing, should I be worried about any particular disease?`

     - `How does the severity of conditions like depression and anxiety compare with physical diseases such as pneumonia and tuberculosis?`

<validation step="5425a04a-c3a5-4aef-8c8c-9bcf2df1ecbf" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.

6. **Publishing the Agent as Web App from Copilot Studio:**

   - Disable **authentication** from settings in Copilot Studio.

   - Configure **Demo Web App** as the channel to publish the agent.

   - Publish the agent, use the **URL** to navigate to the App.

<validation step="4588c822-71a3-4d4a-984f-8e8e343017c8" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.

## Success Criteria  

- Verify the agent by testing it with all the provided prompts to ensure it responds correctly and functions as expected:

  - `I have a rash and fever, could this be a viral infection?`

  - `Can you provide a summary of the symptoms and precautions for common respiratory diseases like the common cold, flu, and pneumonia?`

  - `I have a sore throat and fever, what diseases could this be?`

  - `I've been coughing and feeling short of breath, what conditions should I check?`

  - `Please list the diseases that require vaccination and give me a brief explanation of why they are important to prevent`

  - `I'm feeling chest pain and difficulty breathing, should I be worried about any particular disease?`

  - `Can you recommend simple precautions for managing chronic conditions like diabetes, hypertension, and asthma?`

  - `How does the severity of conditions like depression and anxiety compare with physical diseases such as pneumonia and tuberculosis?`

  - `I'm having digestive problems with bloating and irregular bowel movements, what conditions could this be?`

  - `I have a headache, nausea, and sensitivity to light, what could be causing this?`

- The agent should be deployed as a web app and made accessible online.

- Make sure that all validations are successful.

## Additional Resources:

- Refer to the [Copilot Studio Documentation](https://learn.microsoft.com/en-us/microsoft-copilot-studio/) for any clarifications or guidance during the challenge.

- Refer to the [Add your Own Data](https://learn.microsoft.com/en-us/azure/ai-services/openai/use-your-data-quickstart?tabs=command-line%2Cjavascript-keyless%2Ctypescript-keyless%2Cpython-new&pivots=ai-foundry-portal) for any clarifications or guidance during the challenge.

- You can use the previous day’s lab guides as a reference to complete the challenge.

## Conclusion  

In this challenge, you have successfully developed a Disease Identification System using AI-powered technologies, with significant assistance from Azure OpenAI and Azure AI Search. Throughout the process, you utilized OpenAI's GPT-4 model for generating intelligent responses based on user inputs, integrated Azure Blob Storage for dataset management, and leveraged Azure AI Search to create vectorized indexes for efficient querying.

Your engagement with Copilot Studio enabled you to seamlessly create and configure the bot, design interactive workflows, and integrate the knowledge base for accurate disease identification. Testing the bot with various user queries confirmed the accuracy and relevance of its responses, ensuring a reliable user experience.
  

