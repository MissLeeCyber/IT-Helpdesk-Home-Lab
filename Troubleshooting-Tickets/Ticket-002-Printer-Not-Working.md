# Ticket 002 – Printer Not Working (09/25/2026)

## User Report

**User:** Mike
**Issue:** Printer is not printing.

Mike reports that he is unable to print documents from his computer.

## Initial Assessment

The first step is to determine whether the issue is caused by the physical printer, Windows printer configuration, the print queue, the Print Spooler service, a device/driver problem, or another system issue.

## Troubleshooting Steps

### 1. Check Physical Printer Status

Verified that:

* The printer is powered on.
* The printer is connected properly.
* The printer is not displaying an error.
* The printer has paper and toner/ink.
* There are no obvious hardware problems.

### 2. Check Windows Printer Settings

Verified that:

* The correct printer is selected.
* Windows recognizes the printer.
* The printer is not showing an offline status.
* There are no stuck documents in the print queue.

### 3. Check the Print Spooler Service

Opened `services.msc` and checked the **Print Spooler** service.

Verified that the service was running and configured appropriately.

If the service was stopped or malfunctioning, it could be restarted and the print job tested again.

### 4. Check Device Manager

Opened Device Manager and checked the printer/device for:

* Warning indicators
* Driver problems
* Device errors

If a driver issue was identified, the appropriate driver could be updated or reinstalled according to company procedures.

### 5. Review Event Viewer

Opened Event Viewer and reviewed relevant Windows logs for errors related to:

* Print Spooler
* Printer services
* Device/driver problems

The event timestamp would be compared with the time the printing problem occurred.

### 6. Test Printing

After making the appropriate change, sent a test print to the printer.

Confirmed whether the printer successfully completed the job.

## Troubleshooting Method

**Physical → Windows Configuration → Print Spooler → Device/Driver → Event Logs → Test**

## Resolution

The exact cause and resolution would depend on the evidence discovered during troubleshooting.

## Skills Demonstrated

* Windows printer troubleshooting
* Services management
* Device Manager
* Event Viewer
* Driver troubleshooting
* Systematic troubleshooting
* Verification after remediation

## Key Takeaway

Troubleshooting should progress from simple, low-risk checks toward more involved system-level investigation. Restarting or reinstalling components should not be the first response when the actual cause has not been identified.
