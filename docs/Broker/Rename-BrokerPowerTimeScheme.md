﻿# Rename-BrokerPowerTimeScheme

   Changes the name of an existing power time scheme.

## Syntax
```
Rename-BrokerPowerTimeScheme [-InputObject] <PowerTimeScheme[]> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]

Rename-BrokerPowerTimeScheme [-Name] <String> [-NewName] <String> [-PassThru] [-LoggingId <Guid>] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   The Rename-BrokerPowerTimeScheme cmdlet renames a particular power time scheme.

Each power time scheme is associated with a particular desktop group, and covers one or more days of the week, defining which hours of those days are considered peak times and which are off-peak times. In addition, the time scheme defines a pool size value for each hour of the day for the days of the week covered by the time scheme. No one desktop group can be associated with two or more time schemes that cover the same day of the week.

For more information about the power policy mechanism and pool size management, see 'help about_Broker_PowerManagement'.

## Related Commands
  * [Get-BrokerPowerTimeScheme](Get-BrokerPowerTimeScheme.html)
  * [Set-BrokerPowerTimeScheme](Set-BrokerPowerTimeScheme.html)
  * [New-BrokerPowerTimeScheme](New-BrokerPowerTimeScheme.html)
  * [Remove-BrokerPowerTimeScheme](Remove-BrokerPowerTimeScheme.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| InputObject | The power time scheme to be renamed. | true | true (ByValue) |  |
| Name | The current name of the power time scheme to be renamed. | true | true (ByPropertyName) |  |
| NewName | The new name to be applied to the power time scheme. | true | false |  |
| PassThru | This cmdlet does not generate any output, unless you use the PassThru parameter, in which case it returns the affected record. | false | false | False |
| LoggingId | Specifies the identifier of the high level operation that this cmdlet call forms a part of. Desktop Studio and Desktop Director typically create High Level Operations. PowerShell scripts can also wrap a series of cmdlet calls in a High Level Operation by way of the Start-LogHighLevelOperation and Stop-LogHighLevelOperation cmdlets. | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller that the PowerShell snapin will connect to. This can be provided as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value will become the default. |

## Input Type
### Citrix.Broker.Admin.SDK.PowerTimeScheme
   The power time scheme to be renamed.
## Return Values
### None or Citrix.Broker.Admin.SDK.PowerTimeScheme
   This cmdlet does not generate any output, unless you use the PassThru parameter, in which case it generates a Citrix.Broker.Admin.SDK.PowerTimeScheme object.
## Examples

### EXAMPLE 1
```
C:\PS> Rename-BrokerPowerTimeScheme -Name 'Development Weekdays' -NewName 'Dev Week'
```
   Description<br>-----------<br>Renames the power time scheme named 'Development Weekdays' to 'Dev Week'.
