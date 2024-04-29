# Object ranges in Business Central

# Links
[Object ranges in Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-object-ranges)

When you develop an app for Business Central online, you must request an object range in terms of licensing. Development for Business Central is done using Visual Studio Code with the AL Language extension for Microsoft Dynamics 365 Business Central.

There are currently two available ranges that you can request. Both have some characteristics to keep in mind:

- *RSP Object Range* (ID range 1,000,000-69,999,999)

    This object range is tied to [the RSP Program](https://businesscenter.mbs.microsoft.com/#contentdetail/RegisterSolutionProgram) details.

.alert.is-primary {
    background-color: var(--theme-primary-background);
    border: 1px solid var(--theme-primary-background-glow-high-contrast);
}
<div class="alert is-primary" background-color: Blue;">
<p class="alert-title" > <b> Important </b></p>
</div>


<div class="alert is-primary">
<p class="alert-title"><span style="font-weight:bold;background-color:LightBlue;"> Important </span></p>
<p>We currently advise new publishers to <em>not</em> request an RSP object range</p>
</div>


<div class="alert is-primary">
<p class="alert-title"><span class="docon docon-status-info-outline" aria-hidden="true"></span> Important</p>
<p>We currently advise new publishers to <em>not</em> request an RSP object range</p>
</div>


    > IMPORTANT
    >> We currently advise new publishers to *not* request an RSP object range

- *App Object Range* (ID range 70,000,000-74,999,999)

    This object range was originally designed just for apps in the Microsoft commercial marketplace to be used in [!INCLUDE [prod_short](prod_short.md)] online.

    > [!IMPORTANT]
    > We currently advise new publishers to request an app object range.

Currently, you can implement apps developed in both the *RSP range* and the *app object range* in [!INCLUDE [prod_short](prod_short.md)] online and on-premises, as well as partner-hosted.

For more information, see [Requesting an object range](readiness/get-started.md#requesting-an-object-range).  

The following sections describe the different object ranges that you can find in the base application and extensions.

## 0-49,999

This range is assigned to [!INCLUDE[prod_short](includes/prod_short.md)] base app functionality and must not be used in extensions or customizations.

## 50,000-99,999

This range is for customizations, and for test purposes. For [!INCLUDE [prod_short](includes/prod_short.md)] online, a partner can develop an extension tailored to the individual tenant to fit the needs. The partner will develop the extension either by using a sandbox tenant or by obtaining a Docker image. Once the development is done, the extension can be deployed to the individual tenant.

Also, use this range as part of training and similar, such as if you're using a sandbox tenant or a build of [!INCLUDE[prod_short](includes/prod_short.md)] on Docker.

## 100,000-999,999

The objects in this range are designed when the Microsoft team localizes [!INCLUDE[prod_short](includes/prod_short.md)] for a specific country or region. These objects can't be used by partners.

## 1,000,000-69,999,999

This object range is intended for the Registered Solution Program (RSP). The partner can choose to use this range for developing extensions that can be used in [!INCLUDE[prod_short](includes/prod_short.md)] online or on-premises. When used in [!INCLUDE[prod_short](includes/prod_short.md)] online, these extensions are obtained as apps from [appsource.microsoft.com](https://appsource.microsoft.com).

## 70,000,000-74,999,999

Partners can obtain IDs in this range for extensions for [!INCLUDE[prod_short](includes/prod_short.md)] online. These extensions are obtained as apps from [appsource.microsoft.com](https://appsource.microsoft.com).

For more information, see [Get Started with Building Apps](readiness/get-started.md).

Download the [!INCLUDE[prod_short](includes/prod_short.md)] licensing guide [here](https://go.microsoft.com/fwlink/?LinkId=871590&clcid=0x409).

## See Also

[Get Started with Building Apps](readiness/get-started.md)  
[Get Started with AL](devenv-get-started.md)  
[Blog Post](https://community.dynamics.com/business/b/businesscentraldevitpro/archive/2018/10/17/which-object-ranges-can-we-use-with-microsoft-dynamics-365-business-central)


<details>

<summary>Tips for collapsed sections</summary>

### You can add a header

You can add text within a collapsed section. 

You can add an image or a code block, too.

```ruby
   puts "Hello World"
```

</details>