[[_TOC_]]

# Links


[Breaking Changes](https://github.com/microsoft/ALAppExtensions/blob/main/BREAKINGCHANGES.md) - This document contains a list of the breaking changes that we know were introduced since 2019 release wave 2.

[APIQueryGenerator](https://github.com/microsoft/BCTech/tree/master/samples/APIQueryGenerator) 

This sample code consists of two commandline programs
1. **PayloadGenerator** takes arguments to define general metadata for the API queries you want to generate as well as input files in the simplest format possible (csv) for the AL tables and fields that you would like to include in your API queries.
1. **APIQueryGenerator**  - takes arguments to define general metadata for the API queries you want to generate as well as input files in the simplest format possible (csv) for the AL tables and fields that you would like to include in your API queries.

[github/BCTech/CloudMigration](https://github.com/microsoft/BCTech/tree/master/samples/CloudMigration) - 
PowerShell scripts and application to help with cloud migration  

[Cloud Migration API Overview](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/cloudmigrationapi/cloud-migration-api-overview)

[Analyzing cloud migration trace telemetry](https://learn.microsoft.com/en-gb/dynamics365/business-central/dev-itpro/administration/telemetry-cloud-migration-trace)

[[github/BCTech//environment-app-pbix](https://github.com/microsoft/BCTech/tree/master/samples/AppInsights/PowerBI/Reports/AppSource) - 
Power BI reports

---
[Youtube - Introduction to Business Central cloud migration (2023)](https://youtu.be/Gwgpj1U1wxI?si=_Q9VzoOjE13p4Aw4)

# Tools

[01. BC_Upgrade_Portfolio.xlsx](https://ciellosinc.sharepoint.com/:x:/s/BC-Upgrades/EWpv8L5enjFMlAtUaXAIOZwB2uZQI3PlAa9qhpeP7bLm2Q?e=fzS7D5) - Customer Portfolio (including Questionnaire) to collect the necessary information

[02. Upgrade_Tool.xlsx](https://ciellosinc.sharepoint.com/:x:/r/sites/BC-Upgrades/Shared%20Documents/General/_Templates/02.%20Upgrade_Tool.xlsx?d=w63795f3962b44b67ad97597637bead7f&csf=1&web=1&e=X4U3wd) - This file is for
 - Help in creating an estimate - determine which and how many objects have changed
   - Modified Microsoft objects
   - Custom objects (range 50000 - 99999)
   - Modified ISV Product objects
 - Mapping between installed ISV Solutions and applications in the latest version
 - Mapping between existing custom tables (fileds) and new tables (fields). 
   This file contains information what tables (fields) we migrate and the new name (with affix and limit of 30 symbols). 

[03. Upgrade_Estimate.xlsx](https://ciellosinc.sharepoint.com/:x:/s/BC-Upgrades/EQndCCfzHNFLuc05Y-IBRAQBfCBqXSvnoIC4yZ5KcbnDHQ?e=7fGReZ) - special form of Estimate where added column to identify what steps should be included (excluded), for example **Migration to Azure SQL**.  

[04. Upgrade_Run.xlsx](https://ciellosinc.sharepoint.com/:x:/s/BC-Upgrades/EfS_Nnh2pj1Dn2c8kfNI3BIBQ0LyhG4tNgFtXM0sYXJgRg?e=pbaz8L) - the file contains the steps for upgrade from different versions

---


[github\bc-upgrade](https://github.com/ciellosinc/bc-upgrade) - this is link to project in Github where tools, utilities, application will be kept. 