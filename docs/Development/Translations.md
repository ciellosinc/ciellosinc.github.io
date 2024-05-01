- [Links](#links)
  - [Working with translation files - Business Central | Microsoft Learn](#working-with-translation-files---business-central--microsoft-learn)
  - [Translations Overview - Business Central | Microsoft Learn](#translations-overview---business-central--microsoft-learn)
- [How to work with translation files using Dynamics 365 Translation Service](#how-to-work-with-translation-files-using-dynamics-365-translation-service)
- [Dynamics 365 Translation Service](#dynamics-365-translation-service)
  - [**Azure DevOps Extension**](#azure-devops-extension)
  - [**Visual Studio Code extension**](#visual-studio-code-extension)
- [Multilingual App Toolkit Editor](#multilingual-app-toolkit-editor)
- [Azure Translator](#azure-translator)
  - [Pricing](#pricing)
  - [How to use Azure Translator in Multilingual App Toolkit](#how-to-use-azure-translator-in-multilingual-app-toolkit)
- [POedit](#poedit)
  - [Links](#links-1)
  - [How to work](#how-to-work)
- [Other providers](#other-providers)
- [Tips \& Tricks](#tips--tricks)


# Links 


## [Working with translation files - Business Central | Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-work-with-translation-files)

In this article
- Generating the XLIFF file
- Label syntax
- The XLIFF file
- **Translating other extensions**

## [Translations Overview - Business Central | Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-translations-overview)

In this article
- The life of a caption
- Translations in the same layer
- **Translations in different layers**
- Picking the language to display


# How to work with translation files using Dynamics 365 Translation Service 


1. Generate the XLIFF file - [Generating the XLIFF file in Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-work-with-translation-files#generating-the-xliff-file)
2. In **Dynamics 365 Translation Service** 

   2.1. [Create a translation request](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/use-translation-service#create-a-translation-request)
   
   2.2. [Upload files](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/use-translation-service#upload-files)

3. Review and edit the translations in the **Multilingual App Toolkit Editor** - [Use the Multilingual App Toolkit](https://learn.microsoft.com/en-us/windows/apps/design/globalizing/use-mat)

# Dynamics 365 Translation Service


Use the [Dynamics 365 Translation Service](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/translation-service-overview) to get translations for your target languages. 

For more information, see [Translate user interface files](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/use-translation-service).   

---

> Training - [Translate Dynamics 365 apps and documentation with Dynamics 365 Translation Service - Training | Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/dynamics-translation-service/)
>
> Translation service** - [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index)

## **Azure DevOps Extension** 

> Installation - [Dynamics 365 Translation Service Azure DevOps extension](https://marketplace.visualstudio.com/items?itemName=dts-publisher.dts-vsc)

> Guidance - [Dynamics 365 Translation Service Azure DevOps extension (Public Preview)](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/dts-devops-extension)

## **Visual Studio Code extension**

> Installation - [Dynamics 365 Translation Service Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=dts-publisher.dts-vsc)

> Visual Studio Code Extension - [Dynamics 365 Translation Service (Preview) - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=dts-publisher.dts-vsc)

> Guidance - [Dynamics 365 Translation Service Visual Studio Code extension (Public Preview)](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/dts-vscode-doc)

---

![image.png](./.attachments/.Translations/image-1e31cf12-efb5-4a85-8c90-e3a9352c96c0.png  =700x500)  

![image.png](./.attachments/.Translations/image-3c35cd39-5f35-4ff8-b3da-5c634a6d5aa7.png) 

![image.png](./.attachments/.Translations/image-f2df46a6-bf05-408a-aaf8-49e10a53f458.png  =400x900)

![image.png](./.attachments/.Translations/image-5aaa06c9-32e5-4a2d-a091-115a92bdd1dc.png =489x517)


# Multilingual App Toolkit Editor

Installation -  [Multilingual App Toolkit Editor, Use the Multilingual App Toolkit - Windows apps | Microsoft Learn](https://learn.microsoft.com/en-us/windows/apps/design/globalizing/use-mat)

![image.png](./.attachments/.Translations/image-1d5736c9-e904-4586-83f0-0a25df8495dc.png)


# Azure Translator

[Azure AI Translator](https://azure.microsoft.com/en-us/products/ai-services/ai-translator)

[Azure AI Translator documentation](https://learn.microsoft.com/en-us/azure/ai-services/translator/?WT.mc_id=Portal-Microsoft_Azure_ProjectOxford)

[Text Translation REST API](https://learn.microsoft.com/en-us/azure/ai-services/translator/reference/rest-api-guide?WT.mc_id=Portal-Microsoft_Azure_ProjectOxford)

[Github](https://github.com/MicrosoftTranslator)

![image.png](./.attachments/.Translations/image-b62ddb7a-1bd1-414b-a5a8-d2083979744f.png)

Sample Code
```csharp
using System.Text;
using Newtonsoft.Json;

class Program
{
    private static readonly string key = "<your-translator-key>";
    private static readonly string endpoint = "https://api.cognitive.microsofttranslator.com";

    // location, also known as region.
    // required if you're using a multi-service or regional (not global) resource. It can be found in the Azure portal on the Keys and Endpoint page.
    private static readonly string location = "<YOUR-RESOURCE-LOCATION>";

    static async Task Main(string[] args)
    {
        // Input and output languages are defined as parameters.
        string route = "/translate?api-version=3.0&from=en&to=fr&to=zu";
        string textToTranslate = "I would really like to drive your car around the block a few times!";
        object[] body = new object[] { new { Text = textToTranslate } };
        var requestBody = JsonConvert.SerializeObject(body);

        using (var client = new HttpClient())
        using (var request = new HttpRequestMessage())
        {
            // Build the request.
            request.Method = HttpMethod.Post;
            request.RequestUri = new Uri(endpoint + route);
            request.Content = new StringContent(requestBody, Encoding.UTF8 "application/json");
            request.Headers.Add("Ocp-Apim-Subscription-Key", key);
            // location required if you're using a multi-service or regional (not global) resource.
            request.Headers.Add("Ocp-Apim-Subscription-Region", location);

            // Send the request and get response.
            HttpResponseMessage response = await client.SendAsync(request).ConfigureAwait(false);
            // Read response as a string.
            string result = await response.Content.ReadAsStringAsync();
            Console.WriteLine(result);
        }
    }
}

```

## Pricing

![image.png](./.attachments/.Translations/image-63817a75-e137-4c80-97bc-f7b647cb6f68.png)

## How to use Azure Translator in Multilingual App Toolkit 

[Use Azure Translator Text to automate translation - Training | Microsoft Learn](https://learn.microsoft.com/en-us/training/modules/manage-multilanguage-development/3-automate)

![image.png](./.attachments/.Translations/image-7a396df8-b96b-431e-a8fe-355d081baa97.png)

![image.png](./.attachments/.Translations/image-8c4901be-715b-40ad-b198-62a04ee9d69d.png)


# POedit


## Links

[Poedit Translation Editor — Poedit](https://poedit.net/)

## How to work

1. Install Poedit from [Poedit Translation Editor — Poedit](https://poedit.net/)
2. Configure Poedit in File->Poedit Preference

![image.png](./.attachments/.Translations/image-51512620-bf45-4111-b77e-03e2868c3df9.png)

3. Open .xlf file generated in Visual Studio Code
It appears warning to change target language. Click **Fix language**.

![image.png](./.attachments/.Translations/image-7a80ba9e-d69f-44c4-9eb9-11a155ab5e0c.png)

4. Click **Pre-Translation**

![image.png](./.attachments/.Translations/image-ad67dfb9-f400-4bf0-a448-c7fcda48ef43.png)

# Other providers


These third party providers offer localization services, and may be able to assist you.

[Elanex](https://www.strakertranslations.com/)

[Keywords Studios](https://www.keywordsstudios.com/)

[Lionbridge](https://www.lionbridge.com/)

[Moravia](https://www.rws.com/what-we-do/rws-moravia/)

[SDL](https://www.rws.com/)

[Welocalize](https://www.welocalize.com/)

--- 
 **Note**

 The list above is provided for informational purposes only and is not an endorsement. Microsoft does not make any representation or warranty regarding these vendors or their services, and under no circumstances will Microsoft have any liability for your use of such vendors or services. Any questions, complaints, or claims regarding such vendors or their services must be directed to the appropriate vendor.

---

# Tips & Tricks


**Special symbols**
Instead of symbol & use &amp