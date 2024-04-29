{:toc}

# Code Repositories and Branches
| Item | Definition |
|:-----|:-----------|
| DevOps | Process of Development and Operations
| Azure DevOps | Web-based application to control Development and DevOps processes. It contains reach Development Project Management and a good enough code repository (git and TFVC)
| GitHub | Web-based application to control Development and DevOps processes. It has a strong code repository (git only) and simple Development Project Management
| Jira | Web-based application to control Development and DevOps processes. Contains Development Project Management but doesn't have any code repository
| git | The most popular version control of the code repository
| TFVC | Team Foundation Version Control. Microsoft version of the code repository

> [!NOTE]  
> It is recommended to use Azure DevOps for Development Project Management and GitHub for code repository with the [AL-Go template](https://github.com/microsoft/AL-Go).

# Project Roles
| Role | Description |
|:-----|:------------|
| SA | Solution Architect
| PM | Project Manager
| FC | Functional Consultant
| AS |Application Specialist 
| TA | Technical Architect 
| SE, DevOps | Systems Engineer / DevOps
| DEV | Developer  

#Tests *Not ready*
| Test        | Test App | Description |
|:------------|:-----------------|-------------|
| Manual test | No
| Code coverage | No*
| Unit test | No*
| Automated test | Yes 
| Component test | Yes
| Integration test | Yes*
| Regression test |

Please find more details here:
  - https://learn.microsoft.com/en-us/dynamics365/guidance/implementation-guide/testing-strategy-test-types
  - https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Customer%20Service/Testing/Strategy/Documentation

# Environments type
| Environment | Description |
|:------------|:------------|
| DEV | for development
| TEST | for testing
| QA | for testing
| UAT | User Acceptance Test
| FAT | Final Acceptance Test. Similar to UAT
| Sandbox | for Test or internal testing
| Demo | for Demonstration functionality. Typically used for a prospective customer.
| EIL | Early Integration Laboratory (rare)

# Cloud options
| Name | Description |
|:-----|:------------|
| SaaS | Software-as-a-Service. The application is available to you, for example, Business Central
| PaaS | Platform-as-a-Service. The platform where you may build an Application is available to you, for example, IIS Server
| IaaS | Infrastructure-as-a-Service. The Infrastructure where you can build a platform is available to you; for example, Network and Windows Virtual Machine

# Microsoft Dynamics 365 and Power Platform products
| Short names | Name | Old names | Description | Link
|:------------|:-----|:----------|:------------|:----------|
| **BC** | Business Central | NAV, Navision | ERP | https://learn.microsoft.com/en-us/dynamics365/business-central/
| **FSC**, FSCM, D365FO, F&O | Finance and Operations | AX, Axapta | ERP | https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/
| CE, CRM, Sales | Dynamics 365 Sales | CRM | CRM | https://learn.microsoft.com/en-us/dynamics365/sales/
| Customer Services | Dynamics 365 Customer Services | CRM with ISV solution | CRM for support services | https://learn.microsoft.com/en-us/dynamics365/customer-service/
| Dataverse | Dataverse | CRM Platform | Data Platform: UI+Database+esential services for CRM | https://learn.microsoft.com/en-us/power-apps/developer/data-platform/
| CI | Dynamics 365 Customer Insights | N/A | Not related to CRM. It is about statistical and demographic information about Contacts | https://learn.microsoft.com/en-us/dynamics365/customer-insights/
| Power Platform | Power Platform | N/A | Platform for almost any Power*, except Power BI and CI | https://learn.microsoft.com/en-us/power-platform/
| Power Pages | Power Pages | CRM Portal | Portal solution for Dataverse | https://learn.microsoft.com/en-us/power-pages/
| Power Virtual Agents | Microsoft Copilot Studio | N/A | Chat bot | https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio
| Power Apps | Power Apps | N/A | Canvas App and Model-driven app. For the last one, the Dataverse database is necessary | https://learn.microsoft.com/en-us/power-apps/
| Power BI | Power BI | N/A | Analytical Reports | https://learn.microsoft.com/en-us/power-bi/
