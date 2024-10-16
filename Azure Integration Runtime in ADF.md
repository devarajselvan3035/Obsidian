```embed
title: "What are Integration Runtimes?"
image: "https://miro.medium.com/v2/resize:fit:1200/1*dwAzdScwyFi0RCm5J1vcew.jpeg"
description: "Azure services Data Factory, Purview, and Synapse Workspace all require the installation of a Self Hosted Integration Runtime in your…"
url: "https://medium.com/version-1/what-are-integration-runtimes-da7d24db1174"
```

### Integration Runtime in ADF
• The Integration Runtime (IR) is the compute infrastructure used by Azure Data Factory to provide the following data integration capabilities across different network environments:

=> **Data Flow**: Execute a Data Flow in managed Azure compute environment
=> **Data Movement**: Copy data across data stores in public network and private network
=> **Activity Dispatch**: Dispatch and monitor transformation activities running on a variety of compute services A
=> **SSIS Package Execution**: Execute SQL Server Integration Services (SSIS) packages in a managed Azure compute environment.
### Linked Services
* Target resource data store or compute services 
* Linked services are much like connection strings, which define the connection information needed for the service to connect to external resources. 
* Think of it this way: the dataset represents the structure of the data within the linked data stores, and the linked service defines the connection to the data source
### On-Premise vs Cloud
Simply put, the difference between on-premise vs cloud software is the location. On-premise software is installed and runs on a company's own hardware infrastructure, and is hosted locally, whereas cloud software is stored and managed on the provider's servers, and accessed through a web browser or other interface.
### Azure Integration runtime
Azure integration runtime is capable of performing below in public network.
=> Running Data-Flows
=> Running Copy Activities between Cloud data stores
=> Running Transform Activities
* Azure Integration Runtime supports connecting to data stores and compute services with public accessible endpoints.
* Azure integration runtime provides a fully managed, serverless compute in Azure
* Azure IR is elastically scaled up accordingly without you having to explicitly adjusting size of the Azure Integration Runtime.
![https://azurede.com/wp-content/uploads/2020/06/different-integration-runtimes.png?w=1024](https://azurede.com/wp-content/uploads/2020/06/different-integration-runtimes.png?w=1024)
### Data Flows in ADF
* Data flows feature in Azure data factory will allow you to develop graphical data transformation logic that can be executed as activities in ADF pipelines
* A Your Data flow will execute on your own Azure data bricks cluster for scaled out data processing using spark.
* ADF internally handles all the code translation, spark optimization and execution of transformation.
### Types of Azure Integration Runtime
Azure Data Factory (ADF) is a cloud-based data integration service that allows you to create, schedule, and manage data pipelines.

Azure Data Factory provides four different types of Integration Runtimes (IR) to connect to different types of data stores and perform various data integration activities:
1. **Azure Integration Runtime**: This runtime is used to connect to Azure data stores such as Azure Blob Storage, Azure Data Lake Storage, Azure SQL Database, and Azure Synapse Analytics.
2. **Self-Hosted Integration Runtime**: This runtime is installed on an on-premises machine or a virtual machine (VM) in a private network to provide secure connectivity between the on-premises data stores and the Azure Data Factory service.
3. **Azure-SSIS Integration Runtime**: This runtime is used to execute SQL Server Integration Services (SSIS) packages in the cloud. It provides a fully managed environment to run SSIS packages in Azure.
4. **Azure Function App Integration Runtime**: This runtime allows you to execute Azure Functions as part of an ADF pipeline. It provides serverless compute to run code in response to events or specific triggers,
### Self-Hosted Integration Runtime(IR)
The Self-Hosted IR is installed on a machine in your on-premises environment or other cloud provider and acts as a secure communication channel between the ADF service and the on-premises or other cloud data stores. It provides a gateway for ADF to access the data stores that are not accessible over the public internet, allowing you to create hybrid data integration scenarios
**Uses:**
* Enables you to move data between on-premises data stores and Azure data stores.
* Allows you to create hybrid data integration scenarios, such as data synchronization, data migration, and data transformation.
* Provides secure connectivity by establishing a private connection between the ADF service and the on-premises or other cloud data stores.
* Enables you to run custom activities and code on on-premises or other cloud machines to perform specific data integration tasks that ADF does not natively support.
* Allows you to connect to data stores that require specialized connectors or drivers that are not available in ADF natively.

