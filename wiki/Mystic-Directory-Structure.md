# Mystic Directory Structure

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic release and platform.

Understanding Mystic's directory layout is important before changing paths, configuring backups, troubleshooting permissions, or moving an existing BBS.

Mystic supports configurable paths, so a running system may not use the same layout as a fresh installation.

## Core Paths

A typical Mystic 1.12-era installation includes or references the following logical paths:

| Path | Purpose |
|---|---|
| System path | Main Mystic directory containing core executables and supporting files |
| Data path | Primary Mystic data files and system configuration data |
| Theme path | Theme directories and theme-related resources |
| Message base path | Default storage location for message-base data |
| Log path | Mystic activity and service logs |
| Semaphore path | Small trigger files used by event-driven processing |
| EchoMail inbound | Incoming FTN packets received from known nodes |
| Unsecured inbound | Incoming FTN packets received from unknown or unsecured nodes |
| EchoMail outbound | Outgoing FTN packets waiting for delivery |

With a conventional single-root installation, these are often represented by directories similar to:

```text
mystic/
├── data/
├── themes/
├── msgs/
├── logs/
├── semaphore/
└── echomail/
    ├── in/
    │   └── unsecure/
    └── out/
        └── primary/
```

Additional directories for display files, menus, scripts, documentation, or other features may also be present depending on the installer and Mystic release.

## System Path

The system path is the root of the Mystic installation. Core programs such as Mystic, MIS, and MUTIL normally live here along with supporting files.

Avoid moving individual executables away from the rest of the installation unless the release documentation explicitly supports it.

## Data Path

The data path contains information that Mystic uses to operate the BBS. Treat it as persistent application data, not temporary cache data.

Changes to the data path affect the whole system and should be backed up before modification.

## Theme Path

The theme path contains the directories used by Mystic's theme system. Themes can include prompts, display resources, and other presentation-related content.

Custom theme work should be included in backups.

## Message Base Path

The message-base path is the default location for message-base storage.

Do not assume that deleting or replacing a message-base file is harmless. Message bases are persistent user content and should be treated as application data.

## Log Path

Logs record operational activity and are useful when troubleshooting user sessions, network services, and automated jobs.

Logs normally do not need to be restored as part of a basic disaster-recovery process, but retaining recent logs can be valuable when investigating a failure.

## Semaphore Path

Mystic uses semaphore files as lightweight signals that an event or processing action should occur. These are typically small files whose presence is meaningful to Mystic's event system.

Do not treat the semaphore directory as ordinary temporary storage.

## FTN Paths

FTN installations commonly use separate inbound and outbound locations.

Keeping secured inbound, unsecured inbound, and outbound traffic separate makes it easier to understand where a packet is in the mail-processing flow.

The FTN section documents these paths in more detail.

## Viewing or Changing Paths

Open the Mystic configuration system:

```text
mystic -cfg
```

or on Unix-like systems:

```text
./mystic -cfg
```

Then review the system-path settings under the main configuration area.

Before changing a path:

1. Back up the existing data.
2. Create the destination directory.
3. Confirm ownership and permissions.
4. Move or copy the required data deliberately.
5. Update Mystic's configured path.
6. Start Mystic and verify the affected feature.
7. Keep the original data until verification is complete.

## Backup Implications

A backup of only the Mystic executable files is not a complete BBS backup.

At minimum, identify every configured persistent-data location, including paths that may live outside the Mystic root directory.

Continue with [Backup and Upgrade](Backup-and-Upgrade) for the recommended backup workflow.
