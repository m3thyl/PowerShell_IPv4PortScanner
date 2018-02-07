# PowerShell - IPv4 Port Scanner

Powerful asynchronus IPv4 Port Scanner for PowerShell.

## Description

This powerful asynchronus IPv4 Port Scanner allows you to scan every Port-Range you want (500 to 2600 would work). Only TCP-Ports are scanned.

The result will contain the Port number, Protocol, Service name, Description and the Status.

![Screenshot](Documentation/Images/IPv4PortScan.png?raw=true "IPv4PortScan")

To reach the best possible performance, this script uses a [RunspacePool](https://msdn.microsoft.com/en-US/library/system.management.automation.runspaces.runspacepool(v=vs.85).aspx). As you can see in the following screenshot, the individual tasks are distributed across all cpu cores:

![Screenshot](Documentation/Images/IPv4PortScan_CPUusage.png?raw=true "CPU usage")

If you are looking for a module containing this script as function... you can find it [here](https://github.com/BornToBeRoot/PowerShell)!

Maybe you're also interested in my asynchronus [IPv4 Network Scanner](https://github.com/BornToBeRoot/PowerShell_IPv4NetworkScanner).

## Syntax

```powershell
.\IPv4PortScan.ps1 [-ComputerName] <String> [[-StartPort] <Int32>] [[-EndPort] <Int32>] [[-Threads] <Int32>] [[-Force]] [<CommonParameters>]
```

## Example

```powershell
PS> .\IPv4PortScan.ps1 -ComputerName fritz.box -EndPort 500

Port Protocol ServiceName  ServiceDescription               Status
---- -------- -----------  ------------------               ------
  53 tcp      domain       Domain Name Server               open
  80 tcp      http         World Wide Web HTTP              open
``` 

Blah Blah