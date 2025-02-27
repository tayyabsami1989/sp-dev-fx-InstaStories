# Check User Group

## Summary

This web part finds all the Office 365 or AAD Security groups a user is a member of or all the members present in such a group. It can be used as an admin utility to quickly check the membership of any user or group from within a SharePoint page itself. The retrieved results can also be exported to a CSV file.

![Check User Group](./assets/CheckUserGroup.gif)

## Compatibility

| :warning: Important          |
|:---------------------------|
| Every SPFx version is only compatible with specific version(s) of Node.js. In order to be able to build this sample, please ensure that the version of Node on your workstation matches one of the versions listed in this section. This sample will not work on a different version of Node.|
|Refer to <https://aka.ms/spfx-matrix> for more information on SPFx compatibility.   |

![SPFx 1.10](https://img.shields.io/badge/SPFx-1.10.0-green.svg) 
![Node.js v10 | v8](https://img.shields.io/badge/Node.js-v10%20%7C%20v8-green.svg) 
![Compatible with SharePoint Online](https://img.shields.io/badge/SharePoint%20Online-Compatible-green.svg)
![Does not work with SharePoint 2019](https://img.shields.io/badge/SharePoint%20Server%202019-Incompatible-red.svg "SharePoint Server 2019 requires SPFx 1.4.1 or lower")
![Does not work with SharePoint 2016 (Feature Pack 2)](https://img.shields.io/badge/SharePoint%20Server%202016%20(Feature%20Pack%202)-Incompatible-red.svg "SharePoint Server 2016 Feature Pack 2 requires SPFx 1.1")
![Local Workbench Incompatible](https://img.shields.io/badge/Local%20Workbench-Incompatible-red.svg "The solution requires access to Microsoft Graph")
![Hosted Workbench Compatible](https://img.shields.io/badge/Hosted%20Workbench-Compatible-green.svg)
![Compatible with Remote Containers](https://img.shields.io/badge/Remote%20Containers-Compatible-green.svg)

## Features

This web part uses Microsoft Graph API to get all the Office 365 or AAD Security Groups a user is a member of or all the members in such a group.

This extension illustrates the following concepts:

* Requesting `Directory.Read.All` permission scope for Microsoft Graph through the `webApiPermissionRequests` property in `package-solution.json`
* Using MSGraphClient to call the `/groups/{groupId}/members` API to get all the members in a group
* Using MSGraphClient to call the `/users/${email}/memberOf` API to get all the groups a user is member of
* Exporting the results to a CSV file using [**react-csv**](https://www.npmjs.com/package/react-csv) third party package

## Solution

Solution|Author(s)
--------|---------
react-check-user-group | [Aakash Bhardwaj](https://twitter.com/aakash_316)

## Minimal Path to Awesome

* Clone this repository
* `npm install`
* `gulp bundle --ship`
* `gulp package-solution --ship`
* Add to Site Collection App Catalog and Install the App
* Go to the API Management section in the new SharePoint Admin Center (*https://{tenantname}-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/webApiPermissionManagement*)
* Approve the permission request for Directory.Read.All to Microsoft Graph

>  This sample can also be opened with [VS Code Remote Development](https://code.visualstudio.com/docs/remote/remote-overview). Visit https://aka.ms/spfx-devcontainer for further instructions.


## Help

We do not support samples, but we this community is always willing to help, and we want to improve these samples. We use GitHub to track issues, which makes it easy for  community members to volunteer their time and help resolve issues.

If you're having issues building the solution, please run [spfx doctor](https://pnp.github.io/cli-microsoft365/cmd/spfx/spfx-doctor/) from within the solution folder to diagnose incompatibility issues with your environment.

You can try looking at [issues related to this sample](https://github.com/pnp/sp-dev-fx-webparts/issues?q=label%3A%22sample%3A%20react-check-user-group") to see if anybody else is having the same issues.

You can also try looking at [discussions related to this sample](https://github.com/pnp/sp-dev-fx-webparts/discussions?discussions_q=react-check-user-group) and see what the community is saying.

If you encounter any issues while using this sample, [create a new issue](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Abug-suspected%2Csample%3A%20react-check-user-group&template=bug-report.yml&sample=react-check-user-group&authors=@aakashbhardwaj619&title=react-check-user-group%20-%20).

For questions regarding this sample, [create a new question](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Aquestion%2Csample%3A%20react-check-user-group&template=question.yml&sample=react-check-user-group&authors=@aakashbhardwaj619&title=react-check-user-group%20-%20).

Finally, if you have an idea for improvement, [make a suggestion](https://github.com/pnp/sp-dev-fx-webparts/issues/new?assignees=&labels=Needs%3A+Triage+%3Amag%3A%2Ctype%3Aenhancement%2Csample%3A%20react-check-user-group&template=question.yml&sample=react-check-user-group&authors=@aakashbhardwaj619&title=react-check-user-group%20-%20).

## Disclaimer

**THIS CODE IS PROVIDED *AS IS* WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**


<img src="https://pnptelemetry.azurewebsites.net/sp-dev-fx-webparts/samples/react-check-user-group" />
