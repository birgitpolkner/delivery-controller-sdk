﻿# Set-BrokerApplicationGroup

   Changes properties of application groups.

## Syntax
```
Set-BrokerApplicationGroup [-InputObject] <ApplicationGroup[]> [-PassThru] [-Description <String>] [-Enabled <Boolean>] [-RestrictToTag <String>] [-SessionSharingEnabled <Boolean>] [-UserFilterEnabled <Boolean>] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]

Set-BrokerApplicationGroup [-Name] <String> [-PassThru] [-Description <String>] [-Enabled <Boolean>] [-RestrictToTag <String>] [-SessionSharingEnabled <Boolean>] [-UserFilterEnabled <Boolean>] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   The Set-BrokerApplicationGroup cmdlet changes the properties of one or more application groups. The changed properties and the new values of those properties are specified as parameters to Set-BrokerApplicationGroup.

This cmdlet cannot change the relationships of application group objects with other objects. For instance, it cannot change which users can access applications in this application group, or change which desktop groups this application group is published to. To do this, you need to remove the existing association, and then add a new association.

The following example shows how to change the desktop group that application group $applicationGroup is associated with from $desktopGroup1 to $desktopGroup2:
Remove-BrokerApplicationGroup $applicationGroup -DesktopGroup $desktopGroup1
Add-RemoveApplicationGroup $applicationGroup -DesktopGroup $desktopGroup2

Application groups may not be renamed using this cmdlet. To rename an application group, use Rename-BrokerApplicationGroup.

## Related Commands
  * [Add-BrokerApplicationGroup](Add-BrokerApplicationGroup.html)
  * [Get-BrokerApplicationGroup](Get-BrokerApplicationGroup.html)
  * [New-BrokerApplicationGroup](New-BrokerApplicationGroup.html)
  * [Remove-BrokerApplicationGroup](Remove-BrokerApplicationGroup.html)
  * [Rename-BrokerApplicationGroup](Rename-BrokerApplicationGroup.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| InputObject | Specifies the application group whose properties should be altered. Its Uid can also be substituted for the object reference. | true | true (ByValue) |  |
| Name | Alters the properties of application groups whose name matches the supplied pattern. | true | true (ByPropertyName) |  |
| PassThru | This cmdlet does not generate any output, unless you use the PassThru parameter, in which case it returns the affected record. | false | false | False |
| Description | The new description for the application group. | false | false |  |
| Enabled | Whether the application group's applications should be launchable by end users. | false | false |  |
| RestrictToTag | Specifies the new values of the application group's tag restriction. | false | false |  |
| SessionSharingEnabled | Specifies the new value of the application group's SessionSharingEnabled flag. | false | false |  |
| UserFilterEnabled | Specifies the new value of the application group's UserFilterEnabled flag. | false | false |  |
| LoggingId | Specifies the identifier of the high level operation that this cmdlet call forms a part of. Desktop Studio and Desktop Director typically create High Level Operations. PowerShell scripts can also wrap a series of cmdlet calls in a High Level Operation by way of the Start-LogHighLevelOperation and Stop-LogHighLevelOperation cmdlets. | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller that the PowerShell snapin will connect to. This can be provided as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value will become the default. |

## Input Type
### Citrix.Broker.Admin.SDK.ApplicationGroup
   You can pipe application groups to Set-BrokerApplication.
## Return Values
### None or Citrix.Broker.Admin.SDK.ApplicationGroup
   This cmdlet does not generate any output, unless you use the PassThru parameter, in which case it generates a Citrix.Broker.Admin.SDK.ApplicationGroup object.
## Examples

### EXAMPLE 1
```
C:\PS> Set-BrokerApplicationGroup 'Helpdesk Apps' -Enabled $false
```
   Description<br>-----------<br>Prevent new instances of applications in the 'Helpdesk Apps' application group from being launched.
### EXAMPLE 2
```
C:\PS> Get-BrokerApplicationGroup | Set-BrokerApplicationGroup -UserFilterEnabled $false
```
   Description<br>-----------<br>Disable the user filter on every application group in the system. (Other access control mechanisms, such as access policy and user filters on individual applications, still apply.)
