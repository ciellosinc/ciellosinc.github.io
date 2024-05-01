- [Questionnaire](#questionnaire)
- [Table of services](#table-of-services)
  - [Documentation delivery](#documentation-delivery)
  - [Code delivery](#code-delivery)
  - [Application deployment/delivery to the Environment](#application-deploymentdelivery-to-the-environment)
  - [Automation (AL-Go with GitHub)](#automation-al-go-with-github)


[BC_Questionnaire.xlsx](./.attachments/.Questionnaire/BC_Questionnaire.xlsx)

[BC_Questionnaire.xlsx in Teams](https://ciellosinc.sharepoint.com/:x:/s/Ciellos_D365Technical/EcOWfSqIhWBHqLd3_Pg_qD8BTH6aQ5k5_EU_-M66PgTAfA?e=S0L51h)

> **NOTE**  
> The Excel file can be outdated. Please always use the text below.

# Questionnaire
| No. | Questions | Answer | Notes |
|-----|-----------|--------|-------|
| 1 | **General**
|   | What is the customer name?
|   | What version and localization of BC does the customer have?
|   | Is it cloud or on-prem?
|   | Is there any ISV solution? The customer should provide object range, PTE or AppSource. 
|   | Should we develop a new extension or in the existing one?
|   | Are there any other extensions used? 
|   | Are there any integrations built with any external solutions? 
|   | Do you have any development, deployment policies, or procedures that the team needs to follow? 
| 2 | **Source Code and Code Repository**
|   | Do you have a code repository in Azure DevOps or Github? If so, can you give us access to it?
|   | If the customer does not have a code repository, Ciellos can deploy it on their side following Ciellos best practices. The customer is to provide source code (packages, PTEs, etc.)
| 3 | **Task management**
|   | Do you have a Task management system (Azure DevOps or Jira) that we can use for task tracking? 
|   | If it doesn’t exist or it is not available, Ciellos to deploy it on their side following Ciellos' best practices 
|   | What will be the communication channel, e.g. Teams, emails, DevOps, Jira?
| 4 | **Development environment**
|   | Do you have your own development machines? If so, do you want Ciellos developers to work on your dev machines? 
|   | If not, Ciellos will use local BC docker containers or Microsoft CDX environments (Trial tenant with trial BC environments) 
| 5 | **Test environment**
|   | Do you have a Test environment deployed in your tenant? If so, can you give us access to it? 
|   | If not available, then Ciellos deploys it on their side. 
| 6 | **User Acceptance Test (UAT) environment**
|   | Do you have a UAT environment deployed in your tenant? If so, can you give us access to it?
|   | If not available, then Ciellos is not involved in the UAT stage 
| 7 | **Production environment**
|   | Who will publish and approve the changes to production, and in which schedule? 
| 8 | **Deployment process/App Source publication**
|   | How should the deployment look like? <br/>**Options:**
|   | A) Ciellos can work with the code in Azure DevOps or GitHub. Ciellos provides the code through access to the code repository. The customer deploys a new version of the extension without Ciellos' involvement. 
|   | B) Ciellos can provide the App file with the code to deploy it to the UAT or customer testing environment. The customer deploys a new version of the extension without Ciellos' involvement.
|   | C) Cielos can deploy changes to the client Test/UAT environment. Access to the environment is needed. 
|   | D) Ciellos can deploy changes to the client Test/UAT automatically as part of the CI/CD process.
|   | Are there any restrictions for the deployment time window?
|   | What will be the release schedule (e.g. feature-based, sprint-based, schedule)?

<br/><br/>

# Table of services
## Documentation delivery
| Service name| Enabled? |
|-------------|----------|
| Backlog, tasks, and issues
| Requirements
| Architecture Design
| Functional Design Documents
| Technical Design Documents
| Test results
| Integration Design

| Communication channel| Enabled? |
|----------------------|----------|
| Emails
| Stand-up meetings
| Teams

## Code delivery
| Service name | Enabled? |
|--------------|----------|
| GitHub
| Azure DevOps
| Code Review
| Test App
| Performance Toolkit (BCPT)

## Application deployment/delivery to the Environment
| Service name | Enabled? | Responsibility/Who host |
|--------------|----------|-------------------------|
| Dev box
| Test
| UAT
| PROD

## Automation (AL-Go with GitHub)
| Service name | Enabled? |
|--------------|----------|
| Code validation (CI pipeline)
| Next Minor and Next Major version Code validation (CI pipeline)
| Automatic code deployment to the environments (CI/CD pipeline)
| Execution of Test App
| Execution of Performance Toolkit (BCPT)
| Package publication to AppSource (code update)
| Dedicated Build Server to execute pipelines or free minutes

