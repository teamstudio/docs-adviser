# Release Notes

## Teamstudio Adviser 6.7.0
The current version, Adviser 6.7.0, is a feature release of Adviser. See the Fix List section below for details. Please read the installation guide (available [here](installing.md)) carefully before installing.

## New Features
### Directory Support in Filters
The parent directory of a selected database can now be filtered using the Filter button dropdown, allowing the filter to be applied to all databases in the directory on the current server or on all servers. See [Filters](filters.md) for more information on filtering.

### Complexity and Filtered Databases
When databases are filtered in Adviser, the complexity scan will no longer create/update complexity information for those databases. Combined with directory filtering, this can be a huge performance benefit during initial scans. This operation is non-destructive; complexity data is not discarded, out-dated complexity information is flagged in the UI, and removing the filter can allow complexity to be updated in future scans.

### Log UI Improvements
The Logs pane in the browser app has been improved to show stack traces when clicking on error messages, display more accurate by-date grouping across time zones, and to better allow copying of text in log entries.

## Upgrading
### Upgrading from Adviser 6.x
Upgrading Adviser involves refreshing or replacing the design of the server database, updating the command-line module on the workstation and restarting the server's HTTP task. See Upgrading Adviser on the [installation page](installing.md) for a detailed list of steps.

### Upgrading from Adviser 5.x
It is possible to upgrade from Usage Auditor 5.0 and retain all collected Usage data. Note that data collected with versions of Usage Auditor prior to 5.0 cannot be imported into Adviser. To ensure a successful upgrade, please contact our tech support team for help with your migration.

### Running Adviser and Usage Auditor
If you are evaluating Adviser, you may want to run Adviser and Usage Auditor in parallel. This is supported but you will need to run them on separate workstations. The Adviser workstation database contains a long-running scheduled agent that detects job requests on the server and this agent will not allow Usage Auditor's agent to run.

## Known Issues
* An error message from HSQL will be recorded in the server log whenever Adviser updates usage data. This message is benign, it refers to HSQL being unable to adjust logging levels, due to Domino JVM policy. It starts with the messages  
  &lt;clinit&gt; failure initializing JDK logging system.  Continuing without Application logging.  
  HTTP JVM: java.security.AccessControlException: Access denied (java.util.logging.LoggingPermission control)
* Allowing the browser to "save password" may cause errors in the browser UI on some browsers/platforms. See the [installation page](installing.md) for details.
* During Complexity Scans, the Adviser Workstation may log warnings indicating that "Notes initialization failed" due to reuse of a process ID. Normally these warnings are harmless; the Workstation will recover and continue processing.

## Fix List
### Adviser 6.7.0
[TMS-1423] - Upgrade web UI supporting frameworks  
[TMS-1424] - Skip complexity for filtered databases  
[TMS-1425] - Allow filtering of a database's parent directory  
[TMS-1426] - improve web UI log views to be easier to select text and display/select stack traces  
[TMS-1427] - Improve accuracy of web UI log view date-grouping with regard to local time zones  
[TMS-1429] - Fix issue where Business Value on database details wouldn't 'stick' until the document was reloaded  
