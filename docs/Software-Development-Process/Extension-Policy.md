# Extension policy

## Extension files structure
### Main application
An extension is fully contained in a single folder `\main`. This folder often contains multiple files, such as `app.json` and `launch.json` files, perhaps an image file representing the extension's logo, various folders for source; `\main\src`, other resources; `\main\src\AppResouce`. The extension doesn't need to follow a flat structure, which means that, depending on the number of application files, extra folders can be used in the `src` folder to group objects based on their functionality, which can help make maintaining a large .al project easier.

### Test application
An extension is fully contained in a single folder `\test`. This folder often contains multiple files, such as `app.json` and `launch.json` files, perhaps an image file representing the extension's logo, various folders for source; `\test\src`, other resources; `\test\src\AppResouce`. Source folder consists of 2 subfolders `Lib` which stores library codeunits to provide test data for test scenarios processing and `Test` with test codeunits inside.

### Modularity
AL project structure should keep modularity inside source folder:
```
- app
  - src
    - Functional area or Feature
      - Object type
        - Object
- test
  - src
    - Lib
        - Object type
            - Object
    - Test
        - Object
```

Recommended AL project structure can be found in the <a href='https://dev.azure.com/ciellos-bc/Wiki/_git/AL%20Project%20Template?path=/apps' target='_blank'>AL Project Template</a>.

## Сoding culture

### Code Analysis
To analyze the code we activate the available Cops: AppSourceCop, CodeCop, PerTenantExtensionCop, and UICop. See the explanation of Microsoft shared [HERE](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-using-code-analysis-tool) .
With a ruleset we can change the severity or disable rules (action = None), for more information check this [LINK](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-rule-set-syntax-for-code-analysis-tools). 
**Decisions:**
- Rule **AW0006** "Pages and reports should use the UsageCategory and ApplicationArea properties to be searchable" should not be blocked. 

### Ruleset
To make sure we all focus on the same code quality we updated the ruleSet.json to set a lot of warning to Errors. In this way we know all warning that are relevant will be solved. 

In the setting.json add the following line and make sure this file exists

    "al.ruleSetPath": "./.codeAnalysis/ruleSet.json",
    
Recommended AL Rulesests can be found <a href='https://dev.azure.com/ciellos-bc/Wiki/_git/AL%20Project%20Template?path=/apps/main/.codeAnalysis/ruleset.json' target='_blank'>here</a>

### Code Cleanup

> **ATTENTION**
> This tool must be used everytime before making a commit into a project repository branch.

<i>Run Code Cleanup on the Active Editor:</i> runs code cleanup on the current editor

<i>Run Code Cleanup on the Active Project:</i> runs code cleanup on the current project

<i>Run Code Cleanup on Uncommited Files in the Active Project:</i> runs code cleanup on all uncommited al files in the current project

![file.gif](/.attachments/.Extensions-Policy/image-8cadd3c2-b815-4587-979b-1d1896df6426.gif)

> **NOTE**
> List of actions run by code cleanup commands can be specified in alOutline.codeCleanupActions setting (setting.json file).