
### Overview
---
In this exercise you learn how to perform the following actions:
- Create an API Management (APIM) instance
- Import an API
- Configure the backend settings
- Test the API

   
### Key Aspects
---
- Azure Portal
- Azure Could Shell
- Azure CLI
- Azure api Management Services

### Environment
---
Microsoft Azure Portal
- Valid Subscription

### Actions
---
Prepare your environment
  
  - Sign in to the Azure portal

  - Open the Azure Cloud Shell using the Bash

Create the Azure using Azure CLI
  - Set environment variables
```
DEFAULT_CURRENTDATETIME="20240517183500"
DEFAULT_LOCATION="eastus2"
DEFAULT_RESOURCEGROUP_NAME="myresourcegroup${DEFAULT_CURRENTDATETIME}"
AZURE_APIMANAGEMENTSERVICE_NAME="apims${DEFAULT_CURRENTDATETIME}"
```

- Create a Resource Group
```
az group create --name ${DEFAULT_RESOURCEGROUP_NAME} --location ${DEFAULT_LOCATION}
```

- Create an Azure API Management Service
```
az apim create --name ${AZURE_APIMANAGEMENTSERVICE_NAME} --location ${DEFAULT_LOCATION} --publisher-email vinicius.cunha@farfetch.com --resource-group ${DEFAULT_RESOURCEGROUP_NAME} --publisher-name "AZ204-APIM-Exercise" --sku-name Consumption 
```

Import a backend API

  - Open the new instance of Azure API Management Services

  - Click on the “API” item in the left navigation pane

  - Click on the “OpenAPI” item

  - Click on the “Create” button

Configure the backend settings  
[ On the API form ]

  - Select Settings tab

  - Uncheck the Subscription required checkbox

  - Click on the “Save” button


Test the API  
[ On the API form ]

  - Select Test tab

  - Select “GetSpeakers” API

  - Click on the “Send” button

Clean up resources

  - Delete the Resource Groups and its content
```
az group delete --name ${DEFAULT_RESOURCEGROUP} --no-wait
```

### Media
---
![image](https://github.com/ViCunha/Lab-Azure-AzureAPIManagementServices-OnAzurePortal/assets/65992033/8e390b14-d2b0-42e1-ab4c-f33d958b68e9)

### References
---
- [Exercise - Create a backend API](https://learn.microsoft.com/en-us/training/modules/explore-api-management/8-exercise-import-api)
