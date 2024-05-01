- [Introduction](#introduction)
- [Important changes](#important-changes)
- [Links](#links)
- [Report Layouts](#report-layouts)
  - [Create a new layout](#create-a-new-layout)
    - [Create a new layout by copying](#create-a-new-layout-by-copying)
  - [Modify a layout](#modify-a-layout)
- [Setting the Layout Used by a Report](#setting-the-layout-used-by-a-report)
  - [Set the layout from the Report Layouts page](#set-the-layout-from-the-report-layouts-page)
  - [Set the layout from Report Layout Selection page](#set-the-layout-from-report-layout-selection-page)
- [Register layout from the code.](#register-layout-from-the-code)
- [Storing layouts for different customers](#storing-layouts-for-different-customers)



# Introduction

Many of us have had the headache of the endless back and forth process of editing layouts.
This is especially true for checks, invoices, order confirmation.
When, armed with a ruler, we must adjust text with millimeter accuracy. Or just change size of logo.  
And so on and so forth.
The process is complicated by the fact that we are required to publish new version of app in the Test or UAT environments to allow key users to test.
Below we provide you with a workaround to avoid these problems.

To do this we need to do the following:

- [ ] Create new custom layout based on existing one
- [ ] Modify the created custom layout
- [ ] Load it to Test(UAT) environment
- [ ] Set the created custom layout as the Layout Used by a Report
- [ ] Let key users make test
- [ ] After successful testing, place the layout in application code


# Important changes

----

> <span style="color:red">**Attention**</span>
>
> **[Custom report layouts](https://learn.microsoft.com/en-us/dynamics365/business-central/ui-how-create-custom-report-layout) is a legacy feature that is being phased out. Instead, you should start creating user-defined layouts as described [here](https://learn.microsoft.com/en-us/dynamics365/business-central/ui-get-started-layouts).**

----

# Links
[Defining Multiple Report Layouts](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-multiple-report-layouts)
```csharp
reportextension 50102 EmpReportExt extends "Employee - List"
{
    rendering
    {
        layout(LayoutExcelPivot)
        {

            Type = Excel;
            Caption = 'ExcelPivot';
            Summary = 'Employee list shown in Pivot table in Excel';
            LayoutFile = 'EmpShownAsPivot.xlsx';
        }

        layout(LayoutExcel)
        {
            Type = Excel;
            Caption = 'ExcelColumns';
            Summary = 'Employee list sorted by last name in Excel';
            LayoutFile = 'EmpSortedByLastName.xlsx';
        }

        layout(LayoutWord)
        {
            Type = Word;
            Caption = 'WordList';
            Summary = 'Employee list sorted by last name in Word';
            LayoutFile = 'EmpSortedByLastName.docx';
        }
    }
}
```

# Report Layouts

[Report and Document Layouts Overview](https://learn.microsoft.com/en-ca/dynamics365/business-central/ui-manage-report-layouts)

A report layout determines the look of a report. It controls which data fields of a report dataset appear, how they are arranged, styled, and more. A report may have more than one layout, which you can then switch among as needed.

When there are multiple companies in the application, the layouts are set on a per-company basis. So the same report in one company can have a different layout in another company.

## [Create a new layout](https://learn.microsoft.com/en-ca/dynamics365/business-central/ui-get-started-layouts?tabs=export#create-a-new-layout)

### Create a new layout by copying

Copying is a quick way to create a new layout that's the same as an existing layout. Once you have the copy, you'll make modifications by exporting the layout.

<OL style="margin: 16px 0px 16px 38px;padding: 0px;color: rgb(22, 22, 22);font-family: &amp;quot;font-size: 16px;font-style: normal;font-weight: 400;letter-spacing: normal;text-align: start;text-indent: 0px;text-transform: none;word-spacing: 0px;white-space: normal;background-color: rgb(255, 255, 255)"><LI style="margin: 0px;padding: 0px;list-style: decimal"><P style="margin: 1rem 0px 0px;padding: 0px">Choose the<SPAN> </SPAN><IMG  src="https://learn.microsoft.com/en-us/dynamics365/business-central/media/ui-search/search_small.png"  alt="Lightbulb that opens the Tell Me feature 0."  title="Tell me what you want to do" style="border: 0px;height: auto;vertical-align: baseline"/><SPAN> </SPAN>icon, enter<SPAN> </SPAN><STRONG style="font-weight: 600">Report Layouts</STRONG>, and then choose the related link.</P><P style="margin: 1rem 0px 0px;padding: 0px">The<SPAN> </SPAN><STRONG style="font-weight: 600">Report Layouts</STRONG><SPAN> </SPAN>page appears and lists all the layouts currently available for all reports.</P></LI></OL>

![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture01.png)

1. Select the layout that you want a copy of for your new layout, then choose the **Edit Info** action.
   If you selected an extension layout, you're prompted whether you want to edit a copy. To continue, select **Yes**.

     > _**TIP**_
     >
     > _To help you find the layout, use the **Search** box, **Filter** pane, and columns sorting._

   In our example we do this for Report **./SalesReceivables/Document/StandardSalesOrderConf.rdlc**

![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture02.png)

2. Change the **Layout Name**.
   You can add prefix or suffix in **Layout Name** and **Description**.

![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture03.png =500x250)

3. Turn the **Save Changes to Copy** switch to **On**, then select **OK**

   The new layout shows in the **Report Layouts** page.

![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture04.png)

---

## Modify a layout

Follow these steps to modify an existing user-defined layout.

1. Select the layout that you want to modify, then choose the **Export Layout** action.

   The layout file is downloaded to your device.

   > **_TIP_**
   >
   > _To help you find the layout, use the **Search** box, **Filter** pane, and columns sorting._

   ![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture05.png)

3. Open the layout file in the appropriate application, like Word (for a .docx file) or Excel (for an .xlsx file).

   For more information, see:

   - [Work with Word Layouts](https://learn.microsoft.com/en-us/dynamics365/business-central/ui-how-add-fields-word-report-layout)
   - [Work with Excel Layouts](https://learn.microsoft.com/en-us/dynamics365/business-central/ui-excel-report-layouts)
   - [Work with RDLC Layouts](https://learn.microsoft.com/en-us/dynamics365/business-central/ui-rdlc-report-layouts)

   Make changes to the file and save it.

4. Back on the **Report Layouts** page, select the existing layout, then select the **Replace Layout** action.
5. Select **OK** > **Choose** to open file explorer on your device.
6. Find and select the exported Word file, then select **Open**.

   The selected file is uploaded to the layout, and you return to the **Report Layouts** page.
7. If you want to see how the report looks with the new layout, select the layout in the list, then select **Run Report**.

# Setting the Layout Used by a Report

> **ATTENTION**
>> To use modified Word Report Layout you need to set it as default in **Report Layout Selection**
>> In the current version it is not possible to select **Word Report Layout** from the **Report Request Page**
>> ![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture06.png)
>> For RDLC report layouts it is not necessary

There are a few ways to set which layout a report uses. Each way has advantages, depending on what you're looking to do:

- From the report request page

  When setting up a report to run, the report request page includes the **Reports Layout** field that shows the current default layout used by the report. You can use this field to temporarily switch to another available layout the report you're running. After you run the report, the layout will revert to the default layout again.
  
 ![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture07.png)

 ![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture08.png)

- From the **Report Layout Selection** page

  The **Report Layout Selection** page displays a list of all reports. This page indicates what the current default layout for a report is. It lets you set layouts in different companies, without having to switch the company you're working with.

- From the **Report Layouts** page
  The **Report Layouts** page displays all available layouts for each report in the current company. It's also used to specify the default layout for reports. It's easy to find a specific layout by sorting or filtering the list. Once you find the layout, you can set it for a report with a single selection.

  > **_Note_**
  > _You can't use the **Report Layouts** page for Word and RDLC layouts that were created by using the legacy **Custom Layouts** feature. In fact, you won't even see these custom layouts listed on the **Report Layouts** page. For these layouts, you can only set them by using **Report Layout Selection** page._

## Set the layout from the Report Layouts page

Find the layout in the list, select it, then select the **Set Default** action at the top of the page.

## Set the layout from Report Layout Selection page

1. Set the **Company** field at the top to the company that includes the report.
2. Find and select the report in the list, then do one of the following steps:

   - If the layout that you want to switch to is a different type than the current layout, select the **Layout Type** field, then choose the type of the layout you want to set on the report.
   - If the layout that you want to switch to the same type as the current layout, select the **Select Layout** action at the top.
    ![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture09.png)

3. In the **Report Layouts** page, select the layout, then select **OK**.

# Register layout from the code.
Add code registered layout in 

**Install codeunit**

```csharp
codeunit 50130 "Prefix OnInstall"
{
    Subtype = Install;

    trigger OnInstallAppPerCompany()
    begin
        SetReportLayout()
    end;
```

**Upgrade Codeunit**
```csharp

codeunit 50100 "Prefix OnUpgrade"

{
    Subtype = Upgrade;

    trigger OnUpgradePerCompany()
    begin
        SetReportLayout()
    end;
```

you can use the same procedure
```csharp
    var
        TenantReportLayoutSelection: Record "Tenant Report Layout Selection";
        ReportLayoutSelection: Record "Report Layout Selection";
        AppInfo: ModuleInfo;

    procedure SetReportLayout()
    begin
        NavApp.GetCurrentModuleInfo(AppInfo);

        RegistryLayout(Report::"Item List", './src/Layouts/COSSItemList.rdlc', ReportLayoutSelection.type::"RDLC (built-in)");
    end;

    procedure RegistryLayout(ReportId: Integer; LayoutName: text[250]; ReportType: Option)
    begin
        TenantReportLayoutSelection.Init();
        TenantReportLayoutSelection."App ID" := AppInfo.Id;
        TenantReportLayoutSelection."Company Name" := CompanyName;
        TenantReportLayoutSelection."Layout Name" := LayoutName;
        TenantReportLayoutSelection."Report ID" := ReportId;
        if not TenantReportLayoutSelection.Insert(true) then
            TenantReportLayoutSelection.Modify(true);

        ReportLayoutSelection.SetRange("Report ID", ReportId);
        if ReportLayoutSelection.FindSet() then
            ReportLayoutSelection.DeleteAll();
        ReportLayoutSelection.Init();
        ReportLayoutSelection."Company Name" := CompanyName;
        ReportLayoutSelection."Report ID" := ReportId;
        ReportLayoutSelection.Type := ReportType;
        if not ReportLayoutSelection.Insert(true) then
            ReportLayoutSelection.Modify(true);
    end;
}
```  

# Storing layouts for different customers

Sometimes, we are forced to store layouts for each customer separately. To do this, use a separate folder in the repository 

![image.png](./.attachments/.How-to-Use-Custom-Report-Layouts-in-Development/HTUCRLID_Picture10.png)

In this case, you need to load and register layout manually.  

