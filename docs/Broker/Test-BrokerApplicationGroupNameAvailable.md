﻿# Test-BrokerApplicationGroupNameAvailable

   Determine whether the proposed ApplicationGroup Name is available for use.

## Syntax
```
Test-BrokerApplicationGroupNameAvailable [-Name] <String[]> [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   This cmdlet checks whether proposed ApplicationGroup Name is available for use. It returns a record for each Name indicating the availability of that Name, with $true indicating that the Name is unused and available for use, or $false if it is not available.

## Related Commands
  * [Get-BrokerApplicationGroup](Get-BrokerApplicationGroup.html)
  * [New-BrokerApplicationGroup](New-BrokerApplicationGroup.html)
  * [Rename-BrokerApplicationGroup](Rename-BrokerApplicationGroup.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| Name | The ApplicationGroup Name to be tested. | true | true (ByValue, ByPropertyName) |  |
| AdminAddress | Specifies the address of a XenDesktop controller that the PowerShell snapin will connect to. This can be provided as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value will become the default. |

## Input Type
### System.String
   You can pipe a string that contains the Name to test.
## Return Values
### Citrix.Broker.Admin.SDK.NameAvailability
   The cmdlet returns a result for each Name specified. An availability of "True" indicates the Name is available for use, and "False" if it is not available.
## Examples

### EXAMPLE 1
```
C:\PS> Test-BrokerApplicationGroupNameAvailable -Name Test1
```
   Description<br>-----------<br>Checks whether the Name "Test1" is available.
### EXAMPLE 2
```
C:\PS> Test-BrokerApplicationGroupNameAvailable @("Test1","Test2","Test3")
```
   Description<br>-----------<br>Checks whether each of the specified names is available.
