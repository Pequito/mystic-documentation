# Backup and Upgrade

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic release and platform.

Backups should be part of normal Mystic administration, not something created only immediately before a risky change.

An upgrade is successful only if the BBS can be restored to a known-good state when something goes wrong.

## What to Back Up

Identify every persistent path used by the installation.

This normally includes:

- Mystic system/root directory
- Data path
- Theme path
- Message-base path
- File-base metadata and file storage locations
- Custom menus and display files
- Scripts and custom modules
- FTN configuration and mail-processing data
- Any directories moved outside the default Mystic tree

Logs may also be worth preserving for troubleshooting, even when they are not required to restore normal operation.

## Before an Upgrade

Before changing Mystic versions:

1. Record the currently installed Mystic version.
2. Stop active Mystic services and automated processing.
3. Confirm that no users are connected.
4. Create a complete backup of all persistent paths.
5. Verify that the backup can be listed or extracted successfully.
6. Keep a copy of the currently running Mystic release files.
7. Extract the new release into a separate temporary directory.
8. Read the upgrade instructions supplied with the **target release**.
9. Review `UPGRADE.TXT`, `WHATSNEW.TXT`, and any release-specific notes before replacing files.

Do not perform an upgrade using instructions remembered from a previous version.

## Why Services Should Be Stopped

Backing up active data files while Mystic, MIS, MUTIL, or an event is modifying them can produce an inconsistent snapshot.

A controlled maintenance window reduces the chance of capturing half-written data or processing mail while files are being replaced.

## Installer Replacement Modes

Some Mystic installers provide a replacement mode similar to:

```text
install replace <mystic-directory>
```

This can be useful when the release's upgrade procedure explicitly calls for it.

Do not assume that replacing executables is the only step required for every version transition. Data conversion, prompt changes, configuration changes, or other release-specific actions may also be required.

## Avoid Blind Overwrite Operations

An automated installer may also provide an overwrite option.

Treat this as destructive. Never point an overwrite operation at the only copy of a production BBS.

## Upgrade Workflow

A conservative workflow is:

```text
Running system
     |
     v
Stop services
     |
     v
Create verified backup
     |
     v
Read target-release upgrade notes
     |
     v
Apply required upgrade steps
     |
     v
Start locally and verify
     |
     v
Start MIS / scheduled processing
     |
     v
Verify users, logs, messages, files, and networking
```

## Post-Upgrade Verification

At minimum, verify:

- Mystic reports the expected version
- A local SysOp login works
- Configuration mode opens
- Menus and themes load correctly
- Message areas can be accessed
- File areas can be accessed
- MIS starts correctly if used
- Configured network services start on the intended ports
- Scheduled events still run
- FTN import/export and polling work if used
- Recent logs do not show repeated errors

The exact checklist should grow with the features enabled on the BBS.

## Rollback

If a major function fails after an upgrade:

1. Stop Mystic services.
2. Preserve logs and any new diagnostic information.
3. Do not continue making unrelated configuration changes.
4. Restore the pre-upgrade snapshot or backup.
5. Verify the previous version is operational again.
6. Investigate the failed upgrade separately before retrying.

A rollback procedure that has never been tested should be considered unverified.

## Related Topics

- [Mystic Directory Structure](Mystic-Directory-Structure)
- [Mystic Configuration System](Mystic-Configuration-System)
- [Starting Mystic](Starting-Mystic)
