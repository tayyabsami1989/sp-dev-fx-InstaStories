# Feedback Sidebar Web Part

## Summary

This web part displays a sidebar that allows users to provide feedback on various sections of your site.
The sections displayed in the sidebar are dynamically generated based on the web parts configured on the site page.
Place this web part on top of your page in order to show the Feedback button.

![Feedback Sidebar Web Part](./assets/preview-img-01.png)
![Feedback Sidebar Web Part](./assets/preview.gif)

## Compatibility

| :warning: Important          |
|:---------------------------|
| Every SPFx version is only compatible with specific version(s) of Node.js. In order to be able to build this sample, please ensure that the version of Node on your workstation matches one of the versions listed in this section. This sample will not work on a different version of Node.|
|Refer to <https://aka.ms/spfx-matrix> for more information on SPFx compatibility.   |

![SPFx 1.15.0](https://img.shields.io/badge/SPFx-1.15.0-green.svg)
![Node.js v16](https://img.shields.io/badge/Node.js-v16-green.svg)
![Node.js v16 | v14 | v12 ](https://img.shields.io/badge/Node.js-v16%20%7C%20v14%20%7C%20v12-green.svg)
![Compatible with SharePoint Online](https://img.shields.io/badge/SharePoint%20Online-Compatible-green.svg)
![Does not work with SharePoint 2019](https://img.shields.io/badge/SharePoint%20Server%202019-Incompatible-red.svg "SharePoint Server 2019 requires SPFx 1.4.1 or lower")
![Does not work with SharePoint 2016 (Feature Pack 2)](https://img.shields.io/badge/SharePoint%20Server%202016%20(Feature%20Pack%202)-Incompatible-red.svg "SharePoint Server 2016 Feature Pack 2 requires SPFx 1.1")
![Local Workbench Unsupported](https://img.shields.io/badge/Local%20Workbench-Unsupported-red.svg "Local workbench is no longer available as of SPFx 1.13 and above")
![Hosted Workbench Compatible](https://img.shields.io/badge/Hosted%20Workbench-Compatible-green.svg)
![Compatible with Remote Containers](https://img.shields.io/badge/Remote%20Containers-Compatible-green.svg)

## Prerequisites

- Office 365 subscription with SharePoint Online
- SharePoint Framework [development environment](https://docs.microsoft.com/sharepoint/dev/spfx/set-up-your-development-environment) set up

## Minimal Path to Awesome

- Clone this repository (or [download this solution as a .ZIP file](https://pnp.github.io/download-partial/?url=https://github.com/pnp/sp-dev-fx-webparts/tree/main/samples/react-feedback-sidebar) then unzip it)
- From your command line, change your current directory to the directory containing this sample (`react-feedback-sidebar`, located under `samples`)
- create the package:
  - `npm i`
  - `gulp bundle --ship`
  - `gulp package-solution --ship`
- Add the app package to Site Collection App Catalog and install the App
- Add the web part to a page

## Solution

| Solution               | Author(s)                                                 |
| ---------------------- | --------------------------------------------------------- |
| react-feedback-sidebar | [Alessia De Martino](https://github.com/AlessiaDeMartino) |
| react-feedback-sidebar | Andrea Bellini                                            |
| react-feedback-sidebar | [Matteo Serpi](https://github.com/srpmtt)                 |
| react-feedback-sidebar | [Michele Catena](https://github.com/10xMike)              |

## Help

We do not support samples, but we this community is always willing to help, and we want to improve these samples. We use GitHub to track issues, which makes it easy for community members to volunteer their time and help resolve issues.

If you're having issues building the solution, please run [spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/) from within the solution folder to diagnose incompatibility issues with your environment.

You can try looking at [issues related to this sample](https://github.com/pnp/sp-dev-fx-webparts/issues?q=label%3A%22sample%3A%20react-feedback-sidebar") to see if anybody else is having the same issues.

You can also try looking at [discussions related to this sample](https://github.com/pnp/sp-dev-fx-webparts/discussions?discussions_q=react-feedback-sidebar) and see what the community is saying.

If you encounter any issues while using this sample, [create a new issue](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Abug-suspected%2Csample%3A%20react-feedback-sidebar&template=bug-report.yml&sample=react-feedback-sidebar&authors=@srpmtt&title=react-feedback-sidebar%20-%20).

For questions regarding this sample, [create a new question](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Aquestion%2Csample%3A%20react-feedback-sidebar&template=question.yml&sample=react-feedback-sidebar&authors=@srpmtt&title=react-feedback-sidebar%20-%20).

Finally, if you have an idea for improvement, [make a suggestion](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Aenhancement%2Csample%3A%20react-feedback-sidebar&template=question.yml&sample=react-feedback-sidebar&authors=@srpmtt&title=react-feedback-sidebar%20-%20).

## Disclaimer

**THIS CODE IS PROVIDED _AS IS_ WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**

<img src="https://pnptelemetry.azurewebsites.net/sp-dev-fx-webparts/samples/react-feedback-sidebar" />
