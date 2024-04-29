# VSCode Extensions Policy

## Extensions
By default, there should be waldo's "AL Extensions Pack" installed

![image.png](/.attachments/.VSCode-Extensions-Policy/image-a6e9a1ae-2e5a-4457-97d5-f4259a4148d6.png)

The AL Extensions Pack from Waldo is a collection of Visual Studio Code extensions specifically designed for AL development in Microsoft Dynamics 365 Business Central. It is created and maintained by Eric Wauters, also known as Waldo.

The AL Extensions Pack includes several extensions that enhance the AL development experience, such as:
1. <b>AL Language</b>: This extension provides language support for AL, including syntax highlighting, IntelliSense, code snippets, and more.

2. <b>CRS AL Language Extension</b>: This extension adds additional features and improvements to the AL Language extension, including enhanced IntelliSense, code actions, and code analysis.

3. <b>AL Object Designer</b>: This extension provides a visual designer for AL objects, allowing you to create and modify objects using a graphical interface.

4. <b>AL Code Outline</b>: This extension generates an outline view of your AL code, making it easier to navigate and understand the structure of your code.

5. <b>AL Formatter</b>: This extension automatically formats your AL code according to predefined formatting rules, improving code consistency and readability.

6. <b>AL Test Runner</b>: This extension enables you to run and debug AL unit tests directly from Visual Studio Code, making it easier to test and validate your AL code.

## Extensions settings
The settings.json file for an AL project is a configuration file that allows you to customize various settings related to the AL language and development environment in 
Visual Studio Code. It is specific to AL development and provides a way to modify the behavior and preferences of the AL language extension.
You can access the settings.json file by navigating to the .vscode folder in your AL project and opening the settings.json file within it.

![image.png](/.attachments/.VSCode-Extensions-Policy/image-ecd8ba4f-614a-4769-9aa1-33fabb6abbff.png)

> **NOTE**
> Be sure that you selected a correct scope for your extension: <b>"AppSourceCop"</b> or <b>"PerTenantExtensionCop"</b>
> It's not recommended to use both of the scopes together

Recommended AL extensions settings you can find <a href='https://dev.azure.com/ciellos-bc/Wiki/_git/AL%20Project%20Template?path=/apps/main/.vscode/settings.json' target='_blank'>here</a>