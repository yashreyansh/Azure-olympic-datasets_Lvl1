# 2021-olympic-datasets

Plan:
To understand the flow from data factory -> gen2-> synapse analytics-> any BI tool

Flow would be like:
Data Source(local/github/etc) -> Ingestion to Data factory -> 

Step 1: Important to create a resource group prior to starting anything on which all modules would be working upon.
Step 2: Create Storage account & container gen2 (Hierarchical enabled) storage within that where the data would be stored.
Step 3: Create a dataFactory project , within that create a Pipeline where the data would be fetched(with source) and stored (sink) in the container created in step 2.
Step 4: Now when the raw data is fetched from source(in this case github to the storage container through Datafactory pipeline), do some transformation in Databricks. Open a databricks instance, use the attached jupyterfile script to make changes and write parquet file again in some other directory in Storage account.
Step 5: We need to fetch the file in Synapse analytics, Create a Lake Database -> create table from datalake , choose linked service etc and choose the folder within the ADLS gen2 storage. Repeat for al the tables you want. From here you can fetch from any other Bi tools and do analysis.





How to?
1. Create DataFactory Pipeline: create DF instance and launch it, author->create pipeline -> Move&transform -> copy-data -> add source and sink, thats it!

   note: Github raw data source woule be HTTP , ADLS1 would be sink
