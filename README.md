This theme is developed for docs.aspose.com. 
It is based on Docsy https://www.docsy.dev/ and Hugo Book https://github.com/alex-shpak/hugo-book Hugo themes.

# F.A.Q.

## How to setup theme

1. First of all you need to install npm dependencies:
    
    ``` 
        sudo npm install -D --save autoprefixer
        sudo npm install -D --save postcss-cli 
    ```

2. Start Hugo server
    ```
        hugo server -D
    ```

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
