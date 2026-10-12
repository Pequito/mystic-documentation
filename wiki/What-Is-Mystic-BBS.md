# What Is Mystic BBS?

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic release and platform.

Mystic BBS is a bulletin board system package designed to provide interactive text-based services for local and remote users. A Mystic system can host message areas, file areas, menus, themes, user accounts, network services, and automated tasks from a single BBS environment.

Mystic is commonly used for traditional Internet-accessible BBS systems and for store-and-forward message networks such as FTNs. It also includes scripting and development features for SysOps who want to customize how their system behaves.

## Core Parts of a Mystic System

A typical Mystic installation contains several programs that work together.

| Component | Purpose |
|---|---|
| `MYSTIC` | Main BBS application used for local sessions and user sessions started by a server |
| `MYSTIC -CFG` | Opens the interactive Mystic configuration system |
| `MIS` | Internet/server component used to provide configured network services and events |
| `MUTIL` | Utility processor used for maintenance, imports, exports, message processing, and other batch-style operations |
| MPL / MPY | Scripting and development mechanisms used to extend Mystic |

Executable names may include an extension on some operating systems.

## What Mystic Can Manage

A Mystic BBS can include:

- Local and remote user accounts
- Message groups and message bases
- File groups and file bases
- Menus, prompts, display files, and themes
- Telnet, SSH, BinkP, and other configured network services
- FTN echomail and netmail
- QWK networking
- Scheduled and semaphore-driven events
- Logs and operational status information
- MPL and embedded Python customizations

Not every installation needs every feature. A small private BBS can use only a subset, while a larger public system may use most of them.

## How the Pieces Fit Together

At a high level:

```text
Users
  |
  +-- Local login --------------------+
  |                                    |
  +-- Network connection --> MIS ------+--> MYSTIC
                                           |
                                           +--> Users / Menus
                                           +--> Message Bases
                                           +--> File Bases
                                           +--> Themes / Display Files

MUTIL ------------------------------------> Maintenance / Import / Export

MYSTIC -CFG ------------------------------> System Configuration
```

This is intentionally simplified. Later sections document individual services and processing flows in more detail.

## Local Use vs. Server Use

A local login starts a user session directly on the computer running Mystic. This is useful for initial setup, SysOp work, and testing.

Remote users normally reach Mystic through a service configured in MIS. MIS accepts the network connection and starts or hands the session to Mystic according to the configured service.

Starting a local Mystic session does **not** by itself make the BBS reachable from the Internet.

## Configuration vs. Utilities

Two concepts are important to keep separate:

- **Mystic Configuration System** is the interactive configuration interface opened with `mystic -cfg`.
- **MUTIL** performs utility and batch-processing tasks, generally controlled by configuration files.

A SysOp will normally use both over the lifetime of a system.

## Platforms and Releases

Mystic has been distributed for multiple operating systems and processor families, including Windows, Linux, macOS, and ARM Linux. Availability can differ by Mystic release.

Before installing, confirm that the archive you intend to use matches the operating system and architecture of the target host.

This documentation is being developed around the Mystic 1.12 generation, but individual pages must be verified against specific releases before being marked **Verified**.

## Recommended Learning Path

If you are building a new system, continue in this order:

1. [Installing Mystic](Installing-Mystic)
2. [Creating the First SysOp Account](First-Sysop-Account)
3. [Mystic Directory Structure](Mystic-Directory-Structure)
4. [Mystic Configuration System](Mystic-Configuration-System)
5. [Starting Mystic](Starting-Mystic)
6. [Backup and Upgrade](Backup-and-Upgrade)

After the foundation is understood, move into message bases, file bases, network services, and FTN networking.

For programming and scripting language documentation, use the dedicated [Mystic MPL Documentation](https://github.com/Pequito/mystic-mpl-docs) project.
