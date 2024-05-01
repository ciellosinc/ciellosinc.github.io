- [Environments - From a Usage perspective](#environments---from-a-usage-perspective)
  - [Development environments](#development-environments)
    - [Local Development Environment](#local-development-environment)
    - [Azure VM as a Development Environment](#azure-vm-as-a-development-environment)
    - [SaaS Sandbox environment (trial or permanent) ​](#saas-sandbox-environment-trial-or-permanent-)
  - [Test Environments](#test-environments)
  - [Production Environments](#production-environments)
- [Environments - From a technology perspective](#environments---from-a-technology-perspective)
  - [Local development box on the dev laptop with Docker container​](#local-development-box-on-the-dev-laptop-with-docker-container)
  - [Azure VM with docker container​](#azure-vm-with-docker-container)
  - [SaaS Sandbox environment (permanent)​](#saas-sandbox-environment-permanent)
  - [SaaS Sandbox environment (trial)​](#saas-sandbox-environment-trial)
- [Additional information](#additional-information)
  - [SaaS Environments](#saas-environments)
  - [Trial Environments](#trial-environments)
    - [Enable BC Trial mode for tenant](#enable-bc-trial-mode-for-tenant)
    - [Trials for other Microsoft Dynamics 365 products](#trials-for-other-microsoft-dynamics-365-products)
  - [Permanent solution for Microsoft Partners](#permanent-solution-for-microsoft-partners)


---
# Environments - From a Usage perspective
## Development environments
### Local Development Environment
It is possible to spin up a local dev environment as a Docker container on the developer's laptop.  
Please find more details here: https://github.com/ciellosinc/Ciellos-BC-git-flow-template/blob/main/Guides/LocalDevelopment.md  
In addition, you can always use official documentation from Microsoft: 
- https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-set-up-an-environment
- https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-running-container-development

### Azure VM as a Development Environment
Use the following link with ARM Template to deploy Azure VM with Business Central container: 
- https://aka.ms/getbc.
- https://github.com/microsoft/nav-arm-templates 

### SaaS Sandbox environment (trial or permanent) ​
Use SaaS environments for development.
- https://businesscentral.dynamics.com/common/admin ​
- SaaS vs Container https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-sandbox-overview 

## Test Environments
- Azure VM https://aka.ms/getbc ​
- SaaS Sandbox environment (trial or permanent)​
  - https://businesscentral.dynamics.com/common/admin 

## Production Environments
- SaaS Online environment
  - Business Central online version is used
  - Public Cloud
  - SaaS
  - Provided and managed by Microsoft
- Environment in Private Cloud
  - Business Central on-prem version is used
  - IaaS
  - Provided and managed by 3rd party cloud provider (not Microsoft)
- On-Prem Environment
  - Business Central on-prem version is used
  - Managed by the Customer or outsourced IT on the Customer's premises

<br/>
In short, the private cloud should use the BC on-prem version. 

---
# Environments - From a technology perspective
## Local development box on the dev laptop with Docker container​

## Azure VM with docker container​

## SaaS Sandbox environment (permanent)​
- Business Central user license​
- Dynamics 365 Business Central Additional Environment Add-on (license)​
- Microsoft Partner Sandbox licenses​
  - https://experience.dynamics.com/requestlicense ​
  - https://aka.ms/SandboxFAQ
  - https://aka.ms/sandboxhowto ​

## SaaS Sandbox environment (trial)​
- Enable BC trial on a customer tenant​
  - Enable trial https://learn.microsoft.com/en-us/dynamics365/business-central/trial-signup ​
  - Extend trial https://learn.microsoft.com/en-us/dynamics365/business-central/admin-extend-trial ​
- Create a trial tenant with Microsoft CDX. Enable BC trial on a trial tenant​.
  - https://cdx.transform.microsoft.com/​
- Create a Microsoft 365 developer sandbox tenant​
  - https://learn.microsoft.com/en-us/office/developer-program/microsoft-365-developer-program-get-started ​

---
# Additional information
## SaaS Environments
SaaS or Online Business Central environments available per tenant.  
When you purchase a BC license or enable trial mode, four environments are available to you:
- 1x Production
- 3x Sandbox

The admin portal is available by the following link: https://businesscentral.dynamics.com/common/admin.  
It is possible to purchase more Production environments with Sandboxes.  
And it is possible to purchase more Database storage.

---
## Trial Environments
If you don't want to use your tenant for trials, you have the following options: 
1. Set up a [Microsoft 365 developer trial tenant](https://learn.microsoft.com/en-us/office/developer-program/microsoft-365-developer-program-get-started) for 90 days.
2. If you are a Microsoft partner, you can use [Microsoft CDX](https://cdx.transform.microsoft.com/my-tenants/create-tenant)  
Each user may have:
   - Up to five 90-day trials tenants of Dataverse/CRM/BC/FSC
   - Up to one 1-year trial tenants

Please find more details about Microsoft CDX trial tenant here: https://dev.azure.com/ciellos-bc/main/_wiki/wikis/Internal%20Wiki/118/Microsoft-CDX-trial-tenant.

### Enable BC Trial mode for tenant
It is possible to organize a BC online trial version on any tenant, including your own tenant.  
Please use this link: https://go.microsoft.com/fwlink/?LinkId=2143349&clcid=0x409.   
This trial is for 30 days, but you should be able to extend it for another 30 days.  
Please find more details here: https://learn.microsoft.com/en-us/dynamics365/business-central/trial-signup.  

### Trials for other Microsoft Dynamics 365 products

It would be better to configure tenant for the United States. Please enable trials when you need to. Do not enable all of them at once – in 30 days, the trial will be finished.
- Power Pages trial for 30 days: https://learn.microsoft.com/en-us/power-pages/getting-started/trial-signup.
- Power Virtual Agents trial: https://learn.microsoft.com/en-us/power-virtual-agents/sign-up-individual
- Power Apps trial: https://learn.microsoft.com/en-us/power-apps/maker/signup-for-powerapps
- Other approaches and ways for Power Platform trial: https://learn.microsoft.com/en-us/power-platform/admin/trial-environments#multiple-ways-to-start-a-trial
- Dynamics 365 Sales trial: https://learn.microsoft.com/en-us/dynamics365/sales/sign-up-for-sales-trial
- Dynamics 365 Customer Service trial: https://learn.microsoft.com/en-us/dynamics365/customer-service/try-customer-service
- Business Central trial: https://learn.microsoft.com/en-us/dynamics365/business-central/trial-signup
- Microsoft 365 developer trial tenant for 90 days: https://learn.microsoft.com/en-us/office/developer-program/microsoft-365-developer-program-get-started 

---
## Permanent solution for Microsoft Partners
If you don't like temporary solutions or you are going to use this environment for development, you can purchase BC Sandbox from Microsoft with a special discount for Partners.
In short, you should fill in the following form [ISV Request License](https://experience.dynamics.com/requestlicense) and submit the request.
- **FSC**: The price is 650 USD/month for 25 users.
- **BC**: The price is 30 USD/month for 1 Sandbox for 5 users. ($6 * 5 users = $30)
- List of [all SKUs Dynamics 365 Partner Portal](https://dynamicspartners.transform.microsoft.com/login?returnUrl=%2Fdownload%2Fprotected%3Fassetname%3Dprotectedassets%252FPartner%2520Sandbox%2520Licenses%2520SKU%2520List.pdf%26download%3D1%26protected%3D1%26src%3Dhttps:%252F%252Fdynamicspartners.transform.microsoft.com%252Fisv-connect)
- Request form [ISV Request License](https://experience.dynamics.com/requestlicense)
- FAQ Dynamics 365 Partner Portal https://aka.ms/SandboxFAQ
- Overview Partner Sandbox Licenses – Overview https://aka.ms/sandboxoverview
- Guide Partner Sandbox Licenses – Partner Experience Guide https://aka.ms/sandboxhowto

![image.png](./.attachments/.Environments/image-97dd28ba-a7d7-4153-a66f-eb4e860296b1.png)



