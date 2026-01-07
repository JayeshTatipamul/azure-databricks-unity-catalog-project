# azure-databricks-unity-catalog-project
This repository demonstrates a complete Unity Catalog setup and implementation in Databricks, focusing on centralized data governance, metadata management, and access control

# What is Unity Catalog?
Unity Catalog is a fine-grained data governance solution for data present in a Data Lake.

# Why Unity Catalog is Used Primarily?
Suppose, in a lakehouse project, there is a database in the Hive Metastore of a Databricks Workspace, and, in that database, there are Twenty Delta Tables present.
If the requirement is to provide a specific set of permissions, like Read Only, or, Write Only to a specific Group of Users on one, or, some of the particular Delta Tables, or, even at the Row Level, or, Column Level, which can contain a Personally Identifiable Information, i.e., PII, of that particular Delta Tables, then the Unity Catalog can simplify the solution to the requirement by implementing the Unified Data Access Control.
So, the primary reason for using the Unity Catalog is that it helps to simplify the security, as well as, the governance of the data by providing a Centralized Place, where it is possible to administer the access to the data, and, also audit the access to the data.

# In What Type of Databricks Workspace, the Unity Catalog can be Used?
The Unity Catalog is only available in the Premium pricing tier.
The Unity Catalog is available across multiple Clouds, i.e., on Azure, Amazon, and, Google Cloud Platform.

# Why Unity Catalog is Considered as Unified Catalog?
The Unity Catalog is considered as a Unified Catalog in the sense that it can store all the Databricks Workspace Objects, like - data, Machine Learning Models, Analytics Artifacts etc., in addition to the Metadata for each of the Databricks Workspace Objects.
Whatever is stored inside the Unity Catalog, becomes an Object.
Once an artifact that is stored inside the Unity Catalog becomes an Object, it is possible to provide the selective access to that particular Object.
The Unity Catalog is also considered as a Unified Catalog because, it is possible to blend in the data from other Catalogs, such as existing Hive Metastores into the Unity Catalog.

# What is the Data Lineage Feature in Unity Catalog?
Suppose, in a lakehouse project, a particular Column of a target Delta Table is derived from multiple Columns of three other Delta Tables by using some transformation logic.
In such cases, using the Unity Catalog, it is possible to visualize the Data Lineage of that target Delta Table to get the end-to-end visibility into how the data flows in the lakehouse project from the source layer to the consumption layer.

# What is the Data Sharing Feature in Unity Catalog?
Suppose, in a lakehouse project, there are twenty Delta Tables in a database.
If the requirement is to share the data of those twenty Delta Tables across the different platforms, or, the different Clouds, it can be done so, by using the Data Sharing feature of the Unity Catalog.
Data Sharing is an protocol, that is developed by Databricks for secure data sharing with other organizations, or, with other teams within the organization, regardless of which computing platform the other teams use.

# What is a Hive Metastore?
In order to manage the structure of the data in a Data Lake, it is possible to register, and, share the data as Tables in a Hive Metastore.

A Hive Metastore is a database that holds the Metadata about the data, such as -
The schema of the created Tables
The paths of the underlying data in the Data Lake of the created Tables
The format, like - parquet or delta, in which the underlying data of the created Tables is stored in the Data Lake etc.
Can Hive Metastore of One Databricks Workspace be Shared with Another Databricks Workspace?
Every Databricks Workspace in Azure Databricks comes with a managed built-in Metastore.

In a lakehouse project, there will be multiple Databricks Workspaces for different environments, like - development, qa, uat etc., and, the same set of Tables need to be registered in each of those Databricks Workspaces.

The Table that is created in a particular Databricks Workspace, can not be used in another Databricks Workspace, because each Databricks Workspace has a separate Hive Metastore that can be accessible only from within that particular Databricks Workspace, and, not from other Databricks Workspaces.

