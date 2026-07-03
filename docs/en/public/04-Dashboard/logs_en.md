# Logs & Search

The Logs section of the Nyroxis Dashboard provides a clear, searchable, and structured view of all security-relevant events collected by Nyroxis Agent.
It is the forensic core of the platform — designed to give both non-technical users and security professionals instant visibility into what is happening on their device.

---

## Purpose of Logs View

The Logs module helps users understand:
- What events occurred and when
- Which processes, files, or network connections were involved
- Whether the activity appears normal or suspicious
- The full context of any event for forensic investigation

It turns raw encrypted event data into readable, timestamped, searchable entries.

---

## Event Categories

Nyroxis organizes logs into intuitive groups:

### 1. Process Events
- Process start and stop
- Parent/child relationships
- Execution paths and command-line parameters

### 2. Network Events
- Outgoing and incoming connections
- IP addresses and port details
- Protocol types

### 3. File System Events
- File creation, modification, and deletion
- Access to sensitive directories
- Registry changes

### 4. Privilege & Security Events
- Elevation attempts
- Access to restricted resources
- System policy changes
- Credential-related activity

### 5. System Activity
- Service start and stop
- Driver loading
- Windows Event Log entries (Security, System, Application)
- PowerShell and script execution

---

## Search & Filtering

The Logs interface includes a powerful filtering panel:

### Available Filters
- Date and time range
- Event category
- Severity level (Critical / High / Warning / Info)
- Source and channel
- Process name
- File path
- Network endpoint
- Keywords

### Search Capabilities
- Real-time filtering
- Multi-field search
- Export to CSV for documentation or external analysis

Designed to support both beginners and professional analysts.

---

## Event Details

Clicking an event opens a details panel displaying:
- Full event metadata
- Process lineage
- Related files or network connections
- Severity score
- Raw payload details

---

## Privacy & Offline-First

All logs:
- Are stored locally in the encrypted SQLite database
- Are fully encrypted (AES-256)
- Never leave the device
- Are processed without any cloud interaction

---

## Summary

The Logs & Search module provides a transparent, organized, and fully private way to explore system activity — giving users true forensic visibility without exposing any data externally.
