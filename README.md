This theme is developed for docs.aspose.com. 
It is based on Docsy https://www.docsy.dev/ and Hugo Book https://github.com/alex-shpak/hugo-book Hugo themes.

- [F.A.Q.](#faq)
- [How to setup theme](#how-to-setup-theme)
  * [1. First of all you need to install npm dependencies:](#1-first-of-all-you-need-to-install-npm-dependencies-)
  * [2. Start Hugo server](#2-start-hugo-server)
  * [3. How To Test On Different Domains?](#3-how-to-test-on-different-domains-)
- [Config.toml Params](#configtoml-params)
- [Page Variables](#page-variables)
- [Shortcodes — use in **.md** files](#shortcodes---use-in---md---files)
  * [Products Landing Pages Shortocdes](#products-landing-pages-shortocdes)


## F.A.Q.

## How to setup theme

### 1. First of all you need to install npm dependencies:
    
    ``` 
        sudo npm install -D --save autoprefixer
        sudo npm install -D --save postcss-cli 
    ```

### 2. Start Hugo server
    ```
        hugo server -D
    ```

### 3. How To Test On Different Domains?

You need to use the following comand in the main Hugo directory:

        hugo server -c <directory path> -b <base url (e.g. products.aspose.com)>

**Example:**

        hugo server -c content/Aspose.Slides-Landing/ -b products.aspose.com

*[**directory path**]* — this is path of content. E.g. path to Aspose.Email documentation folder.

*[**base url**]* — Type the domain or website you want to test. To see the website just use your 'localhost' or IP of local hugo server. Hugo accepts theme depending on the URL. Hugo uses "aspose.com" URL if this parameter is not set.

## Config.toml Params

1. **topbar_search_active** — Shows/Hide topbar search field.

 
## Page Variables
1. **showChildPages: true** - Shows the list of child pages in the bottom of the current page.


## Shortcodes — use in **.md** files  
1. ``` {< emoticons/tick >}} ``` — to insert emoticon-tick.
2. ``` {{< emoticons/cross >}} ``` — to insert emoticon-cross.
3. 
``` 
    {{< expand-list title="Title of an expand list" >}}
    Example of the data which you want to insert in expand list.
    {{< /expand-list >}}
```

**You should specify "title" attribute of the expand list.**

This shortcode adds tag which specifies additional details that the user can open and close on demand.
This shortcode is used to create an interactive widget that the user can open and close. By default, the widget is closed. When open, it expands and displays the content within.

4. ``` {{< list-of-articles-in-this-section >}} ``` — adds list of **links to other articles in the current section**. Current section is highlighted.

5. ``` {{< list-children-pages >}} ``` — adds list of **links to children articles** for the current section.

6. 
```
    {{< nosnippet >}}
        Any text or tags, which you want to hide from appearing in Google snippets.
    {{< /nosnippet >}}
```

7. **Tab shortocde:**

*tabTotal* parameter is optional, the shortcode will work without it either.
```
{< tabs [tabTotal="3"] tabID="uniqueid" tabName1="MacOS" tabName2="Linux" tabName3="Windows" >}}
    {{< tab tabNum="1" >}}

    You can use **Markdown** *formatting* in tabs.
    Some code example.

    {{< /tab >}}

    {{< tab tabNum="2" >}}

    # Linux

    This is tab **Linux** content.

    {{< /tab >}}

    {{< tab tabNum="3" >}}

    # Windows

    This is tab **Windows** content.

    {{< /tab >}}
{{< /tabs >}}
```

8. **Run Shortcode**

Run Shortcode adds a button. When you click on it you will be redirected to the page that you pass as a *href* parameter.

For example, you can use it under the code block to refer to Swagger documentation.

**Notice, this shortcode only redirect to another page!**

```
    {{< run href="https://www.aspose.com" >}}
```

### Products Landing Pages Shortocdes




1.  **blocks/products/pf/upper-banner**

This shortocde insers an upper banner which includes title and sub-title to the page.

* **h1** — H1 title on the banner, e.g. *h1=".NET API for PowerPoint File Formats"*
* **h2** — Subtitle (H2) which is displaying on the banner, e.g. *h2="Read, write, modify, merge, clone, *protect & convert PowerPoint and OpenOffice presentations in .NET C# without any external software."
* **logoImageSrc** — The path of logo image, e.g. *logoImageSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/header/aspose_slides-for-net.png"*
* **pfName** — Product Family Name, eg. *pfName="Aspose.Slides"*
* **subTitlepfName** — Subtitle for product family product, eg. subTitlepfName="for.Net"
* **downloadUrl** — The download link, which is used in menu, e.g. *downloadUrl="https://downloads.aspose.com/slides/net"*
* **[tryOnlineUrl]** — **Optional Parameter**  adds "Try Online" button to the header. Pass the link in this parameter. *tryOnlineUrl="https://products.aspose.app/slides/family"*

```
{{< blocks/products/pf/upper-banner h1=".NET API for PowerPoint File Formats" h2="Read, write, modify, merge, clone, protect & convert PowerPoint and OpenOffice presentations in .NET C# without any external software." logoImageSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/header/aspose_slides-for-net.png" pfName="Aspose.Slides" subTitlepfName="for.Net" downloadUrl="https://downloads.aspose.com/slides/net" tryOnlineUrl="https://products.aspose.app/slides/family" >}}
```

2. **blocks/products/pf/main-container**

Within this shortcode must be placed all content shortcodes of the page.

**The following parameters are used in **sub-menu** shortcode on product pages.**

* **pfName** — Product Family Name, eg. pfName="Aspose.Slides"

* **subTitlepfName** — Subtitle for product family product, eg. subTitlepfName="for.Net"


```
    {{< blocks/products/pf/main-container pfName="Aspose.Slides" subTitlepfName="for.Net" >}}
        ....
    {{< /blocks/products/pf/main-container >}}
```

3. **blocks/products/pf/main-wrap-class** Adding block with "pf-landing-page-com" class. 

**Important: Use this shortocde on product families landing pages and on product pages. For example, https://products.aspose.com/slides and https://products.aspose.com/slides/net**


4. **blocks/products/pf/product-card-row**

This shortcode must contain product cards.

* **title** — the title of product row, e.g. *title="Aspose.Slides On Premise APIs Include"* 

```
    {{< blocks/products/pf/product-card-row title="Aspose.Slides On Premise APIs Include" >}}
    ...
    {{< blocks/products/pf/product >}}
        ...
    {{< /blocks/products/pf/product >}}
    ...
    ...
    ...  
    {{< /blocks/products/pf/product-card-row >}}

```

5. **blocks/products/pf/product-card-row**

This shortcode is used for displaying a single product card

* **pfName** — the upper string of product’s title. Sometimes includes additional words, as in the example. E.g. *pfName="Aspose.Slides for"*
* **title** — this is a title of product, usually used as SDK’s name, e.g. *title=".NET"*
* **imgSrc** - link to the image/icon of the product card, e.g. *imgSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-net.png"*
* **productLink** - a link which product card leads to, e.g. *productLink="https://products.aspose.com/slides/net"*

* **In the shortcode, you should write a description of the product.**

```
    {{< blocks/products/pf/product pfName="Aspose.Slides for" title=".NET" imgSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-net.png" productLink="https://products.aspose.com/slides/net" >}}
    Target Windows Forms, ASP.NET, WPF, WCF or any type of application based on .NET Framework 2.0 or later.
    {{< /blocks/products/pf/product >}}
```

6. **{{< blocks/products/pf/support-learning-resources >}}** — Adds support learning resources block.

Use this shortcode to add **support learning resources** block.

There are 3 columns. 


```
    {{< blocks/products/pf/support-learning-resources >}}
        {{< blocks/products/pf/slr-tab tabTitle="Learning Resources" tabId="resources" >}}
        {{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.com/slides/" >}}
        {{< blocks/products/pf/slr-element name="Source Code" href="https://github.com/aspose-slides?tab=repositories" >}}
        {{< blocks/products/pf/slr-element name="API References" href="https://apireference.aspose.com/" >}}
        {{< blocks/products/pf/slr-element name="Tutorial Videos" href="https://www.youtube.com/user/asposevideo" >}}
        {{< /blocks/products/pf/slr-tab >}}

        {{< blocks/products/pf/slr-tab tabTitle="Product Support" tabId="support" >}}
        {{< blocks/products/pf/slr-element name="Free Support" href="https://docs.aspose.com/slides/" >}}
        {{< blocks/products/pf/slr-element name="Paid Support" href="https://helpdesk.aspose.com/" >}}
        {{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.com/category/slides/" >}}
        {{< /blocks/products/pf/slr-tab >}}

        {{< blocks/products/pf/slr-tab tabTitle="Why Aspose.Slides Product Family?" tabId="success-stories" >}}
        {{< blocks/products/pf/slr-element name="Customers List" href="https://company.aspose.com/customers" >}}
        {{< blocks/products/pf/slr-element name="Success Stories" href="https://company.aspose.com/customers/success-stories/aspose-slides" >}}
        {{< /blocks/products/pf/slr-tab >}}
    {{< /blocks/products/pf/support-learning-resources >}}

```

6.1. **blocks/products/pf/slr-tab** — initialize a column.  

```

{{< blocks/products/pf/slr-tab tabTitle="Learning Resources" tabId="resources" >}}

```

* **tabTitle** — Name of column, e.g. *tabTitle="Learning Resources"*
* **tabId** — id using for anchor, e.g. *tabId="resources"*

|  Column Name | tabId  |
|----------|:-------------:|
| Learning Resources | resources |
| Product Support | support |
| Why ... Product Family? | success-stories |


6.2. **blocks/products/pf/slr-element** — child element of *slr-tab* shortcode.

* **name** — name of link, e.g. *name="Documentation"*
* **href** — the link, e.g. *href="https://docs.aspose.com/slides/"*

```
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.com/slides/" >}}
```
___

7. **download-section** — Adds downloading section

* **downloadFreeTrialLink** — download free trial link, e.g. *downloadFreeTrialLink="https://downloads.aspose.com/slides"*
* **pricingInformationLink** — link to the pricing information link, e.g. *pricingInformationLink="https://purchase.aspose.com/pricing/slides"*

```
{{< blocks/products/pf/download-section downloadFreeTrialLink="https://downloads.aspose.com/slides" pricingInformationLink="https://purchase.aspose.com/pricing/slides" >}}
```

8. **blocks/products/pf/sub-menu** — Adds sub menu on products pages.

* **logoImageSrc** — logo of product, e.g. *logoImageSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-net.png"*
* **liveDemosLink** — Live demos Link, e.g. *liveDemosLink="https://products.aspose.app/slides/family"*
* **PricingLink** — Pricing Link, e.g. *PricingLink="https://purchase.aspose.com/pricing/slides/net"*
* **buyLink** — Learn Link , e.g. *buyLink="https://purchase.aspose.com"*
* **docsLink** — Link to Documentation , e.g. *docsLink="https://docs.aspose.com/slides/net/"*
* **instalationsDocsLink** — Link to the instalation Guide, e.g. *instalationsDocsLink="https://docs.aspose.com/slides/net/installation/"*
* **nugetLink** — Link to the nuget repository, e.g. *nugetLink="https://www.nuget.org/packages/Aspose.Slides.NET/"*
* **nugetPackageName** —  e.g. *nugetPackageName="Aspose.Slides.NET"*

```
{{< blocks/products/pf/sub-menu logoImageSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-net.png" liveDemosLink="https://products.aspose.app/slides/family" PricingLink="https://purchase.aspose.com/pricing/slides/net" buyLink="https://purchase.aspose.com" docsLink="https://docs.aspose.com/slides/net/" instalationsDocsLink="https://docs.aspose.com/slides/net/installation/" nugetLink="https://www.nuget.org/packages/Aspose.Slides.NET/" nugetPackageName="Aspose.Slides.NET" >}}
```

9. **blocks/products/pf/tab-conent** – Adds tetual tab on product page.

```
{{< blocks/products/pf/tab-conent >}}
    <p>Aspose.Slides for .NET is a Presentation Processing API for PowerPoint and OpenOffice formats.
    Aspose.Slides enables applications to read, write, protect, modify and convert presentations in .NET C#.
    Manage presentation text, shapes, charts, tables &amp; animations, add audio &amp; video to slides,
    preview slides.</p>
    <p>Aspose.Slides for .NET supports all of the popular presentation formats. Use C# to merge, split, clone
    and reuse multiple PowerPoint presentations, templates and slides in numerous ways. Moreover, API offers
    a number of advanced features such as printing on physical printers and rendering presentations to
    fixed-layout formats, HTML &amp; images.</p>
    <p>Aspose.Slides for .NET is a standalone API and does not require Microsoft PowerPoint or any other
    additional software or library.</p>
{{< /blocks/products/pf/tab-conent >}}
```

10. **blocks/products/pf/testimonials** Adding a block with quotes

This shortcode is used for adding quotes on the page.

To add a quote use **blocks/products/pf/testimonials-quote** shortocode.

*You can add as many quotes as you need. They will be automatically organized in the quote block.*

```
    {{< blocks/products/pf/testimonials title="What People Are Saying" subTitle="Don't just take our word for it. See what&nbsp;users have to say about Aspose.Slides." >}}

    {{< blocks/products/pf/testimonials-quote >}}
    We have found Aspose.Slides to be easy to use and to work nicely on our ASP.Net servers. We have found they fill an important need for dynamically generating files to expand our reach beyond the traditional web application.<em>Rick Joi | Workplace Dynamics, UK</em>
    {{< /blocks/products/pf/testimonials-quote >}}
    {{< blocks/products/pf/testimonials-quote >}}
    The product worked as advertised, the documentation was easy to follow, and the support forums were all the help we needed. The final solution that we deployed has exceeded our initial expectations by a great deal.<em>Bruce Brien | Stratascope Inc, USA</em>
    {{< /blocks/products/pf/testimonials-quote >}}

    {{< /blocks/products/pf/testimonials >}}
```

11. **blocks/products/pf/offers-section** and **blocks/products/pf/offers-section-item**

**blocks/products/pf/offers-section** — Adds offers section.

* **pfName** — e.g. *pfName="Aspose.Slides"*

**blocks/products/pf/offers-section-item** — An item in offers section.

* **link** — e.g. *link="/slides/java"*
* **imgSrc** — e.g. *imgSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-java.png"*
* **sdkName** — e.g. *sdkName="Java"*


```
{{< blocks/products/pf/offers-section pfName="Aspose.Slides" >}}

    {{< blocks/products/pf/offers-section-item link="/slides/java" imgSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-java.png" sdkName="Java" >}}

    {{< blocks/products/pf/offers-section-item link="/slides/cpp" imgSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-cpp.png" sdkName="C++" >}}
    ...
    ...
    ...
{{< /blocks/products/pf/offers-section >}}
```

12. **blocks/products/products-backtop-button** Adding a scroll-to-the-top button.

Add this at the end of .md page to add an autoscroll button.
```
   {{< blocks/products/products-backtop-button >}} 
```

13. **blocks/products/pf/carousel** Adding diagram block as carousel

```
    {{< blocks/products/pf/carousel >}}

    {{< blocks/products/pf/carousel-item h3="At A Glance" escription="Aspose.Slides for .NET supports the popular [presentation formats](https://docs.aspose.com/slides/net/supported-file-formats/) and export formats listed below." >}}
    <div class="diagram1 d1-net">
    <div class="d1-row">
        <div class="d1-col d1-left">
        ...
    {{< /blocks/products/pf/carousel-item >}}

    {{< /blocks/products/pf/carousel >}}
```

#### Shortcodes for auto-generated pages

Shortcodes that are used on products’ auto-generated pages are the same as on product pages, but extended with additional parameters.

1.  **blocks/products/pf/upper-banner**

This shortocde insers an upper banner which includes title and sub-title to the page.

* **h1** — H1 title on the banner, e.g. *h1=".NET API for PowerPoint File Formats"*
* **h2** — Subtitle (H2) which is displaying on the banner, e.g. *h2="Read, write, modify, merge, clone, *protect & convert PowerPoint and OpenOffice presentations in .NET C# without any external software."
* **logoImageSrc** — The path of logo image, e.g. *logoImageSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/header/aspose_slides-for-net.png"*
* **sourceAdditionalConversionTag** — Defines the text for the initial file format. It uses to make a logo circle of file formats, e.g. *sourceAdditionalConversionTag="3DS"*
* **additionalConversionTag** — Defines the text for the result file format. A big file formats text which appears within logo in the banner, e.g. *additionalConversionTag="GLTF"*
* **pfName** — Product Family Name, eg. *pfName="Aspose.Slides"*
* **subTitlepfName** — Subtitle for product family product, eg. subTitlepfName="for.Net"
* **downloadUrl** — The download link, which is used in menu, e.g. *downloadUrl="https://downloads.aspose.com/slides/net"*

```
{{< blocks/products/pf/upper-banner h1="Convert 3DS to GLTF via Java" h2="Java library to render 3DS as GLTF without any 3D modeling software." logoImageSrc="https://www.aspose.com/templates/aspose/App_Themes/V3/images/3d/272x272/aspose_3d-for-java.png" sourceAdditionalConversionTag="3DS" additionalConversionTag="GLTF" pfName="Aspose.3D" subTitlepfName="for Java" downloadUrl="https://downloads.aspose.com/3d/java" >}}
```

2. **blocks/products/pf/sub-menu**

**This shortcode is under development.**

* **autoGeneratedVersion** — **Important** to set TRUE on auto-generated pages, e.g. *autoGeneratedVersion="true"*
* **[directDownloadLink]** — **Optional Parameter** If it’s set, "Download" button works like a direct link , e.g. *directDownloadLink="aspose.com"*
* **logoImageSrc** — logo of product, e.g. *logoImageSrc="https://www.aspose.cloud/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-net.png"*
* **apiHomeLink** — API Home Link, e.g. *apiHomeLink="/3d/java"*
* **codeSamplesLink** — Code Samples Link, e.g. *codeSamplesLink="https://github.com/aspose-3d"*
* **liveDemosLink** — Live demos Link, e.g. *liveDemosLink="https://products.aspose.app/slides/family"*
* **docsLink** — Link to Documentation , e.g. *docsLink="https://docs.aspose.com/slides/net/"*
* **instalationsDocsLink** — Link to Installation guide. This link appears when you click on "Download" button **inside of pop up**, e.g. *instalationsDocsLink="https://docs.aspose.com/3d/java/installation"*
* **mavenRepoLink** — Link to Maven repository guide. This link appears when you click on "Download" button **inside of pop up**, e.g. *mavenRepoLink="https://repository.aspose.com/webapp/#/artifacts/browse/tree/General/repo/com/aspose/aspose-3d"*

```
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.com/templates/aspose/App_Themes/V3/images/3d/272x272/aspose_3d-for-java.png" apiHomeLink="/3d/java" codeSamplesLink="https://github.com/aspose-3d" liveDemosLink="https://products.aspose.app/3d/family" docsLink="https://docs.aspose.com/3d/java/"
instalationsDocsLink="https://docs.aspose.com/3d/java/installation" mavenRepoLink="https://repository.aspose.com/webapp/#/artifacts/browse/tree/General/repo/com/aspose/aspose-3d" >}}
```

**3 scenarios of using sub-menu shortcode with "Download" Button.** 

"Download" Button can act as Direct link, pop up with Nuget code example and pop up with Maven Repo Link.

1. "Download" button works as Direct link:

You need to set *directDownloadLink* parameter.

```
{{< blocks/products/pf/sub-menu directDownloadLink="aspose.com" autoGeneratedVersion="true" logoImageSrc="https://www.aspose.com/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-cpp.png" apiHomeLink="https://products.aspose.com/slides/cpp" codeSamplesLink="https://github.com/aspose-slides" liveDemosLink="https://products.aspose.app/slides/family" docsLink="https://docs.aspose.com/slides/cpp" >}}
```

2. "Download" button works as pop up with Nuget Code Example: 

```
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.com/templates/aspose/App_Themes/V3/images/slides/272x272/aspose_slides-for-cpp.png" apiHomeLink="https://products.aspose.com/slides/cpp" codeSamplesLink="https://github.com/aspose-slides" liveDemosLink="https://products.aspose.app/slides/family" docsLink="https://docs.aspose.com/slides/cpp" instalationsDocsLink="https://docs.aspose.com/slides/cpp/" nugetLink="https://www.nuget.org/packages/aspose.slides" nugetPackageName="Aspose.Slides.Cpp" >}}
```

3. "Download" button works as pop up with plain text and Maven Repo Link: 

```
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.com/templates/aspose/App_Themes/V3/images/3d/272x272/aspose_3d-for-java.png" apiHomeLink="/3d/java" codeSamplesLink="https://github.com/aspose-3d" liveDemosLink="https://products.aspose.app/3d/family" docsLink="https://docs.aspose.com/3d/java/"
instalationsDocsLink="https://docs.aspose.com/3d/java/installation" mavenRepoLink="https://repository.aspose.com/webapp/#/artifacts/browse/tree/General/repo/com/aspose/aspose-3d" >}}
```

2. **blocks/products/pf/agp/content** 

This shortocde insers a block with text within.

* **h2** — Title of this section, eg. h2="About Aspose.3D for Java API"

```
{{< blocks/products/pf/agp/content h2="About Aspose.3D for Java API">}}
    Aspose.3D is a CAD and Gameware API to load, modify and convert 3D files. API is a standalone and does not require any any 3D modeling or rendering software...
{{< /blocks/products/pf/agp/content >}}
```

3. **blocks/products/pf/agp/feature-section**

This shortcode is used to insert a feature section on auto-generated page.
It must include th following shortcodes:

    1. **blocks/products/pf/agp/feature-section-col**
    2. Code example as pure HTML.


4. **blocks/products/pf/agp/feature-section-col**

* **title** — Title of this section, eg. *title="Steps to Convert 3DS to GLTF via Java"*

4.1. **blocks/products/pf/agp/text**

**To use markdown formatting you should use % symbol with this shortcode.**

This shortcode inserts text into a feature column.

4.2. **blocks/products/pf/agp/list**

Adds a list. 
**It’s important to set *style* parameter. It can be set to 'ol' or 'ul' simmilar to HTML tags**

* **style** — Defines a style of a list, eg. *style="ol"*

4.3. **blocks/products/pf/agp/list-el**

This shortcode adds element of a list.

* **text** — Sets text of list element, eg. *text="Load 3DS file via the constructor of Scene class"*

**EXAMPLE OF USE:**

```
{{< blocks/products/pf/agp/feature-section-col title="Steps to Convert 3DS to GLTF via Java" >}}

{{% blocks/products/pf/agp/text %}}
You need [aspose.3d.jar](https://downloads.aspose.com/3d/java) referenced in your project to execute the following workflow.
{{% /blocks/products/pf/agp/text %}}

{{< blocks/products/pf/agp/list style="ol" >}}
{{< blocks/products/pf/agp/list-el text="Load 3DS file via the constructor of Scene class">}}
{{< blocks/products/pf/agp/list-el text="Create an instance of GltfSaveOptions">}}
{{< blocks/products/pf/agp/list-el text="CSet GLTF specific properties for advanced conversion">}}
{{< blocks/products/pf/agp/list-el text="Call Scene.save method">}}
{{< blocks/products/pf/agp/list-el text="Pass the output path with GLTF file extension & object of GltfSaveOptions">}}
{{< /blocks/products/pf/agp/list >}}

{{< /blocks/products/pf/agp/feature-section-col >}}
```

5. **blocks/products/pf/agp/about-file-section**

Adds section with file formats information.

6. **blocks/products/pf/agp/demobox**

This shortcode adds information about the current app.

* **sectionTitle** — title of the section , eg. *sectionTitle="Free App to Convert 3DS to GLTF"*
* **sectionDescription** — additional text (*It can be in markdown format*)  , eg. *sectionDescription="Check our live demos for [3DS to GLTF conversion](https://products.aspose.app/3d/conversion/3ds-to-gltf) with following benefits."*

6.1. **blocks/products/pf/agp/democard**

Adds a card with an advantage of using the app.

* **icon** — favicon which used on a card , eg. *icon="fa-cogs"*
* **text** — text on a card , eg. *text="No need to write or compile code"*

6.2. **blocks/products/pf/agp/about-file-text**

Adds brief information about the file format. Paste the brief information inside this shortcode.

* **fileFormat** — file format’s name , eg. *fileFormat="3DS"*
* **readMoreLink** — A link for "Read More" button, eg. *readMoreLink="https://docs.fileformat.com/3d/3ds/"*

**EXAMPLE OF USE:**

```
{{< blocks/products/pf/agp/about-file-section >}}

    {{< blocks/products/pf/agp/demobox sectionTitle="Free App to Convert 3DS to GLTF" sectionDescription="Check our live demos for [3DS to GLTF conversion](https://products.aspose.app/3d/conversion/3ds-to-gltf) with following benefits." >}}
        {{< blocks/products/pf/agp/democard icon="fa-cogs" text="No need to download or setup anything" >}}
        {{< blocks/products/pf/agp/democard icon="fa-edit" text="No need to write or compile code" >}}
        {{< blocks/products/pf/agp/democard icon="fa-file-text" text="Just upload 3DS file and hit the \"Convert\" button" >}}
        {{< blocks/products/pf/agp/democard icon="fa-download" text="Download the resultant GLTF file immediately" >}}
    {{< /blocks/products/pf/agp/demobox >}}

    {{< blocks/products/pf/agp/about-file-text fileFormat="3DS" readMoreLink="https://docs.fileformat.com/3d/3ds/" >}}
    A file with 3DS extension represents 3D Sudio (DOS)...
    {{< /blocks/products/pf/agp/about-file-text >}}

    {{< blocks/products/pf/agp/about-file-text fileFormat="GLTF" readMoreLink="https://docs.fileformat.com/3d/gltf/" >}}
    glTF (GL Transmission Format) is a 3D file format that store...
    {{< /blocks/products/pf/agp/about-file-text >}}

{{< /blocks/products/pf/agp/about-file-section >}}

```

7. **blocks/products/pf/agp/faq** Adding FAQ section

```
    {{< blocks/products/pf/agp/faq imgSrc="https://www.aspose.com/templates/brand/images/slides/aspose_slides-brand.png" >}}

    {{< blocks/products/pf/agp/faq-item question="How can I get the Aspose.Slides.Cpp DLL?" answer="Simply execute *_Install-Package Aspose.Slides.Cpp_* in Package Manager console of Visual Studio or get it from [Downloads](https://downloads.aspose.com/slides/cpp) in ZIP format for both Windows & Linux." >}}
    .
    .
    .

    {{< /blocks/products/pf/agp/faq >}}
```
