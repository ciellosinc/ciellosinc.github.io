[[_TOC_]]

# Links

[Use Markdown in Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/project/wiki/markdown-guidance?view=azure-devops)

[GitHub: Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

# Tips & Tricks

## How to work with pictures

All pictures are saved in the folder .attachments.
In order to simplify the transfer of articles from one source to another, for each article it is necessary to create its own folder with the same name as the article, and be sure to add a dot (.) at the beginning. Replace all special symbols and spaces by dash '-'

**Example**
The name of the file containing this article will be **How-to%3A-Work-with-Wiki.md**
So, we create folder "**/.attachments/.How-to-A-Work-with-Wiki**" and paste pictures there

![image](/.attachments/.How-to-A-Work-with-Wiki/HTAWWWPicture01.png)

and in the code we paste image as

```wiki
![image.png](/.attachments/.How-to-A-Work-with-Wiki/HTAWWWPicture01.png)
```

# Basic formatting syntax

## Headers

**Example:**
```markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Result:**

![image.png](/.attachments/.How-to-A-Work-with-Wiki/HTAWWWPicture02.png)

## Blockquotes

**Example:**

<pre>
> Single line quote
>> Nested quote
>> multiple line
>> quote
</pre>

**Result:**  

> Single line quote
>> Nested quote
>> multiple line
>> quote

## Horizontal rules

To add a horizontal rule, add a line that's a series of dashes `---`. The line above the line containing the `---` must be blank.

**Example:**

```wiki
above    

-----    
below 
```

**Result:**  

above    

-----    
below    

## Emphasis (bold, italics, strikethrough) 

You can emphasize text by applying bold, italics, or strikethrough to characters:

- To apply italics: surround the text with an asterisk `*` or underscore `_` 
- To apply bold: surround the text with double asterisks `**`.
- To apply strikethrough: surround the text with double tilde characters `~~`.

Combine these elements to apply emphasis to the text.

> <b>NOTE</b>  
> There is no Markdown syntax that supports underlining text. Within a wiki page, you can use the HTML `<u>` tag to generate underlined text. For example, `<u>underlined text</u>` yields <u>underlined text</u>.

**Example:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~  
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

**Result:**  

Use _emphasis_ in comments to express **strong** opinions and point out <s>corrections</s>  
**_Bold, italicized text_**
**~~Bold, strike-through text~~**  

## Code highlighting

Highlight suggested code segments using code highlight blocks.
To indicate a span of code, wrap it with three backtick quotes (`&#96;&#96;&#96;`) on a new line at both the start and end of the block. To indicate code inline, wrap it with one backtick quote (`&#96;`).

Code highlighting entered within the Markdown widget renders code as plain preformatted text.

**Example:**

<pre>&#96;&#96;&#96;
sudo npm install vsoagent-installer -g  
&#96;&#96;&#96;
</pre>  

**Result:**

```
sudo npm install vsoagent-installer -g
```

**Example:**

<pre>
&#96;&#96;&#96;To install the Microsoft Cross Platform Build & Release Agent, run the following: &#96;$ sudo npm install vsoagent-installer -g&#96;.
&#96;&#96;&#96; 
</pre>

**Result:**

To install the Microsoft Cross Platform Build & Release Agent, run the following command: `$ sudo npm install vsoagent-installer -g`.  

<br/>

Within a Markdown file, text with four spaces at the beginning of the line automatically converts to a code block.  

Set a language identifier for the code block to enable syntax highlighting for any of the supported languages in [highlightjs](https://github.com/highlightjs/highlight.js/tree/stable-11/src/languages).

<pre>
``` language
code
```
</pre>

<br/>

**More examples:**

<pre>
``` js
const count = records.length;
```
</pre>

``` js
const count = records.length;
```

<br/>

<pre>
``` csharp
Console.WriteLine("Hello, World!");
```
</pre>

``` csharp
Console.WriteLine("Hello, World!");
```

## Tables

Organize structured data with tables. Tables are especially useful for describing function parameters, object methods, and other data with a
clear name to description mapping.

- Place each table row on its own line.
- Separate table cells using the pipe character `|`.
- To use a pipe character within a table, you must escape with a backslash `\|`.
- The first two lines of a table set the column headers and the alignment of elements in the table.
- Use colons (`:`) when dividing the header and body of tables to specify column alignment (left, center, right).
- To start a new line, use the HTML break tag (`<br/>`) (works within a Wiki but not elsewhere).  
- Make sure to end each row with a CR or LF.
- You must enter a blank space before and after work item or pull request (PR) mentioned inside a table cell.

**Example:**

```markdown
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```

**Result:**  

| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:---------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  

## Lists

### Ordered or numbered lists

**Example:**  
```markdown
1. First item.
2. Second item.
3. Third item.
```

**Result:**  
1. First item.
2. Second item.
3. Third item.

### Bulleted lists

**Example:**

```
- Item 1
- Item 2
- Item 3
```

**Result:**

- Item 1
- Item 2
- Item 3

### Nested lists

**Example:**  
```
1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
      - Further nested item 1
      - Further nested item 2
      - Further nested item 3
   - Nested item 2
   - Nested item 3
```

**Result:**  

1. First item.
    - Item 1
    - Item 2
    - Item 3
2. Second item.
    - Nested item 1
       - Further nested item 1
       - Further nested item 2
       - Further nested item 3 
    - Nested item 2
    - Nested item 3

## Links

In Markdown files and widgets, you can set text hyperlinks for your URL using the standard Markdown link syntax:

```markdown
[Link Text](Link URL)
```

When you link to another Markdown page in the same Git or TFVC repository, the link target can be a relative path or an absolute path in the repository.  

**Supported links for Welcome pages:**

- Relative path: `[text to display](target.md)` 
- Absolute path in Git: `[text to display](/folder/target.md)`
- Absolute path in TFVC: `[text to display]($/project/folder/target.md)`
- URL: `[text to display](http://address.com)`

**Supported links for Markdown widget:**

<ul>
- URL: `[text to display](http://address.com)`  </br>
</ul>

**Supported links for Wiki:**  
<ul>
- Absolute path of Wiki pages: `[text to display](/parent-page/child-page)` </br>
- URL: `[text to display](http://address.com)`  </br>
</ul>

> <b>NOTE</b>  
> - Links to documents on file shares using `file://` aren't supported on 2017.1 and later versions. This restriction has been implemented for security purposes.
> - For information on how to specify relative links from a Welcome page or Markdown widget, see [Source control relative links](#source-control-relative-links).

**Example:**  

```
[C# language reference](/dotnet/csharp/language-reference/)
```

**Result:**

[C# language reference](/dotnet/csharp/language-reference/)

<a id="relative-links">  </a>


### [Anchor links](#anchor-links)

Within Markdown files, anchor IDs are assigned to all headings when rendered as HTML. The ID is the heading text, with the spaces replaced by dashes (-) and all lower case. In general, the following conventions apply:

- Punctuation marks and leading white spaces within a file name are ignored
- Upper case letters convert to lower case letter
- Spaces between letters convert to dashes (-)

**Example:**

```
###Link to a heading in the page
```

<br/>

**Result:**

The syntax for an anchor link to a section...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre>

The ID is all lower case, and the link is case-sensitive, so be sure to use lower case, even though the heading itself uses upper case.

You can also reference headings within another Markdown file:

<pre>
[text to display](./target.md#heading-id)  
</pre>

In wiki, you can also reference heading in another page:

<pre>
[text to display](/page-name#section-name)
</pre>

<a name="images"> </a>

## Images

To highlight issues or make things more interesting, you can add images and animated GIFs to the following aspects of your pull requests.

- Comments
- Markdown files
- Wiki pages

Use the following syntax to add an image: <div id="do_not_render"><pre>&#33;&#91;Text](URL)</pre></div> The text in the brackets describes the linked image and the URL points to the image location.

**Example:**

<pre>
![Illustration to use for new users](https://azurecomcdn.azureedge.net/cvt-779fa2985e70b1ef1c34d319b505f7b4417add09948df4c5b81db2a9bad966e5/images/page/services/devops/hero-images/index-hero.jpg)
</pre>

**Result:**

The path to the image file can be a relative path or the absolute path in Git or TFVC, just like the path to another Markdown file in a link.  

- Relative path: `![Image alt text](./image.png)`  
- Absolute path in Git: `![Image alt text](/media/markdown-guidance/image.png)`  
- Absolute path in TFVC: `![Image alt text]($/project/folder/media/markdown-guidance/image.png)`  
- Resize image: `IMAGE_URL =WIDTHxHEIGHT`
  
  </br>

  > <b>NOTE</b>
  > Be sure to include a space before the equal sign.
  >- Example: `![Image alt text]($/project/folder/media/markdown-guidance/image.png =500x250)`
  >- It's also possible to specify only the WIDTH by leaving out the HEIGHT value: `IMAGE_URL =WIDTHx`

## Checklist or task list

Use `[ ]` or `[x]` to support checklists. Precede the checklist with either `-<space>` or `1.<space>` (any numeral).

**Example**

```wiki
**What testing scenarios are required?**
- [x] Create new Account
- [ ] Add new user
- [ ] Assign licenses
```

**Result:**  

**What testing scenarios are required?**

- [x] Create new Account
- [ ] Add new user
- [ ] Assign licenses

> <b> NOTE </b>
> A checklist within a table cell isn't supported.

## Emoji

In pull request comments and wiki pages, you can use emojis to add character and react to comments in the request. Enter what you're feeling surrounded by `:` characters to get a matching emoji in your text. We support the [full set of emojis](https://www.webpagefx.com/tools/emoji-cheat-sheet/).

**Example:**
<pre>
:smile:
:angry:
</pre>

**Result:**  

:smile: :angry:

To escape emojis, enclose them using the `\` character.

**Example:**

```wiki
\:smile: \:) \:angry:
```

**Result:**

 \:smile: \:) \:angry:

## Ignore or escape Markdown syntax to enter specific or literal characters
   
To insert one of the following characters, prefix with a `&#92;`(backslash).  
      `&#92;`, backslash   
      `&#96;`, backtick  
      `&#95;`, underscore  
      `{}`, curly braces  
      `[]`, square brackets  
      `()`, parentheses  
      `#`, hash mark  
      `+`, plus sign 
      `-`, minus sign (hyphen) 
      `.`, period  
      `!`, exclamation mark 
      `*`, asterisk
   
Some examples on inserting special characters:  
      Enter `&#92;&#92;` to get \   
      Enter `&#92;&#95;` to get &#95;   
      Enter `&#92;#` to get #  
      Enter `&#92;(` to get (  
      Enter `&#92;.` to get .  
      Enter `&#92;!` to get !  
      Enter `&#92;*` to get *  

## Attachments

Attachments support the following file formats:

|          Type          | File formats |
|------|---------|
| Code | CS (.cs), Extensible Markup Language (.xml), JavaScript Object Notation (.json), Hypertext Markup Language(.html, .htm), Layer (.lyr), Windows PowerShell script (.ps1), Roshal Archive (.rar), Remote Desktop Connection (.rdp), Structured Query Language (.sql) - **Note: Code attachments aren't permitted in PR comments**  |
| Compressed files | ZIP (.zip) and GZIP (.gz) |
| Documents | Markdown (.md), Microsoft Office Message (.msg), Microsoft Project (.mpp), Word (.doc and .docx), Excel (.xls, .xlsx and .csv), and Powerpoint (.ppt and .pptx), text files (.txt), and PDFs (.pdf) | 
| Images | PNG (.png), GIF (.gif), JPEG (both .jpeg and .jpg), Icons (.ico) | 
| Visio | VSD (.vsd and .vsdx)  |
| Video | MOV (.mov), MP4 (.mp4) |

> <b> NOTE </b>
> Not all file formats are supported within pull requests, such as Microsoft Office Message (.msg) files.

## Mathematical notation and characters

We support both inline and block [KaTeX](https://khan.github.io/KaTeX/function-support.html) notation in wiki pages and pull requests. See the following supported elements:

- Symbols
- Greek letters
- Mathematical operators
- Powers and indices
- Fractions and binomials
- Other KaTeX supported elements

To include mathematical notation surround the mathematical notation with a `$` sign for inline and `$$` for block,  as shown in the following examples:

> <b> NOTE </b>  
> This feature is supported within Wiki pages and pull requests for TFS 2018.2 or later versions.

### Example: Greek characters

```KaTeX
$
\alpha, \beta, \gamma, \delta, \epsilon, \zeta, \eta, \theta, \kappa, \lambda, \mu, \nu, \omicron, \pi, \rho, \sigma, \tau, \upsilon, \phi, ...
$  


$\Gamma,  \Delta,  \Theta, \Lambda, \Xi, \Pi, \Sigma, \Upsilon, \Phi, \Psi, \Omega$
```

**Result:**
$
\alpha, \beta, \gamma, \delta, \epsilon, \zeta, \eta, \theta, \kappa, \lambda, \mu, \nu, \omicron, \pi, \rho, \sigma, \tau, \upsilon, \phi, ...
$  


$\Gamma,  \Delta,  \Theta, \Lambda, \Xi, \Pi, \Sigma, \Upsilon, \Phi, \Psi, \Omega$

### Example: Algebraic notation

```KaTeX
Area of a circle is $\pi r^2$

And, the area of a triangle is:

$$
A_{triangle}=\frac{1}{2}({b}\cdot{h})
$$
```

**Result:**
Area of a circle is $\pi r^2$

And, the area of a triangle is:

$$
A_{triangle}=\frac{1}{2}({b}\cdot{h})
$$

### Example: Sums and Integrals

```KaTeX
$$
\sum_{i=1}^{10} t_i
$$

$$
\int_0^\infty \mathrm{e}^{-x}\,\mathrm{d}x
$$     
```

**Result:**
$$
\sum_{i=1}^{10} t_i
$$

$$
\int_0^\infty \mathrm{e}^{-x}\,\mathrm{d}x
$$     

## Add Mermaid diagrams to a wiki page

Mermaid lets you create diagrams and visualizations using text and code. 

> <b> NOTE </b>
> - Not all syntax in the following linked content for diagram types works in Azure DevOps. For example, we don't support most HTML tags, Font Awesome, `flowchart` syntax (`graph` used instead), or LongArrow `---->`. 
> - Mermaid isn't supported in the Internet Explorer browser.
> - If you experience an "Unsupported diagram type," the functionality may not be yet available in your organization due to usual deployment scheme.

Wiki supports the following Mermaid diagram types:

- [Sequence diagrams](https://mermaid-js.github.io/mermaid/#/sequenceDiagram)
- [Gantt charts](https://mermaid-js.github.io/mermaid/#/gantt)
- [Flowcharts](http://mermaid-js.github.io/mermaid/#/flowchart)
- [Class diagram](https://mermaid-js.github.io/mermaid/#/classDiagram)
- [State diagram](https://mermaid-js.github.io/mermaid/#/stateDiagram)
- [User journey](https://mermaid-js.github.io/mermaid/#/user-journey)
- [Pie chart](https://mermaid-js.github.io/mermaid/#/pie)
- [Requirements diagram](https://mermaid-js.github.io/mermaid/#/requirementDiagram)

For more information, see the [Mermaid release notes](https://github.com/mermaid-js/mermaid/releases) and [active requests in the Developer Community](https://developercommunity.visualstudio.com/search?space=21&q=mermaid&stateGroup=active).

To add a Mermaid diagram to a wiki page, use the following syntax:

``` wiki-mermaid
::: mermaid
<mermaid diagram syntax>
:::
```
### Sequence diagram example

A sequence diagram is an interaction diagram that shows how processes operate with one another and in which order.

```markdown
::: mermaid
sequenceDiagram
New->>Ready for Estimate: Application Specialist (AP)
alt Not enough information
Ready for Estimate->>New: Technical Architect (TA)
New->>Ready for Estimate: Application Specialist (AP)
else Enough information
Ready for Estimate->>Estimate: Technical Architect (TA)
end
Estimate->>Ready for Approval: Technical Architect (TA)
Ready for Approval->>Approved: Project Manager (PM)
alt Not approved
Ready for Approval->>Estimate: Project Manager (PM)
Estimate->>Ready for Approval: Technical Architect (TA)
else Approved 
Ready for Approval->>Approved: Project Manager (PM)
Approved->>In Progress: Technical Architect (TA)
end
Note over Ready for Approval,Approved:Environment - Test
Note over Ready for Estimate,Estimate:Environment - Preprod
:::
```

::: mermaid
sequenceDiagram
participant New as New
create actor R as Requester
create actor AP as Application Specialist (AP)
R->>AP: Send request by e-mail
AP->>New: Create new work item (PBI, Bug) 
New->>Ready for Estimate: Application Specialist (AP)
alt Not enough information
Ready for Estimate->>New: Technical Architect (TA)
New->>Ready for Estimate: Application Specialist (AP)
else Enough information
Ready for Estimate->>Estimate: Technical Architect (TA)
end
Estimate->>Ready for Approval: Technical Architect (TA)
Ready for Approval->>Approved: Project Manager (PM)
alt Not approved
Ready for Approval->>Estimate: Project Manager (PM)
Estimate->>Ready for Approval: Technical Architect (TA)
else Approved 
Ready for Approval->>Approved: Project Manager (PM)
Approved->>In Progress: Technical Architect (TA)
end
Note over Ready for Approval,Approved:Environment - Test
Note over Ready for Estimate,Estimate:Environment - Preprod
:::
### Gantt chart example

A Gantt chart records each scheduled task as one continuous bar that extends from the left to the right. The `x` axis represents time and the `y` records the different tasks and the order in which they're to be completed.

When you exclude a date, day, or collection of dates specific to a task, the Gantt chart accommodates those changes by extending an equal number of days toward the right, not by creating a gap inside the task.

```markdown
::: mermaid
gantt
    title A Gantt chart
    dateFormat YYYY-MM-DD
    excludes 2022-03-16,2022-03-18,2022-03-19
    section Section

    A task          :a1, 2022-03-07, 7d
    Another task    :after a1 , 5d
:::
```

::: mermaid
gantt
    title A Gantt chart
    dateFormat YYYY-MM-DD
    excludes 2022-03-16,2022-03-18,2022-03-19
    section Section

    A task          :a1, 2022-03-07, 7d
    Another task    :after a1 , 5d
:::

### Flowchart example

A flowchart is composed of nodes, geometric shapes and edges, and arrows or lines.
The following example shows a flowchart using `graph` rather than `flowchart`. 

> [!NOTE]
> We don't support `---->` or `flowchart` syntax, nor links to and from `subgraph`.

```
:::mermaid
graph LR;
    A[Hard edge] -->|Link text| B(Round edge) --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
:::
```

:::mermaid
graph LR;
    A[Hard edge] -->|Link text| B(Round edge) --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
:::

### Class diagram example

The class diagram is main part of object-oriented modeling. The diagram describes objects, their attributes, methods, and inheritance between them. 

```
:::mermaid
classDiagram
    Creature <|-- Superman
    Creature <|-- Vampire
    Creature <|-- Diavolo
    Creature: +int size
    Creature: +int weight
    Creature: +isBenign()
    Creature: +power()
    class Superman{
        +String currentName
        +fly()
        +heal()
    }
    class Vampire{
        -int age
        -canBite()
    }
    class Diavolo{
        +bool is_serving
        +heat()
    }
:::
```

classDiagram
    Creature <|-- Superman
    Creature <|-- Vampire
    Creature <|-- Diavolo
    Creature: +int size
    Creature: +int weight
    Creature: +isBenign()
    Creature: +power()
    class Superman{
        +String currentName
        +fly()
        +heal()
    }
    class Vampire{
        -int age
        -canBite()
    }
    class Diavolo{
        +bool is_serving
        +heat()
    }
:::

### State diagram example

The state diagram is used to describe how the system states can change from one to another. 

```
:::mermaid
stateDiagram-v2
    [*] --> Active
    state Active {
        [*] --> NumLockOff
        NumLockOff --> NumLockOn : EvNumLockPressed
        NumLockOn --> NumLockOff : EvNumLockPressed
        --
        [*] --> CapsLockOff
        CapsLockOff --> CapsLockOn : EvCapsLockPressed
        CapsLockOn --> CapsLockOff : EvCapsLockPressed
        --
        [*] --> ScrollLockOff
        ScrollLockOff --> ScrollLockOn : EvScrollLockPressed
        ScrollLockOn --> ScrollLockOff : EvScrollLockPressed
    }
:::
```

:::mermaid
stateDiagram-v2
    [*] --> Active
    state Active {
        [*] --> NumLockOff
        NumLockOff --> NumLockOn : EvNumLockPressed
        NumLockOn --> NumLockOff : EvNumLockPressed
        --
        [*] --> CapsLockOff
        CapsLockOff --> CapsLockOn : EvCapsLockPressed
        CapsLockOn --> CapsLockOff : EvCapsLockPressed
        --
        [*] --> ScrollLockOff
        ScrollLockOff --> ScrollLockOn : EvScrollLockPressed
        ScrollLockOn --> ScrollLockOff : EvScrollLockPressed
    }
:::

### User journey example

The user journey diagram describes what steps are required to complete certain higher level action or task. 

```
:::mermaid
journey
    title Home office day
    section Go to work
      Wake up: 1: Me, Dog
      Take shower: 2: Me
      Go downstairs: 3: Me, Dog
      Make coffee: 4: Me
      Have a breakfast: 5: Me, Dog
      Go upstairs: 3: Me, Dog
      Do work: 1: Me, Dog
    section Go home
      Go downstairs: 3: Me, Dog
      Sit down: 5: Me
:::
```

:::mermaid
journey
    title Home office day
    section Go to work
      Wake up: 1: Me, Dog
      Take shower: 2: Me
      Go downstairs: 3: Me, Dog
      Make coffee: 4: Me
      Have a breakfast: 5: Me, Dog
      Go upstairs: 3: Me, Dog
      Do work: 1: Me, Dog
    section Go home
      Go downstairs: 3: Me, Dog
      Sit down: 5: Me
:::

### Pie chart example

The pie chart diagram is used to visualize the percentages in a circled graph. 

```
:::mermaid
pie title Fishermans in countries
    "Norway" : 684
    "Sweeden" : 234
    "Switzerland" : 10
:::
```

:::mermaid
pie title Fishermans in countries
    "Norway" : 684
    "Sweeden" : 234
    "Switzerland" : 10
:::

### Requirements diagram example

The requirements diagram visualizes the requirements and their connections.

```
:::mermaid
requirementDiagram
    requirement development_req {
    id: 1
    text: requirements spec.
    risk: medium
    verifymethod: test
    }
    element test_suite {
    type: manual test
    }
    test_suite - verifies -> development_req
:::
```

requirementDiagram
    requirement development_req {
    id: 1
    text: requirements spec.
    risk: medium
    verifymethod: test
    }
    element test_suite {
    type: manual test
    }
    test_suite - verifies -> development_req
:::

### Add a collapsible section

To add a collapsible section in a wiki page, use the following syntax:

```html
# A collapsible section with markdown
<details>
  <summary>Click to expand!</summary>
  
  ## Heading
  1. A numbered
  2. list
     * With some
     * Sub bullets
</details>
```

## A collapsible section with markdown
<details>
  <summary>Click to expand!</summary>
  
  ## Heading
  1. A numbered
  2. list
     * With some
     * Sub bullets
</details>

Make sure to add an empty line in the following areas:

- after the closing `</summary>` tag, otherwise the markdown/code blocks don't show correctly
- after the closing `</details>` tag if you have multiple collapsible sections

## Embed videos in a wiki page

To embed videos from YouTube and Microsoft Streams in a wiki page, use the following syntax:

```markdown
::: video
> [!VIDEO https://www.youtube.com/embed/_EXAMPLE_]
:::
```
The iframe corresponds to the embedding iframe block of either a YouTube or Microsoft Streams video.

The ending ":::" is required to prevent a break in the page.

## Embed Azure Boards query results in wiki

To embed Azure Boards query results in a wiki page as a table, use the following syntax:

> [!div class="tabbedCodeSnippets"]
```Query syntax
::: query-table <queryid>
:::
```

For example:

:::
query-table 6ff7777e-8ca5-4f04-a7f6-9e63737dddf7
:::

You can also use the **toolbar** and the **query selector** to embed the query results in a wiki page.

For more information about how to copy the query URL, which provides a GUID for the query, see [Email query items or share query URL](../../boards/queries/view-run-query.md#email-query-items-or-share-a-query-url).

## @mention users and groups

To @mention users or groups in wiki, key in "@" in the wiki editor. This @mention opens autosuggest from which you can mention users or groups to get notified by email.

You can also select **@mention** from the edit toolbar.

When you edit pages directly in code, use the following pattern, `@<{identity-guid}>`.

## View page visits for wiki pages

Automatically, you see an aggregated count of page visits for the last 30 days on every page. We define a page visit as a page view by a given user in a 15-minute interval.

Use the batch API `pagesBatch` to see the daily quantity of visits to all pages in a paginated way. They aren't sorted by number of visits, however. For data over 30 days old, you can get all page visits using the rest API. Sort these pages based on the number of visits to get the top 100. You can store these visits in a dashboard or database.

## Link to work items from a wiki page

Enter the pound sign (`#`), and then enter a work item ID.

## Use HTML tags in wiki pages

In wiki pages, you can also create rich content using HTML tags.

> <b><ins>TIP</ins></b>
> You can nest Markdown within your HTML, but you must include a blank line between the HTML element and the markdown.


 ```HTML
<p>
 
  [A Markdown link](https://microsoft.com) 
</p>
```

**Example - Embedded video**

```HTML
<video src="path of the video file" width=400 controls>
</video>
```

```HTML
<video src="https://sec.ch9.ms/ch9/7247/7c8ddc1a-348b-4ba9-ab61-51fded6e7247/vstswiki_high.mp4" width=400 controls>
</video>
```

**Example - Rich text format**

```HTML
<p>This text needs to <del>strikethrough</del> <ins>since it is redundant</ins>!</p>
<p><tt>This text is teletype text.</tt></p>
<font color="blue">Colored text</font>
<center>This text is center-aligned.</center>
<p>This text contains <sup>superscript</sup> text.</p>
<p>This text contains <sub>subscript</sub> text.</p>
<p>The project status is <span style="color:green;font-weight:bold">GREEN</span> even though the bug count / developer may be in <span style="color:red;font-weight:bold">red.</span> - Capability of span
<p><small>Disclaimer: Wiki also supports showing small text</small></p>
<p><big>Bigger text</big></p>
```

**Result:**

<p>This text needs to <del>strikethrough</del> <ins>since it is redundant</ins>!</p>
<p><tt>This text is teletype text.</tt></p>
<font color="blue">Colored text</font>
<center>This text is center-aligned.</center>
<p>This text contains <sup>superscript</sup> text.</p>
<p>This text contains <sub>subscript</sub> text.</p>
<p>The project status is <span style="color:green;font-weight:bold">GREEN</span> even though the bug count / developer may be in <span style="color:red;font-weight:bold">red.</span> - Capability of span
<p><small>Disclaimer: Wiki also supports showing small text</small></p>
<p><big>Bigger text</big></p>

<!---
<p>This text needs to <del>strikethrough</del> <ins>since it is redundant</ins>!</p>
<p><tt>This text is teletype text.</tt></p>
<font color="blue">Colored text</font>
<center>This text is center-aligned.</center>
<p>This text contains <sup>superscript</sup> text.</p>
<p>This text contains <sub>subscript</sub> text.</p>
<p>The project status is <span style="color:green;font-weight:bold">GREEN</span> even though the bug count / developer may be in <span style="color:red;font-weight:bold">red.</span> - Capability of span
<p><small>Disclaimer: Wiki also supports showing small text</small></p>
<p><big>Bigger text</big></p>
-->

## Related articles  
