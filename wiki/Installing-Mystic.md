# Installing Mystic

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic release and platform.

This page describes a conservative first-install workflow for Mystic BBS. The goal is to get a clean installation in place without exposing network services or making unnecessary system-level changes.

## Before You Begin

Decide the following before running the installer:

- Which operating system and architecture will host Mystic
- Which Mystic release you intend to install
- Where the Mystic root directory will live
- Which operating-system account will own and run the BBS files
- Whether data, themes, and message bases will remain under the main Mystic directory or be placed elsewhere
- Where backups will be stored

For a first installation, keeping Mystic's directories together is easier to understand and back up. More complex layouts can be introduced later if there is a clear operational reason.

## Obtain the Correct Archive

Download the Mystic archive that matches the target operating system and architecture.

Before installing:

1. Keep the original archive unchanged.
2. Extract it into a temporary working directory.
3. Review the files supplied with that exact release, especially release notes, `WHATSNEW.TXT`, and any installation or upgrade instructions included in the archive.
4. Do not reuse upgrade instructions from a different Mystic release.

## Fresh Installation

The normal interactive workflow is:

1. Extract the Mystic installation archive.
2. Run the included installer for the target platform.
3. Select the fresh-install option.
4. Review the destination paths.
5. Start the installation.
6. Exit the installer after it reports completion.
7. Create the first SysOp account before configuring public network access.

The installer normally establishes the primary directory structure and initial data files required by Mystic.

### Command Names

On Windows, commands are normally entered using executable names directly, for example:

```text
install
mystic -cfg
mystic -l
```

On Linux and other Unix-like systems, when running from the current directory, the equivalent commands commonly use `./`:

```text
./install
./mystic -cfg
./mystic -l
```

Exact filenames and execution requirements can vary by distribution and release.

## Installer Modes

Mystic installers in the 1.12 generation may provide multiple command-line modes, including interactive installation, automated installation, replacement of selected program files, and extraction of selected files.

Typical syntax is conceptually similar to:

```text
install
install auto <root> [options]
install replace <directory>
install extract <mask> <directory>
```

These modes are useful, but the automated and replacement modes should not be treated as shortcuts around release-specific instructions.

### Automated Installation

An automated install can be useful for repeatable lab builds or testing. For the first production installation, the interactive installer is easier to review because it exposes the selected paths before files are written.

### Overwrite Options

Treat any installer option containing terms such as `overwrite` or `replace` as destructive until proven otherwise.

Do not use an overwrite option against an existing BBS unless:

- A verified backup exists
- The target Mystic release specifically requires that action
- You have reviewed what files will be replaced
- You have a rollback plan

## Directory Ownership

Mystic should be run by an account that has appropriate access to its files and directories. Avoid making the entire installation globally writable.

On Unix-like systems, prefer a dedicated unprivileged account or the intended SysOp account for normal operation. Do not run Mystic permanently as `root` merely to simplify file permissions or network-port binding.

Service hardening and low-numbered network ports will be covered separately.

## Initial Verification

After the installer completes, verify that:

- The Mystic root directory exists
- Core executables are present
- The data directory exists
- Theme/display content exists
- Message storage directories exist if selected by the installer
- The current user can read and write the directories Mystic is expected to manage

Do not consider a fresh installation complete until you can start a local Mystic session and create the first SysOp account.

## Next Step

Continue with [Creating the First SysOp Account](First-Sysop-Account).

If you are upgrading an existing installation instead of performing a fresh install, stop here and review [Backup and Upgrade](Backup-and-Upgrade) first.
