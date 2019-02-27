# AZURE STORAGE
Azure Storage, a component of Azure, is a Microsoft-managed service providing cloud storage that is highly available, secure, durable, scalable, and redundant. Azure Storage includes Azure Blobs (objects), Azure Data Lake Storage Gen2, Azure Files, Azure Queues, and Azure Tables.  A storage account needs to be created to use Azure Storage.  Multiple Storage Accounts can be created in an Azure Subscription.

**More on types of storage accounts:**
- **Blobs Storage:** Binary Large Objects; any type of file or binary data and for storing unstructured data.
E.g., Documents, images, videos. Log files, VM Disks.
- **Table Storage:** Tables to store data; they have no schema.  Developers can use table storage to develop based on fast changing requirements.
- **Queue Storage:** When distributed applications need to communicate asynchronously, this is one mechanism.
- **File Storage:**  It's similar to file share.  It can be mapped using a network drive.

## CREATING A STORAGE ACCOUNT:

> Home page of Azure Portal > Storage accounts > Add (Create Storage Account)

Fill the following required fields:

- Project details:
  - Subscription
  - Resource group
    
    (A resource group is a  logical container that holds related resources for an Azure solution.)

- Instance details:
  - Storage Account Name
   
   (The name must be unique across all existing storage account names in Azure.  It must have 3 to 24 characters and can contain only lowercase letters and numbers.) ure. It must be 3 to 24 characters long, a
  - Location
  - Performance: There are two available options-
    a. Standard: backed by magnetic drives and provide the lowest cost per GB; best for bulk storage or where data is accessed infrequently.
    b. Premium: Backed by solid state drives and offer consistent, low-latency performance. Can only be used with Azure virtual machine disks.  

This setting can not be changed after the storage account is created.
  - Acount kind:  Three types are available
    a. General-purpose v2 accounts: Basic storage account type for blobs, files, queues, and tables.
       Recommended for most scenarios using Azure Storage.
    b. General-purpose v1 accounts: Legacy account type for blobs, files, queues, and tables. Use general purpose v2 accounts instead when possible.
    c. Blob storage accounts: Blob-only storage accounts. Use general-purpose v2 accounts instead when possible.
  - Replication: Replication options for a storage account include:
    a. Locally-redundant storage(LRS): A simple, low-cost replication strategy. Data is replicated within a single storage scale unit.
    b. Zone-redundant storage (ZRS): Replication for high availability and durability. Data is replicated synchronously across three availability zones.
    c. Geo-redundant storage (GRS): Cross-regional replication to protect against region-wide unavailability.
    d. Read-access geo-redundant storage (RA_GRS): Cross-regional replication with read access to the replica.
  - Access tier:  There are two available access tier options-
    a. Hot Access tier:  suitable for frequently accessed data.
    b. Cool Access tier:  suitable for infrequently accessed data.

The Archive access tier can be set only at the blob level and not for the entire storage account.

Select Review + Create to review the storage account settings and create the account.

## CREATING A BLOB:
Blob is a massively scalable storage object for unstructured data.  It can scale up or down based on the need, making it easily manageable and cost effective.  

- To create a blob storage, choose the storage account in which the files need to be stored in.

- Under 'Services', select 'Blobs'.

- Select 'Container' to create a container.  Give a name to the container and set the appropriate public access level.

- Click 'OK' to create the container.

- From the list of containers available, click on the one in which the files need to be saved.

- Click on 'Upload'  and browse to upload files to the container.


# VIRTUAL MACHINE

## CREATING A VIRTUAL MACHINE:

Go to 'Create Virtual Machine'.  Fill the following required fields

- Basic:
  - Project details (Subscription and Resource Group)
  - Instance details (Virtual Machine Name, Region, Availability options, Image, Size)
  - Create Administrative account (Select Password in Authentication type, give username and create password)
  - Public inbound ports

Click Next: Disks >

-  Disk options:
  - OS disk type (Premium SSD, Standard SSD, Standard HDD)
  - Data disks (default option)

Click Next: Networking >

- Networking:
  - Network interface:  It will be created on its own.
  - Configure Virtual networks (Virtual network, subnet, public IP,  NIC network security group, Public inbound ports, Accelerated networking), use default options.

Click Next: Management >

- Management:
  - Monitoring ( Boot diagnostics , OS guest diagnostics, Diagnosticss storage account )
  - Identity (System assigned managed identity)
  - Auto-shutdown ( Enable auto- shutdown)
  - Backup ( Enable backup )

Click Next: Guest config >

- Guest config
  - Extensions
  - Cloud init

Click Next: Tags >

- Tags ( enter Name, Value and Resource)

Click Review + Create


## CONNECTING THE VIRTUAL MACHINE TO THE SYSTEM:

- Select the virtual machine.

- Click 'connect'.

- Select RDP (for Windows) or SSH (for Linux)

-  Click on 'Downlaod RDP file'

- Click 'connect on remote desktop connection'.

- Enter your credentials.

It will get connected.


