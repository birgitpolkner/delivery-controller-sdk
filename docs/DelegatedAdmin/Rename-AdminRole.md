﻿# Rename-AdminRole

   Rename a role

## Syntax
```
Rename-AdminRole [-InputObject] <Role> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]

Rename-AdminRole [-Id] <Guid> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]

Rename-AdminRole [-Name] <String> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   The Rename-AdminRole cmdlet changes the name of a role.

Role names must be unique, and you cannot modify the name of built-in roles.

## Related Commands
  * [New-AdminRole](New-AdminRole.html)
  * [Get-AdminRole](Get-AdminRole.html)
  * [Set-AdminRole](Set-AdminRole.html)
  * [Remove-AdminRole](Remove-AdminRole.html)
  * [Set-AdminRoleMetadata](Set-AdminRoleMetadata.html)
  * [Remove-AdminRoleMetadata](Remove-AdminRoleMetadata.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| InputObject | Specifies the role to rename (by object). | true | true (ByValue) |  |
| Id | Specifies the role to rename (by id). | true | true (ByPropertyName) |  |
| Name | Specifies the role to rename (by name). | true | true (ByPropertyName) |  |
| NewName | Specifies the new name of the role. | true | false |  |
| PassThru | Returns the affected record. By default, this cmdlet does not generate any output. | false | false | False |
| LoggingId | Specifies the identifier of the high-level operation this cmdlet call forms a part of. Citrix Studio and Director typically create high-level operations. PowerShell scripts can also wrap a series of cmdlet calls in a high-level operation by way of the Start-LogHighLevelOperation and Stop-LogHighLevelOperation cmdlets. | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller the PowerShell snap-in will connect to. You can provide this as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value becomes the default. |

## Input Type
### Citrix.DelegatedAdmin.Sdk.Role
   You can pipe the role to be renamed into this command.
## Return Values
### None or Citrix.DelegatedAdmin.Sdk.Role
   When you use the PassThru parameter, Rename-AdminRole generates a Citrix.DelegatedAdmin.Sdk.Role object. Otherwise, this cmdlet does not generate any output.
## Examples

### EXAMPLE 1
```
C:\PS> Rename-AdminRole -Name Supervisor -NewName HelpDeskLead
```
   Description<br>-----------<br>Renames the 'Supervisor' role to 'HelpDeskLead'.