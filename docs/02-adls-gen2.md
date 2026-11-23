
# Module 2 – Azure Data Lake Storage Gen2 (ADLS Gen2)

## 1. Project Context

ADLS Gen2 is the cloud storage layer for our Banking Data Engineering Platform.

It stores customer, account, transaction and fraud-event datasets.

## 2. What is ADLS Gen2?

Azure Data Lake Storage Gen2 is Microsoft's cloud storage solution for analytics workloads.

It combines Azure Blob Storage capabilities with a hierarchical namespace.

### Why do we use it?

- Store large volumes of data.
- Support analytical workloads.
- Organise data into directories.
- Integrate with Azure Data Factory.
- Support access control through RBAC and ACLs.

## 3. Important Keywords

| Keyword | Meaning |
|---|---|
| ADLS | Azure Data Lake Storage |
| HNS | Hierarchical Namespace |
| LRS | Locally Redundant Storage |
| RBAC | Role-Based Access Control |
| ACL | Access Control List |
| BLOB | Binary Large Object |
| RG | Resource Group |
| CONTAINER | Top-level storage container |

## 4. Storage Account Configuration

Our project configuration:

| Setting | Value |
|---|---|
| Resource Group | rg-retail-data-platform |
| Storage Account | stretaildata21112643 |
| Region | UK South |
| Performance | Standard |
| Redundancy | LRS |
| Account Kind | StorageV2 |
| Hierarchical Namespace | Enabled |

Note: The resource group name will be renamed or replaced with a banking-specific resource group later if we decide to separate the project resources.

## 5. What is Hierarchical Namespace?

HNS enables directory-based organisation inside the storage account.

Without HNS:
- Blob storage uses a flat namespace.
- Folder-like structures are represented using blob names and prefixes.

With HNS:
- Directories are first-class objects.
- Directory operations are more efficient.
- File and directory ACLs are supported.

HNS is a key capability of ADLS Gen2.

## 6. Bronze, Silver and Gold Architecture

### Bronze Layer
Purpose: Store original source data.

Examples:
- Customers
- Accounts
- Transactions
- Fraud events

### Silver Layer
Purpose: Store cleaned and validated data.

Operations:
- Remove duplicates.
- Handle NULL values.
- Validate data types.
- Standardise records.

### Gold Layer
Purpose: Store business-ready datasets.

Examples:
- Customer 360.
- Daily transactions.
- Account balances.
- Fraud analysis.

## 7. Container Structure

Our planned data lake structure:

banking-data/
|
|-- bronze/
|   |-- customers/
|   |-- accounts/
|   |-- transactions/
|   |-- fraud_events/
|
|-- silver/
|   |-- customers/
|   |-- accounts/
|   |-- transactions/
|
|-- gold/
    |-- customer_360/
    |-- daily_transactions/
    |-- account_balances/
    |-- fraud_analysis/

Implementation note:
We will create bronze, silver and gold as separate private containers initially. The directories shown above will be created inside those containers.

## 8. Practical Implementation Steps

### Storage Account Creation
1. Open Azure Portal.
2. Search for Storage Accounts.
3. Select Create.
4. Choose the project Resource Group.
5. Enter a globally unique storage account name.
6. Select UK South.
7. Select Standard performance.
8. Select LRS redundancy.
9. Enable Hierarchical Namespace.
10. Review and create.

### Existing Account Upgrade
Our account was initially created without HNS.

We used the Data Lake Gen2 migration option to:
1. Review account changes.
2. Validate the account.
3. Upgrade the account.
4. Verify successful completion.

Important: HNS upgrade is a one-way operation.

### Container Creation
1. Open the Storage Account.
2. Select Data Storage.
3. Open Containers.
4. Select Add Container.
5. Enter the container name.
6. Select Private access.
7. Create the container.

Repeat for bronze, silver and gold.

## 9. Security Concepts

### RBAC
Controls access to Azure resources through assigned roles.

### ACL
Controls access to directories and files within ADLS Gen2.

### Managed Identity
Allows Azure services such as Data Factory to authenticate without storing passwords.

We will implement these during the security and ADF integration phases.

## 10. Common Errors and Solutions

### Error 1: StorageAccountAlreadyTaken

Cause:
Storage account names must be globally unique.

Solution:
Choose another available name.

### Error 2: Hierarchical Namespace Disabled

Cause:
The account was created without HNS.

Solution:
Upgrade the existing account where supported, or create a new HNS-enabled account.

### Error 3: Authorization Permission Denied

Possible causes:
- Missing RBAC role.
- Missing directory ACL permissions.
- Incorrect managed identity configuration.

Solution:
Check the identity, role assignments and ACL permissions.

## 11. Interview Questions

Q1. What is ADLS Gen2?

Q2. What is Hierarchical Namespace?

Q3. What is the difference between Blob Storage and ADLS Gen2?

Q4. What is the difference between RBAC and ACL?

Q5. What is the Medallion Architecture?

Q6. Why do we use LRS?

Q7. How does Azure Data Factory connect to ADLS Gen2?

## 12. Quick Revision

ADLS Gen2 = Azure Blob Storage capabilities + Hierarchical Namespace.

HNS = Directory-based storage organisation.

Bronze = Raw data.

Silver = Clean data.

Gold = Business-ready data.

RBAC = Resource-level access control.

ACL = File and directory access control.

LRS = Locally redundant storage.

## 13. Project Status

- [x] Storage account created.
- [x] HNS upgrade completed.
- [ ] Bronze container created.
- [ ] Silver container created.
- [ ] Gold container created.
- [ ] Storage permissions configured.
- [ ] ADF integration completed.

## 14. Official Documentation

- https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction
- https://learn.microsoft.com/en-us/azure/storage/blobs/upgrade-to-data-lake-storage-gen2-how-to
- https://learn.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-access-control
