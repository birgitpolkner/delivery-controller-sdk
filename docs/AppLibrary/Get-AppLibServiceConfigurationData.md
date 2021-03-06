﻿# Get-AppLibServiceConfigurationData

   Gets configuration data for the service.

## Syntax
```
Get-AppLibServiceConfigurationData [-Name <String[]>] [-Value <String[]>] [-ReturnTotalRecordCount] [-MaxRecordCount <Int32>] [-Skip <Int32>] [-SortBy <String>] [-Filter <String>] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   Provides the ability to determine the configuration parameters for the service

## Related Commands
  * [Set-AppLibServiceConfigurationData](Set-AppLibServiceConfigurationData.html)
  * [Remove-AppLibServiceConfigurationData](Remove-AppLibServiceConfigurationData.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| Name | The Configuration data item Name . | false | false |  |
| Value | The Configuration data item value. | false | false |  |
| ReturnTotalRecordCount | When specified, the cmdlet outputs an error record containing the number of records available. This error record is additional information and does not affect the objects written to the output pipeline. See about_AppLib_Filtering for details. | false | false | False |
| MaxRecordCount | Specifies the maximum number of records to return. | false | false | 250 |
| Skip | Skips the specified number of records before returning results. Also reduces the count returned by -ReturnTotalRecordCount. | false | false | 0 |
| SortBy | Sorts the results by the specified list of properties. The list is a set of property names separated by commas, semi-colons, or spaces. Optionally, prefix each name with a + or - to indicate ascending or descending order. Ascending order is assumed if no prefix is present. | false | false | The default sort order is by name or unique identifier. |
| Filter | Gets records that match a PowerShell-style filter expression. See about_AppLib_Filtering for details. | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller the PowerShell snap-in will connect to. You can provide this as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value becomes the default. |

## Input Type
### 
   
## Return Values
### Citrix.AppLibrary.Sdk.ServiceConfigurationData
   This object provides details of the configuration data and contains the following information:<br>    Name <string><br>        The Name for the configuration item.<br>    Value <string><br>        The value for the configuration item.## Notes
   In the case of failure the following errors can be produced.<br>    Error Codes<br>    -----------<br>    UnknownObject<br>        One of the specified objects was not found.<br>    PartialData<br>         Only a subset of the available data was returned.<br>    InvalidFilter<br>        A filtering expression was supplied that could not be interpreted for this cmdlet.<br>    CouldNotQueryDatabase<br>         The query required to get the database was not defined.<br>    DatabaseError<br>        An error occurred in the service while attempting a database operation.<br>    DatabaseNotConfigured<br>        The operation could not be completed because the database for the service is not configured.<br>    DataStoreException<br>        An error occurred in the service while attempting a database operation - communication with the database failed for various reasons.<br>    PermissionDenied<br>        You do not have permission to execute this command.<br>    AuthorizationError<br>        There was a problem communicating with the Citrix Delegated Administration Service.<br>    CommunicationError<br>        An error occurred while communicating with the service.<br>    ExceptionThrown<br>        An unexpected error occurred.  To locate more details see the Windows event logs on the controller being used, or examine the XenDesktop logs.
## Examples

### EXAMPLE 1
```
C:\PS>Get-AppLibConfiguratuionData

Name                : DeltaDiskDelete.timeDelay
Value               : 10
```
   Description<br>-----------<br>Get the Configuration data for the service.
