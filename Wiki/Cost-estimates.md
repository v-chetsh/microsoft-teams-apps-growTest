

# Cost estimates

  ## Assumptions

The estimate below assumes:
-   Tenant has 1 team containing 100 users.

## SKU recommendations
The recommended SKU for a production environment is:

 - App Service: Standard (S1)
 - Azure Search: Basic
    - The Azure Search service cannot be upgraded once it is provisioned, so select a tier that will meet your anticipated needs.

## [](/wiki/Cost-estimate#estimated-load)Estimated load

**Data storage**: up to 1 GB usage of azure table storage.

**Table data operations (monthly)**:
  - User adds/updates/deletes/joins/close 10 projects per day
  - Total write calls  = 100 users * 10 projects * 30 days = 30,000
- User views 20 projects per day
- Total read calls = 100 users * 20 projects * 30 days = 60,000 

  - Azure Search service reads data for indexing
    -   For instantly reflecting data in Azure Search service, indexer is triggered manually whenever change happens to database
   
- Total storage calls = 30,000 + 60,000 = 90,000

## Estimated cost
**IMPORTANT:**  This is only an estimate, based on the assumptions above. Your actual costs may vary.

Prices were taken from the  [Pricing](https://azure.microsoft.com/en-us/pricing/)  on 30 June 2020, for the West US 2 region.

Use the  [Azure Pricing Calculator](https://azure.com/e/b81550f036734816ab56e59beac9515a)  to model different service tiers and usage patterns.

|**Resource**|**Tier**|**Load**|**Monthly price**|
|--------------------------|-----------------|-------------------------|--------------------------------------
|Bot Channels Registration|F0|N/A|Free|
|App Service Plan|S1 |744 hours|$74.40|
| App Service (Messaging Extension)| -|  |(charged to App Service Plan)|
| Azure Search|B||$75.14|
|Application Insights (Bot)|||(free up to 5 GB)|
| Storage account (Table)| Standard_LRS|< 1GB data & 182,004 operations| $0.05 + $0.01 = $0.06 |
|Total|||**$149.6**|