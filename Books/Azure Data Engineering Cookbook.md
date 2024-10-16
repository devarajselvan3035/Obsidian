# <u>**Chapter 1: Creating and Managing Data in Azure Data Lake**</u>
Azure Data lake is highly scalable and durable object-based cloud storage solution from Microsoft.

Data Lake used as a data source and destination
**Source** => Structured and semi-structured data
**Destination** => Store the result of a data pipeline.

==Blobs = files==

How to provision, manage, upload data into data lake,
- Provisioning an azure storage account using Azure portal
- Provisioning an azure storage account using power-shell
- Create containers and uploading files to azure blob storage using power-shell
- Managing blobs in azure storage using power-shell
- configuring blob lifecycle management for blob objects using the azure portal

**Types of Storage services:**
1. Azure blob storage
2. Table
3. Queue
4. File Share
> [!note]
> Blob storage service stored data as ==key-value pairs==

**Fault-Tolerance**
- Recovery from data loss
- Involves active intervention for restore the system
- This may involve some downtime or permanent data loss
- How to achieve this...?
	- *Recovery Time Objective(RTO)*
		- The Maximum duration of acceptable downtime
		- Measured in the unit of time
	- *Recovery Point Objective(RPO)*
		- The maximum duration acceptance data loss
		- Measured in the unit of time
## 1.1 Create containers and uploading files to azure blob storage using power-shell
Create Storage container - **New-AzStorageContainer**
Upload files to the container - **Set-AzStorageBlobContent**

Azure Portal => Azure Subscription => Azure Storage account => Azure Blob Storage => Azure Container

- Copying blobs across in the same storage account or a different storage account - **Start-CopyAzureStorageBlob**
- Download a blob form azure to a local system - **Get-AzStorageBolbContent**
- delete blob - **Remove-AzStroageBlob**

## 1.2 Configuring blob lifecycle management for blob object using the Azure portal
**Types of Blob Access tier,**
1. Archive
2. Cool
3. Hot

<u>**Blob Lifecycle management rule**</u>
helps in managing storage costs by modifying the access tier of blob as per the specified rule.
![](https://i1.wp.com/dailydotnettips.com/wp-content/uploads/2018/07/update-Access-Tier-in-Azure-Storage-Blob-Level-Tier.png?resize=665%2C620&ssl=1)

---


# <u>**Chapter 2: Securing and Monitoring Data in Azure Data Lake**</u>
To allow access form an Ip and an Ips range, click on the the selected network option on the storage account on the firewall and virtual network page.

## 2.1 Configuring virtual network for an azure data lake account using the azure portal

**Public** - Access using the azure portal
**Private** - Access to selected Virtual Networks

<u>**Azure Virtual Network**</u>
A service that provides the fundamental building block for your private network in azure.

> [!note]
> Virtual network and storage account should be in same location

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSww8TIbU9OVzAvKesqRyHReQfVuLfJYoJlEw)


## 2.2 Create Private Links for and azure Data lake account

Azure portal => Storage account => Networking => Private Endpoint tab
=> + Private endpoint button

<u>**Domain Name System(DNS):**</u>
A DNS zone is used to host the DNS records for a particular domain.

We have create a private link to a storage account and ensured that traffic goes through the microsoft backbone network(and not the public network), as we will be accessing the storage account via a private endpoint.

> [!note]
> Your machine is not part of the VM

Get Private link URL => **nslookup**
## 2.3 Configuring Encryption using azure key vault for azure data lake
<u>**Azure Key Vault**</u>
- Box for storin key, password, secrets, certificates
- Azure key vault is a cloud services that provides a secure store for secrets you can securely store keys, password, certification
![](https://learn.microsoft.com/en-us/azure/key-vault/media/azure-key-vault.png)

Azure portal => create a resource => key vault => click create 
=> click Review + create
*after create*,
Storage account | Encryption => Encryption(left) => Encryption tab
=> select key vault and key

All data lake operation (read, write, and metadata) will use the key from key vault to encrypt and decrypt the data in data lake

## 2.4 Accessing Blob storage accounts using managed identities
<u>**Managed Identities**</u>
Managed identities are password less service accounts used by azure service such as Data factory and Azure VM to access other azure services such as Blob Storage.

Storage Account | Access Control(IAM) => Click + add 
=> Select Add role assignment
=> Select Managed identity access to => Select Member
=> Select Data Factory
*inside the Data factory,*
Open Azure Data Factory Studio => Manage => Linked services => + New
=> Select storage account => Select Managed identity 
=> Click test connection

A managed identity for the data factory was automatically created when the data factory account was created

## 2.5 Creating an alert to monitor an azure storage account
> [!note]
> To create alert, we need to define trigger condition

Azure portal => Storage Account => Search Alert => Click + New alert rule
=> Resource section select storage account(*Can add multiple storage account*)

At first, we need to define the alert condition (a trigger or signal). An alert condition defines the metrics and threshold that when breached, trigger the alert. We can define more than one condition on multiple metrics for one alert we then need to define the action to be performed when the alert condition is reached. we can define more than one action for alert

## 2.6 Securing an azure storage account with SAS using power-shell
<u>**Shared Access Signature(SAS):**</u>
- Using SAS we can specify different permission to users or application or different blobs, based on the requirement.
- For Example, If an application needs to read on file/blob from a container instead of providing access to all the files in the container, we can use an SAS to provide read access on the required blob.

Generate a shared access token for blob => **New-AzStorageBlobSASToken**
Create access policy => **New-AzStorgeContainerStoredAccessPolicy**

# <u>**Chapter 3: Building data ingestion pipelines using Azure Data Factory**</u>

Azure Data Factory, you can build pipeline that are capable of reading data from multiple sources, transforming the data and loading the data into data storages to be consumed by reporting application.

## 3.1 Provisioning Azure Data Factory
Data Factory Comprised key components,
**Linked Service** : A component that maintains the connection credentials to data source. *Ex: connection to a SQL database/Text file*
**Dataset**:The data that's obtained after connecting to the data source using linked service.
**Activity**: A task that will process the dataset. *Ex: Copy Activity*
**Data Flow**: There are specific tasks that perform data transformation on datasets.
**Integration Runtime**: This is the azure data factory engine that works behind the scenes and provides the compute and resources to run the activities or tasks.
**Pipeline**: A single entity that combines all the aforementioned components to connect, process, transform and ingest the data to the destination. A single pipeline may contain multiple linked services, datasets, activities and data flows

<u>**Git Configuration**</u>:
Git configuration allows you to configure integration with azure Dev-ops or Github.

## 3.2 Copying files to a database from a data-lake using a control flow and copy activity
<u>**Linked Services:**</u>
Linked services are used to connect other resources with ADF Linked services are like connection string for resources to connect

<u>**Datasets:**</u>
Datasets are simply points or references the data, which you want to use in your activities as input or output.
