#Microsoft CDX trial tenant
{:toc}

Microsoft Customer Digital Experiences (CDX) are interactive digital experiences that help partners show customers why Microsoft is the right choice and how they can integrate and manage Microsoft cloud products. Please find more details here: https://learn.microsoft.com/en-us/partner-center/mpn-demos.

### How to get a Microsoft CDX Trial tenant
To access Customer Digital Experiences, use the following steps:

1. Sign in at https://cdx.transform.microsoft.com/.
2. When prompted to create a profile, select Partner for both Segment and Role.
3. When you're signed in, select My Environments, where you can create a new tenant.

![image.png](./.attachments/image-b1ce267a-41f9-4916-80df-3aae7a2e932b.png)
![image.png](./.attachments/image-442ac724-c609-472a-ba40-7205cfd5bee3.png)
![image.png](./.attachments/image-67352287-8273-4a56-b192-21ef25016661.png)

### How to get Dynamics 365 Sales trial environment
Please choose the Dynamics 365 Customer Engagement trial tenant, as shown in the picture above.

### How to get Dynamics 365 Business Central trial environments
1. Please choose any tenant, for example, the Dynamics 365 Customer Engagement trial tenant.
2. Then open [Admin Portal](https://admin.microsoft.com) using Admin user credentials for the trial tenant in the incognito/in-private browser.
3. To add Business Central trial to your tenant, please use the same browser as you did in the previous step and go to https://signup.microsoft.com/signup?sku=6a4a1628-9b9a-424d-bed5-4118f0ede3fd&ru=https%3A%2F%2Fbusinesscentral.dynamics.com%2F%3FredirectedFromSignup%3D1 and follow the onscreen steps.

### How to get Dynamics 365 Finance and Operations trial environment
1. Please choose any tenant, for example, the Dynamics 365 Customer Engagement trial tenant.
2. Then open [Admin Portal](https://admin.microsoft.com) using credentials for the trial tenant in the incognito/in-private browser.
3. To add Finance and Operations trial to your tenant, open Marketplace or Billing - Purchase services. Then, search Supply Chain Management or other D365 products and choose Dynamics 365 Supply Chain Management Trial. Other D365 products could be the following: Finance, Supply Chain Management, Project Operations, or Commerce
![image.png](./.attachments/image-89221b0b-a807-4f45-af5e-5b9d9c8d460d.png)
4. After the product is purchased, assign the license to an admin who can sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/) and perform the environment creation
5. Deploy the trial environment in the Power Platform admin center
   - Sign in to the Power Platform admin center after the trial license is assigned to your user account.
   - Select Environments in the navigation pane. The Environments page is displayed.
   - Select New to create a new environment. The New Environment pane is displayed.
   - Enter a name for the environment.
   - Select your region.
   - Change the environment type to "Trial (subscription-based)".
   - Select Next.
   - Select a Security group None.
   - Choose Enable Dynamics 365 apps.
   - In the drop-down menu, select the template that is related to the trial license you were given, such as Finance (Preview).
   - Select Save to start the deployment, which may take an hour to complete.
![image.png](./.attachments/image-7842c363-39b5-4c81-929b-bdad008592f5.png)

   Please find more details here: https://learn.microsoft.com/en-us/power-platform/admin/unified-experience/admin-trials.

6. Wait for about 2 hours.
![image.png](./.attachments/image-729d1c21-d5ed-4c62-ab95-b71507a92d38.png)

7. In addition to the PPAC (Power Platform admin center) environment, you can deploy a Tier2 environment through the [LCS](https://lcs.dynamics.com/). Please pass the Project Onboarding to enable the Tier2 Sandbox environment deployment slot on the main LCS page.
