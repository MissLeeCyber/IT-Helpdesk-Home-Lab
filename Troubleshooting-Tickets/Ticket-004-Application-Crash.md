# Ticket 004 – Application Crashing (09/25/2026)

## User Report

**User:** David
**Issue:** Application keeps crashing.

David reports that an application repeatedly closes or crashes when he attempts to use it.

## Initial Assessment

The first step is to reproduce the issue and determine exactly what happens.

Documented:

* Application name
* What action causes the crash
* Exact error message, if any
* When the issue began
* Whether the issue occurs every time
* Whether other users are experiencing the same problem

## Troubleshooting Steps

### 1. Reproduce the Problem

Attempted to open and use the application to determine whether the reported problem could be reproduced.

Recorded the exact error message or behavior if one appeared.

### 2. Determine the Scope

Asked whether other users were experiencing the same application problem.

* **One user affected:** Investigate the user's computer, application installation, profile, or configuration.
* **Multiple users affected:** Investigate the application service, server, network, or vendor-side issue.

### 3. Check Service Status

If the application depends on an online service, checked the organization's internal IT status page or the application's official service-status information when appropriate.

### 4. Check for Updates

Verified that:

* The application was up to date.
* Windows was up to date.
* Any required application components were current.

### 5. Check Task Manager

Opened Task Manager to determine whether the application was still running in the background after appearing to close.

If the application was hung or unresponsive, the process could be ended and the application tested again.

### 6. Review Event Viewer

Opened Event Viewer and reviewed:

**Windows Logs → Application**

Looked for events occurring at approximately the same time as the crash.

Relevant information may include:

* Application Error events
* Faulting application
* Faulting module
* Exception information
* Event timestamp

The event information can help identify whether the crash is related to the application itself, a Windows component, or another dependency.

### 7. Test the Application

After making an appropriate change, reopened the application and attempted the same action that originally caused the crash.

Confirmed whether the problem was resolved.

## Troubleshooting Method

**Reproduce → Exact Error → Scope → Service Status → Updates → Task Manager → Event Viewer → Fix → Retest**

## Resolution

The exact cause and resolution would depend on the evidence discovered during troubleshooting.

## Skills Demonstrated

* Application troubleshooting
* Task Manager
* Event Viewer
* Windows troubleshooting
* Service-status investigation
* Error message analysis
* Process management
* Verification after remediation

## Key Takeaway

An application crash should be investigated systematically rather than immediately assuming the application needs to be reinstalled. Reproducing the issue, identifying the exact error, determining the scope, and reviewing available evidence can help identify the actual cause.
