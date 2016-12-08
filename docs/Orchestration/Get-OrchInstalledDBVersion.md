﻿# Get-OrchInstalledDBVersion

   Gets a list of all available database schema versions for the Orchestration Service.

## Syntax
```
Get-OrchInstalledDBVersion [-Upgrade] [-Downgrade] [-AdminAddress <String>] [<CommonParameters>]
```

## Detailed Description
   Gets the current version number of the Citrix Orchestration Service database schema when called with no parameters.

When called with the -Upgrade parameter, gets the service schema version numbers to which an upgrade could be performed.

When called with the -Downgrade parameter, gets the service schema version numbers to which a downgrade could be performed.

The SQL scripts to perform schema upgrades and downgrades can be obtained using the Get-OrchDBVersionChangeScript cmdlet. Citrix recommends that where possible service schema upgrades are performed using Studio rather than manually via the SDK.

Only one of the -Upgrade or -Downgrade parameters may be supplied at once.

## Related Commands
  * [Get-OrchDBVersionChangeScript](Get-OrchDBVersionChangeScript.html)
  * [Get-OrchDBSchema](Get-OrchDBSchema.html)
## Parameters

| Name   | Description | Required? | Pipeline Input | Default Value |
| --- | --- | --- | --- | --- |
| Upgrade | Specifies that only schema versions to which the current database version can be updated should be returned. | false | false |  |
| Downgrade | Specifies that only schema versions to which the current database version can be reverted should be returned. | false | false |  |
| AdminAddress | Specifies the address of a XenDesktop controller the PowerShell snap-in will connect to. You can provide this as a host name or an IP address. | false | false | Localhost. Once a value is provided by any cmdlet, this value becomes the default. |

## Input Type
### None
   You cannot pipe input into this cmdlet.
## Return Values
### System.Version
   Get-OrchInstalledDBVersion returns database schema version numbers as requested.<br>Major <Integer> Minor <Integer> Build <Integer> Revision <Integer>## Notes
   If the command fails, the following errors can be returned.<br>    Error Codes<br>    -----------<br>    InvalidParameterCombination<br>        Both the Upgrade and Downgrade flags were specified.<br>    NoOp<br>        The operation was successful but had no effect.<br>    NoDBConnections<br>        The database connection string for the Orchestration Service has not been specified.<br>    DatabaseError<br>        An error occurred in the service while attempting a database operation.<br>    DatabaseNotConfigured<br>        The operation could not be completed because the database for the service is not configured.<br>    DataStoreException<br>        An error occurred in the service while attempting a database operation - communication with the database failed for various reasons.<br>    PermissionDenied<br>        You do not have permission to execute this command.<br>    AuthorizationError<br>        There was a problem communicating with the Citrix Delegated Administration Service.<br>    CommunicationError<br>        There was a problem communicating with the remote service.<br>    ExceptionThrown<br>        An unexpected error occurred.  For more details, see the Windows event logs on the controller or the XenDesktop logs.
## Examples

### EXAMPLE 1
```
PS C:\>Get-OrchInstalledDBVersion

Major  Minor  Build  Revision
-----  -----  -----  --------
5      6      0      0
```
   Description<br>-----------<br>Gets the current Citrix Orchestration Service database schema version number.
### EXAMPLE 2
```
C:\PS>Get-OrchInstalledDBVersion -Upgrade
```
   Description<br>-----------<br>Get the versions of the Orchestration Service database schema for which upgrade scripts are supplied.