[App type, contact type, and customer leads - Business Central | Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/readiness/readiness-checklist-e-industries-categories-apptype)

# Application Type

• **connect app** - establish point-to-point connection between Business Central and a 3rd party solution or service

[Build Connect apps](https://aka.ms/BusinessCentralConnectApps/)

[Get started developing Connect apps for Dynamics 365 Business Central - Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)

[API (v2.0) for Dynamics 365 Business Central - Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/api-reference/v2.0/)

[Endpoints for the APIs for Microsoft Dynamics NAV and Microsoft Dynamics 365 Business Central - Dynamics NAV](https://learn.microsoft.com/en-us/previous-versions/dynamicsnav-2018-developer/endpoints-apis-for-dynamics)
	
• **add-on app** - extends the experience and the existing functionality of Business Central. 

[Build Add-on apps](https://aka.ms/BusinessCentralAddonApps)
	
• **library app** - contains common code that other apps depend on. If you are going to have multiple AppSource apps that all share common code, such as licensing, registration, and so on, you can put that common code into a library app, and have the AppSource apps depend on the library app.

• **dependency app** - is not much different from a library app. A dependency app does have its own offer on AppSource. For example, you might have AppSource App A that serves a purpose on its own and is listed on AppSource. You then also have App B as its own offer on AppSource, but it does depend on code within App A, and needs App A to be installed before it can be installed. 

• **localization app** -  

[Build Localization apps](https://aka.ms/BusinessCentralLocalizationApps/)

# Links

<https://learn.microsoft.com/en-us/training/modules/application-types/3-library-dependency-applications> 
