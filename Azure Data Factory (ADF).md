## Creating an Azure Data Factory Instance
### Azure Tenant
=> An Azure Tenant can be described as an exclusive instance of Azure Active Directory (AAD) that corresponds to an organization's Azure subscription. It primarily functions as a directory for all the applications, groups, and users utilized within the organization's Azure environment.
=> Your directory, commonly called a tenant, is an instance of Microsoft Entra ID,formerly known as Azure Active Directory (AAD). “Default Directory” is the default name of a new tenant.
![images](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRlEg8S3V5tS2_6jowzDd9OKDGxuzvmbHWsX2VfJPreVDqqONkG0KVnPcM&s=10)
### Microsoft Entra ID
Microsoft Entra ID (formerly known as Microsoft Azure Active Directory or Azure AD) is a cloud-based identity and access management (IAM) solution. It is a directory and identity management service that operates in the cloud and offers authentication and authorization services to various Microsoft services such as Microsoft 365, Dynamics 365, and Microsoft Azure.[1] Entra ID provides users with single sign-on experience, regardless of whether their applications are cloud-based or on-premises.
### Azure Resource Group
Instances of Azure services are referred to generally as 
resources. An instance of Azure Data Factory is an example of a resource. Resources belonging to a subscription are organized further into resource groups. A resource group is a logical container used to collect together related resources – for example, all the resources that belong to a data warehousing or analytics platform.
![image](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/media/overview/consistent-management-layer.png)
### Azure Repos
Azure Repos is **a set of version control tools that you can use to manage your code**. Whether your software project is large or small, using version control as soon as possible is a good idea. Version control systems are software that helps you track changes you make in your code over time.
### Link to a Git Repositor 
A data factory instance can be brought under source control by linking it to a cloudbased Git repository. While it is possible to undertake development work in ADF without linking your data factory to a Git repository, there are many disadvantages of doing so – without a linked repository, even saving work in progress is difficult. Before beginning work in your new ADF instance, you will link it to a Git repository
## Your first Pipeline
### Pipeline: 
A data integration workload unit in Azure Data Factory. A logical grouping of activities assembled to execute a particular data integration process.
### Activity: 
Performs a task inside a pipeline, for example, copying data from one place to another.
### Dataset: 
Contains metadata describing a specific set of data held in an external storage system. Pipeline activities use datasets to interact with external data.
### Linked service: 
Represents a connection to an external storage system or external compute resource.
### Integration runtime: 
• **Debug**: You can run a pipeline interactively in ADF Studio using “Debug” mode. This means that the pipeline definition present in the ADF Studio session is executed – it does not need to be published to the connected factory instance, or even saved. During a debugging run, a pipeline treats external resources in exactly the same way as in published pipeline runs.
• **Copy Data tool**: A wizard-style experience in ADF Studio that creates a pipeline to copy data from one place to another. I have presented it in this chapter as a quick way to start exploring the pipeline structure, but in practice, you are unlikely to use the tool very often.
### Azure Storage: 
Microsoft’s cloud-based managed storage platform. • Storage account: A storage account is created in order to use Azure Storage services.
• **Storage key**: Storage keys are tokens used to authorize access to a storage account. You can manage an account’s keys in the Azure portal.
• **Blob storage**: General-purpose file (blob) storage, one of the types of storage offered by Azure Storage. Other supported storage types (not described here) include file shares, queues, and tables.
• **Container**: Files in blob storage are stored in containers, subdivisions of a storage account’s blob storage. Blob storage is divided into containers at the root level only – they cannot be nested.
• **Storage browser**: A web-based app used to manage Azure Storage accounts, hosted in the Azure portal.
• **Azure Storage Explorer**: A free desktop app used to manage Azure Storage accounts.
• **Bandwidth**: A term used by Microsoft to describe the movement of data into and out of Azure data centers. Outbound data movements incur a fee, sometimes referred to as an egress charge.
## The Copy Activity
Data integration tasks can be divided into two groups: those of data movement and those of data transformation