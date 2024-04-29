# AL Naming Policy
[[_TOC_]]


This policy is based on [Microsoft Best Practices for AL](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/compliance/apptest-bestpracticesforalcode#file-naming)

## Naming Conventions
This section describes naming of all visible items in an application such as table fields.

### Naming Objects

Two objects of the same type must not have the same name.
In general, each object must be named in a way that leaves no doubt as to what it is concerned with (for example, an object can be specifically related to customers, items or resources). Do not name a table “Status,” for example, because the word Status is too general and could refer to something in almost every table.

<ins>Table Objects</ins>

Table objects are always named in the singular. That is, the table name corresponds to what one record in the table is called.

<ins>Page Objects</ins>

The name of a page depends on the page type.
A card page has the singular form of the table name. 
A tabular page has the plural form of the table name. 
This gives the users an idea of the type of form they have selected or that will be presented. If a table can be accessed by both a card page and a tabular page, the page names should explicitly describe the page types (for example, Item Card and Item List). This tells the user that there is more than one way to access the table. Other page types (statistics, for example) are given names that are as descriptive as possible.

<ins>Report Objects</ins>

Users see names of report objects when they need to identify a sales invoice, for example, or when they modify or create reports. Object names also appear in the request window. This is why these should be as descriptive as possible and not include abbreviations. Whenever possible, the object name should be the same as the heading in the actual report.

### Table and Page extension naming

For table and page extensions object name contains **[prefix][space][principal object name]**
For object extensions – table extension, page extension, etc., the short name without space but uppercase is used.
Examples,

```
pageextension 70553579 "MyPrefix CustomerLedgerEntries" extends "Customer Ledger Entries"

tableextension 70553580 "MyPrefix SalesCrMemoLine" extends "Sales Cr.Memo Line"
```

### Report Template Naming
Report template (rdlc, word, excel) name should be the same as report name with suffix , 002, 003 added
Examples,

| Report                | Report file name                                                                                                              | Template file name |
|--------------------------------------------------|-----|----------------------|
| report 70553575 "MyPrefix Prepare Trust Journal" | MyPrefixPrepareTrustJournal.Report.al|<br>MyPrefixPrepareTrustJournal.rdlc</br><br>MyPrefixPrepareTrustJournal02.rdlc</br> |

## File Naming

Each file name has object names with only characters [A-Za-z0-9], object type, and dot al, for file type. In your extension, the name of each new application object (table, page, codeunit), can contain a prefix or suffix. 

File name
- Can contain any letters from a to z and any numbers from 0 through 9.
- Must not cont ain spaces and special characters, including @ (at sign), - (hyphen or dash), _ (underscore ), * (asterisk), & and sign).
- Must not contain non-English characters (such as é, è, ç, etc.).</
- Is case-sensitive.
- Should be unique for extension regardless of location in different folders (The same file name causes problem while exporting source of extension from web client)

The CodeCop analyzer suggests that the object name is part of the file name, which is encouraged as a best practice. Adding any affixes to the file names is voluntary.

   > **NOTE**   
   > If you are submitting an app to AppSource, you must follow the guidance in the [Technical Validation Checklist] 
   > (../developer/devenv-checklist-submission.md).

### File naming notation

Follow the syntax for file naming as shown in the table:

| Full objects                                   | Extensions                                        |
|------------------------------------------------|---------------------------------------------------|
| `<ObjectNameSuffix>.<FullTypeName>.al`         | `<ObjectNameSuffix>.<FullTypeName>Ext.al`         |
| `<PrefixObjectName>.<FullTypeName>.al`         | `<PrefixObjectName>.<FullTypeName>Ext.al`         |
| `<ObjectNameExcludingAffix>.<FullTypeName>.al` | `<ObjectNameExcludingAffix>.<FullTypeName>Ext.al` |

> **ATTENTION**
> Due to restriction of maximum number of characters in application object names to 30 characters abbreviate names using a period 

```
table 70553580 "MyPrefix Job Tr. Job Plan. Line"
```

### Type map

Use the listed abbreviations for each type of object in the file naming:

| Object                   | Abbreviation     |
|--------------------------|------------------|
| Page                     | Page             |
| Page Extension           | PageExt          |
| Page Customization       | PageCust         |
| Codeunit                 | Codeunit         |
| Table                    | Table            |
| Table Extension          | TableExt         |
| XML Port                 | Xmlport          |
| Report                   | Report           |
| Request Page             | RequestPage      |
| Query                    | Query            |
| Enum                     | Enum             |
| Enum Extension           | EnumExt          |
| Control Add-ins          | ControlAddin     |
| Dotnet                   | Dotnet           |
| Profile                  | Profile          |
| Interface                | Interface        |
| Permission Set           | PermissionSet    |
| Permission Set Extension | PermissionSetExt |


### File naming examples

For the listed objects in the table, these examples show how to name the files.

| Object name                                                        | File name                         |
|--------------------------------------------------------------------|-----------------------------------|
| codeunit 70000000 MyPrefixSalesperson                              | `MyPrefixSalesperson.Codeunit.al` |
| page 70000000 MyPrefixSalesperson                                  | `MyPrefixSalesperson.Page.al`     |
| pageextension 70000000 MyPrefixSalesperson extends "Customer Card" | `MyPrefixSalesperson.PageExt.al`  |

### Examples of object naming

#### Table

```
table 70000000 MyPrefixSalesperson
```

#### Page

```
page 70000000 MyPrefixSalesperson
```

#### Action

```
actions
{
    addafter(ApprovalEntries)
    {
        action(MyPrefixVacation)
```

#### Codeunit

```
codeunit 70000000 MyPrefixSalesperson
```
###Translation Files Naming

[Working with translation files](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-work-with-translation-files)

You can have only one .xlf file per language. If you translate your extension to multiple languages, you must have a translation file per language.
Name files as <extensionname>.<language>.xlf and place them into **.\Translations folder**

**Examples**
<extensionname>.en-CA.xlf
<extensionname>.fr-CA.xlf
<extensionname>.g.xlf

###Namespaces

AL amespaces should be used to organize and group related objects together. They provide a way to avoid naming conflicts and improve code readability. Here is an example of how to define a namespace in AL:
```
namespace MyCompany.MyApplication.Functionality;

codeunit MyCodeunit
{
    procedure MyProcedure()
    begin
        // Code goes here
    end
}
```
Also, namespaces can be nested, allowing for further organization of objects. It is a best practice to use meaningful and descriptive names for namespaces to make your code more maintainable.

In this example, the codeunit MyCodeunit is defined within the namespace MyCompany.MyApplication.Functionality. To access the codeunit or any other objects within the namespace, you would use the fully qualified name, like MyCompany.MyApplication.Functionality.MyCodeunit:
```
namespace MyCompany.MyApplication.OtherFunctionality;

codeunit OtherCodeunit
{
    procedure SomeProcedure()
    var
        MyCodeunit: Codeunit MyCompany.MyApplication.Functionality.MyCodeunit;
    begin
        MyCodeunit.MyProcedure();
        // Rest of the code
    end;
}
```
or call the namespace via **using** keyword

```
namespace MyCompany.MyApplication.OtherFunctionality;

using MyCompany.MyApplication.Functionality;

codeunit OtherCodeunit
{
    procedure SomeProcedure()
    var
        MyCodeunit: Codeunit MyCodeunit;
    begin
        MyCodeunit.MyProcedure();
        // Rest of the code
    end;
}
```
In this example, the using statement is used to attach the MyCompany.MyApplication.Functionality namespace to the MyCodeunit object. Now, you can directly reference objects within the namespace, such as the MyCodeunit codeunit, without specifying the fully qualified name.

> <b> NOTE </b>
> Please note that the namaspace and using statements should be placed at the beginning of the codeunit or any other object where you want to use the objects within the namespace. <br/>
> <u>The namespace mask is next:</u> 
> <b>namespace PublisherName.ApplicationName.FeatureOrFunctionalArea;</b>