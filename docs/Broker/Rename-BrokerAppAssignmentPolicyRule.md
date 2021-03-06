﻿# Rename-BrokerAppAssignmentPolicyRule

   Renames an application rule in the site's assignment policy.

## Syntax
```
Rename-BrokerAppAssignmentPolicyRule [-InputObject] <AppAssignmentPolicyRule[]> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]

Rename-BrokerAppAssignmentPolicyRule [-Name] <String> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   The Rename-BrokerAppAssignmentPolicyRule cmdlet renames an application rule in the site's assignment policy. The Name property of the rule is changed.

An application rule in the assignment policy defines the users who are entitled to a self-service persistent machine assignment from the rule's desktop group; once assigned the machine can run one or more applications published from the group.

## Related Commands
  * [New-BrokerAppAssignmentPolicyRule](New-BrokerAppAssignmentPolicyRule.html)
  * [Get-BrokerAppAssignmentPolicyRule](Get-BrokerAppAssignmentPolicyRule.html)
  * [Set-BrokerAppAssignmentPolicyRule](Set-BrokerAppAssignmentPolicyRule.html)
  * [Remove-BrokerAppAssignmentPolicyRule](Remove-BrokerAppAssignmentPolicyRule.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| InputObject | The application rule in the assignment policy to be renamed. | true | true (ByValue) |  |
| Name | The existing name of the application rule in the assignment policy to be renamed. | true | true (ByPropertyName) |  |
| NewName | The new name of the application rule in the assignment policy being renamed. The new name must not match that of any other existing rule in the policy (irrespective of whether it is a desktop or application rule). | true | false |  |
| PassThru | This cmdlet does not generate any output, unless you use the PassThru parameter, in which case it returns the affected record. | false | false | False |
| LoggingId | Specifies the identifier of the high level operation that this cmdlet call forms a part of. Desktop Studio and Desktop Director typically create High Level Operations. PowerShell scripts can also wrap a series of cmdlet calls in a High Level Operation by way of the Start-LogHighLevelOperation and Stop-LogHighLevelOperation cmdlets. | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller that the PowerShell snapin will connect to. This can be provided as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value will become the default. |

## Input Type
### Citrix.Broker.Admin.SDK.AppAssignmentPolicyRule
   The application rule in the assignment policy being renamed.
## Return Values
### None or Citrix.Broker.Admin.SDK.AppAssignmentPolicyRule
   This cmdlet does not generate any output, unless you use the PassThru parameter, in which case it generates a Citrix.Broker.Admin.SDK.AppAssignmentPolicyRule object.
## Examples

### EXAMPLE 1
```
C:\PS> Rename-BrokerAppAssignmentPolicyRule 'Offshore' -NewName 'Remote Workers'
```
   Description<br>-----------<br>Renames the application rule in the assignment policy called Offshore to Remote Workers. The new name of the rule must be unique in the assignment policy.
