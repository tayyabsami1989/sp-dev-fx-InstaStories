---
page_type: sample
products:
- office-sp
languages:
- javascript
- typescript
extensions:
  contentType: samples
  technologies:
  - SharePoint Framework
  platforms:
  - react
  createdDate: 8/1/2017 12:00:00 AM
---
# Content Query Web Part (Compatible with On-Premises SharePoint versions)

## Summary

> NOTE: This web part was built with an earlier version of SPFx which is compatible with on-premises versions of SharePoint. If you wish, you can use the [newer version of this web part](../react-content-query-online/README.md) which is compatible with SharePoint Online only.

The `React Content Query Web Part` is a modern version of the good old `Content by Query Web Part` that was introduced in SharePoint 2007. Built for *SharePoint 2016* and *Office 365*, this modern version is built against the new **SharePoint Framework (SPFx)** and uses the latest *Web Stack* practices. While the original Web Part was based on a `XSLT` templating engine, this *React* Web Part is based on the well known [Handlebars templating engine](http://handlebarsjs.com), which empowers users to create simple, yet powerful `HTML` templates for rendering the queried content. This new version also lets the user query `any site collections` which resides on the same domain url, add `unlimited filters`, query *DateTime* fields to the `nearest minute` rather than being limited to a day, and much more.

<img src="Misc/toolpart.gif" />


## Compatibility

| :warning: Important          |
|:---------------------------|
| Every SPFx version is only compatible with specific version(s) of Node.js. In order to be able to build this sample, please ensure that the version of Node on your workstation matches one of the versions listed in this section. This sample will not work on a different version of Node.|
|Refer to <https://aka.ms/spfx-matrix> for more information on SPFx compatibility.   |

![SPFx 1.1.0](https://img.shields.io/badge/SPFx-1.1.0-green.svg)
![Node.js v6](https://img.shields.io/badge/Node.js-v6-green.svg) 
![Compatible with SharePoint Online](https://img.shields.io/badge/SharePoint%20Online-Compatible-green.svg)
![Compatible SharePoint 2019](https://img.shields.io/badge/SharePoint%20Server%202019-Compatible-green.svg)
![Compatible with SharePoint 2016 (Feature Pack 2)](https://img.shields.io/badge/SharePoint%20Server%202016%20(Feature%20Pack%202)-Compatible-green.svg)
![Local Workbench Compatible](https://img.shields.io/badge/Local%20Workbench-Compatible-green.svg)
![Hosted Workbench Compatible](https://img.shields.io/badge/Hosted%20Workbench-Compatible-green.svg)
![Compatible with Remote Containers](https://img.shields.io/badge/Remote%20Containers-Compatible-green.svg)


## Applies to

* [SharePoint Framework Developer](https://learn.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview)
* [Office 365 developer tenant](https://learn.microsoft.com/sharepoint/dev/spfx/set-up-your-developer-tenant)

## Solution

Solution|Authors
--------|-----------
react-content-query-webpart|Simon-Pierre Plante

## Version history

Version|Date|Comments
-------|----|--------
1.0.0|May 04, 2017|Initial release
1.0.1|July 23rd 15, 2017|Updated to GA Version
1.0.3|August 12, 2017|Added external scripts functionality
1.0.4|August 31, 2017|Fixed a bug where tenant sites/subsites were missing from the **Web Url** dropdown
1.0.5|September 1st, 2017|Added a **Site Url** parameter next to the **Web Url** parameter in order to narrow down the results
1.0.6|September 19, 2017|Upgraded to SharePoint drop 1.2.0 and added the site url and web url pre-selection when adding the web part for the first time on a page. Also fixed a bug with fields that had spaces in their internal names (automatically replaced with `_x0020_` by SharePoint).
1.0.7|November 17, 2017|Reverted to drop 1.1.0 in order to keep compatibility for SP2016 on-premise
1.0.8|March 17, 2018|Updated to store the selected list using its ID instead of its title, so the web part keeps working if the list title gets updated.
1.0.9|March 28, 2018|Added a switch to enable the web part to apply it's query recursively within folders, and fixed a bug where webs could sometimes not appear under the web url dropdown
1.0.10|April 5, 2018|Fixed a bug where the webs of the selected site collection were not being loaded correctly for particular tenants
1.0.11|May 22, 2018|Fixed a bug causing filters to loose their sort order in IE

## Disclaimer

**THIS CODE IS PROVIDED *AS IS* WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**

## Features

### Cross site collection

The web part uses the search in order to get all sites under the current domain, which makes it possible to query not only sub-sites but other site collections and their sub-sites as well. By default, the current site collection and the current web on which the user is adding the web part will be pre-selected automatically.

<img src="Misc/allsites_v2.gif" />
<br>

### Unlimited filters

The user isn't limited to 3 filters anymore, an unlimited amount of filters can be added to narrow down your query

<img src="Misc/filters.gif" width="500" />
<br>

### Improved date time filters

It is now possible to include time validation when querying date fields, giving the ability to be more precise when it comes to querying items against date values.

<img src="Misc/datetime.gif" width="500" />
<br>

### Handlebars templating engine

Enjoy a simple, yet powerfull html-based templating engine for rendering your results. The web part even generates a default Handlebars template for you based on the view fields you have selected during the configuration! 

For advanced users, more than 150 Handlebars block helpers are available by default within the user defined template. For a list of all block helpers, see [handlebars-helpers](https://github.com/helpers/handlebars-helpers#helpers) 
<br>

### Built-in template editor

Edit your Handlebars template directly within the toolpane using a built-in [code editor](https://ace.c9.io/) which provides code folding, syntax highlighting, line wrapping, indentation and many more features to the tip of your fingers.

<img src="Misc/editor.gif" />
<br>

### Include your own external scripts and/or block helpers!

You can now specify your own external scripts that needs to be loaded either **before** or **after** rendering the Handlebars template.

<img src="Misc/externalScripts.png" />

External scripts can be used to include either libraries such as *jQuery*, or even *custom logic scripts* that can leverage the exposed **onPrerender** and **onPostRender** methods for advanced functionnalities. 

## Getting Started

### Adding the web part to your page

To add the `React Content Query Web Part` to your site page you have two options : 
- Either clone this repository, build the project yourself and connect it to SharePoint (see [officedev documentation](https://learn.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/connect-to-sharepoint))
- Or download the `react-content-query-webpart.sppkg` file available in the `sharepoint/solution` folder of the repository and add it directly in your app catalog in order to be able to use it in your site. 

Note : The second method will only work for Office 365 sites, since the **.ppkg** file points to an Office 365 public CDN url which expects the referer to come from a valid https://**\*.sharepoint.com\*** url.

### Configuring the Web Part

As seen in the [User friendly configuration](#user-friendly-configuration) section, configuring the web part is quite straight forward. However, here's a list of *gotchas* that could save you some time :

- The `Web Url` property uses the search to find all sites that are under the current domain. That being said, newly created sites can take a while to appear within the dropdown options, based on the search crawl schedule.
- The `Filters` property still supports query string expressions like *[PageQueryString:ParamName]* for text fields, and date expressions such as *[Today]* or *[Today] + 4* for date fields.
- The `Template` property stops getting automtically generated while selecting view fields as soon as the template is manually updated, in order to prevent unwanted loss of templating efforts.
- The `Template Url` property has priority over the `Template` property, which means if a valid handlebars template url is provided, the inline template will be kept, but ignored at runtime.  

### Designing your Handlebars template

#### Basics

Before anything, make sure you understand the basics of Handlebars and its associated syntax by reading their [documentation](http://handlebarsjs.com)

#### Available tokens

To make it simple, a `template context` is automatically exposed within the handlebars template, giving the user the ability to work with the following exposed tokens :

Property         | Description
-----------------|------------------
{{items}}        | The array of objects that represents the items returned from the CAML query
{{pageContext}}  | The SPFx [PageContext](https://github.com/SharePoint/sp-dev-docs/blob/master/reference/spfx/sp-page-context/pagecontext.md) object which contains usefull informations about the current web, list, user, language etc...
{{accessDenied}} | A boolean value indicating if the current user has a denied access to the configured site that gets queried. This gives the designer the power to decide what to render in a case where the current user doesn't have access to the queried site.
{{webNotFound}}  | A boolean value indicating if the configured site that gets queried doesn't exist anymore. This also gives the designer the power to decide what to render in a case where the queried site doesn't exist anymore.

#### Available block helpers

Besides the available tokens above, nearly 150 [block helpers](http://handlebarsjs.com/block_helpers.html) are also available for use in the Handlebars template, see [handlebars-helpers](https://github.com/helpers/handlebars-helpers#helpers) for a list of all available block helpers. 

*Example using the "compare" block helper for conditional rendering based on current language :*
```handlebars
{{#compare pageContext.web.language '==' 1033}}
    <h1>This is rendered if current language is 1033</h1>
{{else}}
    <h1>This is rendered if current language is anything else
{{/compare}}
```

#### Displaying items and their values

For displaying items and their field values, we must first iterate through the exposed **{{items}}** token using a **{{each}}** block helper : 

*Handlebars : *
```handlebars
{{#each items}}
    <div class="item"></div>
{{/each}}
```

*Output : *
```handlebars
<div class="item"></div>
<div class="item"></div>
<div class="item"></div>
...
```

Once we can loop within the items, we can render any field, as long as the field has been selected in the `View Fields` property of the toolpane. The Handlebars token corresponsding to a field is always the field's internal name, which is displayed in between {{brackets}} next to the field's display name in the property pane for reference. 

*Handlebars : *
```handlebars
{{#each items}}
    <div class="item">
        <p>MyField value : {{MyField}}</p>
    </div>
{{/each}}
```

*Output : *
```handlebars
<div class="item">[object]</div>
<div class="item">[object]</div>
<div class="item">[object]</div>
```

We are almost there, the above code is rendering a *[object]* because the Content Query Web Part offers 3 different ways to render a field value:

Property | Description
---------|---------------
{{MyField.textValue}} | Renders the text value of the field, a more readable end-user value to use for display.
{{MyField.htmlValue}} | Renders the HTML value of the field. For example, a *Link* field HTML value would render something like \<a href="...">My Link Field\</a>
{{MyField.rawValue}}  | Returns the raw value of the field. For example, a *Taxonomy* field raw value would return an object which contains the term wssId and it's label

*Handlebars : *
```handlebars
{{#each items}}
    <div class="item">
        <p>MyUserField text value : {{MyUserField.textValue}}</p>
        <p>MyUserField html value : {{MyUserField.htmlValue}}</p>
        <p>MyUserField raw value : {{MyUserField.rawValue}}</p>
    </div>
{{/each}}
```

*Output : *
```handlebars
<div class="item">
    <p>MyUserField text value : Simon-Pierre Plante</p>
    <p>MyUserField html value : <a href="..." onclick="...">Simon-Pierre Plante</a></p>
    <p>MyUserField raw value : 26</p>
</div>
...
```
<br>

### Including your own external scripts and/or block helpers

#### Including basic library files

For including JavaScript files within the web part, file URLs must be added to the **External Scripts** parameter available in the toolpart. 

<img src="Misc/externalScripts.png" />

Each file URL must be on its own line, and placed in the desired order. The scripts will be loaded asynchronously, but in a sequential fashion, which means that the web part will wait until a script is completely loaded before proceeding to load the next one.

#### Including custom logic files

If you need custom logic files that can interact precisely **before** or **after** the rendering of the HTML generated by the *Handlebars* template, you must follow the pattern below in order for the web part to recognize the endpoints and call them when needed :

```javascript
ReactContentQuery.ExternalScripts.MyScriptFile = {
	
    onPreRender: function(wpContext, handlebarsContext) {
        // Do someting before rendering (ie: adding a custom block helper)
    },
    
    onPostRender: function(wpContext, handlebarsContext) {
        // Do something after rendering (ie: calling a plugin on the generated HTML)
    }
    
}
```

Looking at this example, here are the key things that needs to be respected in order for the file to work :

_Namespace_

- [x] The script uses a namespace which starts by **ReactContentQuery.ExternalScripts.**, followed by the name of its own file
- [x] The name of the file has to be written without its **.js** extension, and without any characters that aren't letters or numbers
- [x] The name of the file needs to respect the same casing as in it's URL

Examples :

*https://www.mysite.com/MyScript.js*
```javascript
ReactContentQuery.ExternalScripts.MyScript {
    ...
}
```

*https://www.mysite.com/_My-Funky*named*Script_.js*
```javascript
ReactContentQuery.ExternalScripts.MyFunkynamedScript {
    ...
}
```

_Functions_

- [x] The script implements the **onPreRender** function for code that has to be executed before rendering
- [x] The scripts implements the **onPostRender** function for code that has to be executed after rendering

Both functions provide the following parameters : 

Parameter             | Description
----------------------|-------------
**wpContext**         | Represents the context of the web part which called the function, which exposes all kinds of useful information such as **wpContext.domElement** which represents the HTML element on which the current web part is being rendered. 
**handlebarsContext** | Represents the handlebars context used for generating the template of the current web part. Can be used for adding handlebar block helpers in the **onPreRender** function for example.


#### Including custom block helpers

Custom *block helpers* that can be used directly within the *Handlebars* template can be added simply by using a custom logic script file that implements the **onPreRender** function.

Example: 

*https://www.mysite.com/MyCustomBlockHelper.js*
```javascript
ReactContentQuery.ExternalScripts.MyCustomBlockHelper = {

    onPreRender: function(wpContext, handlebarsContext) {
    
        // Adds the "testHelper"
        handlebarsContext.registerHelper('testHelper', function(param, options) {
            return "Output from testHelper : " + param;
        });
    }
}
```

## Building the code

```bash
git clone the repo
npm i
npm i -g gulp
gulp
```

This package produces the following:

* lib/* - intermediate-stage commonjs build artifacts
* dist/* - the bundled script, along with other resources
* deploy/* - all resources which should be uploaded to a CDN.


<img src="https://pnptelemetry.azurewebsites.net/sp-dev-fx-webparts/samples/react-content-query-webpart/onprem" />
