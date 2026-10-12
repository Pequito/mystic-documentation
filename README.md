<p align="center">
  <img src="assets/wiki/mystic_documentation_dashboard.png" alt="Mystic Documentation" width="100%">
</p>

<h1 align="center">Mystic Documentation</h1>

<p align="center">
  Community-maintained documentation for installing, configuring, operating, networking, troubleshooting, and extending Mystic BBS.
</p>

> **Mystic BBS was created by James Coyle.**  
> This repository is an independent community documentation project and is not an official Mystic BBS publication.

## Start Here

| Goal | Documentation |
|---|---|
| New or returning SysOp | [Getting Started](https://github.com/Pequito/mystic-documentation/wiki/Getting-Started) |
| Understand Mystic and its components | [What Is Mystic BBS?](https://github.com/Pequito/mystic-documentation/wiki/What-Is-Mystic-BBS) |
| Install a new system | [Installing Mystic](https://github.com/Pequito/mystic-documentation/wiki/Installing-Mystic) |
| Learn the configuration system | [Mystic Configuration System](https://github.com/Pequito/mystic-documentation/wiki/Mystic-Configuration-System) |
| Begin FTN networking | [FTN Networking](https://github.com/Pequito/mystic-documentation/wiki/FTN-Networking) |
| Review project coverage | [Documentation Status](https://github.com/Pequito/mystic-documentation/wiki/Documentation-Status) |

## Current Documentation

### Phase 1: Foundation

The first foundation pass is complete and currently marked **Draft / Needs verification** while procedures are reproduced against named Mystic releases and platforms.

- [Getting Started](https://github.com/Pequito/mystic-documentation/wiki/Getting-Started)
- [What Is Mystic BBS?](https://github.com/Pequito/mystic-documentation/wiki/What-Is-Mystic-BBS)
- [Installing Mystic](https://github.com/Pequito/mystic-documentation/wiki/Installing-Mystic)
- [Creating the First SysOp Account](https://github.com/Pequito/mystic-documentation/wiki/First-Sysop-Account)
- [Mystic Directory Structure](https://github.com/Pequito/mystic-documentation/wiki/Mystic-Directory-Structure)
- [Mystic Configuration System](https://github.com/Pequito/mystic-documentation/wiki/Mystic-Configuration-System)
- [Starting Mystic](https://github.com/Pequito/mystic-documentation/wiki/Starting-Mystic)
- [Backup and Upgrade](https://github.com/Pequito/mystic-documentation/wiki/Backup-and-Upgrade)

### FTN Networking

The FTN section currently establishes the core concepts and mail-flow model before moving into transport and automation topics.

- [FTN Networking Overview](https://github.com/Pequito/mystic-documentation/wiki/FTN-Networking)
- [FTN Addressing](https://github.com/Pequito/mystic-documentation/wiki/FTN-Addressing)
- [Echomail and Netmail](https://github.com/Pequito/mystic-documentation/wiki/Echomail-and-Netmail)
- [Mystic FTN Mail Flow](https://github.com/Pequito/mystic-documentation/wiki/Mystic-FTN-Mail-Flow)

Planned FTN coverage includes EchoMail Nodes, BinkP, MUTIL mail processing, MIS POLL, AreaFix, FileFix, TIC/file echoes, routing, nodelists, and troubleshooting. Legacy FIDOPOLL behavior will be documented only where it is useful for historical or upgrade reference.

## Project Scope

The long-term goal is a practical Mystic BBS reference covering:

- Installation and upgrades
- System configuration
- Users, security levels, and ACS
- Message groups and message bases
- File groups and file bases
- Menus, prompts, themes, and display files
- MIS and network services
- FTN echomail, netmail, BinkP, MUTIL, and polling
- AreaFix, FileFix, TIC processing, and file echoes
- Events, semaphores, logging, backups, and maintenance
- Troubleshooting and recovery
- Development integration and links to dedicated scripting documentation

## Documentation Standards

This project is intended to be useful at the console, not merely descriptive. Documentation should therefore be:

- **Practical** — focused on real SysOp tasks and operational workflows
- **Structured** — explaining how Mystic components fit together before presenting isolated settings
- **Version-aware** — clearly identifying behavior that differs between Mystic releases or platforms
- **Testable** — including verification steps wherever a procedure changes or starts something
- **Transparent** — distinguishing drafts, unverified procedures, and confirmed behavior
- **Original** — written as independent community documentation rather than copied third-party material

## Verification Policy

Documentation uses the following broad status levels:

| Status | Meaning |
|---|---|
| **Planned** | The page or section has been identified but not written |
| **Draft** | Initial documentation exists and needs review or expansion |
| **Needs verification** | The documented behavior should be reproduced against a named Mystic version and platform |
| **Verified** | The procedure or behavior has been tested and the environment is recorded |
| **Version-specific** | The behavior is confirmed only for a named Mystic release or platform |

A procedure is not considered verified simply because the configuration appears correct. Verification should include the expected runtime result.

See [Documentation Status](https://github.com/Pequito/mystic-documentation/wiki/Documentation-Status) for current coverage.

## MPL and MPY Development

Detailed Mystic Programming Language documentation is maintained separately in:

- [Pequito/mystic-mpl-docs](https://github.com/Pequito/mystic-mpl-docs)

This repository may document how scripting integrates with Mystic features, but language-level MPL and MPY documentation should remain in the dedicated programming documentation project rather than being duplicated here.

## Repository Layout

```text
mystic-documentation/
├── assets/
│   └── wiki/          # Documentation artwork and wiki assets
├── wiki/              # Wiki source Markdown
├── CONTRIBUTING.md    # Contribution guidelines
├── LICENSE             # Documentation license
└── README.md           # Project overview
```

The published documentation is available in the [GitHub Wiki](https://github.com/Pequito/mystic-documentation/wiki). The `wiki/` directory in this repository is maintained as the source copy for that documentation, including custom sidebar and footer content.

## Contributing

Corrections, tested procedures, screenshots, diagrams, platform notes, version notes, and additional Mystic documentation are welcome.

Before contributing, review [CONTRIBUTING.md](CONTRIBUTING.md). When documenting version-sensitive behavior, include the Mystic version and operating system used for testing whenever possible.

## About Mystic BBS

Mystic BBS was created by **James Coyle**. This project documents his software from a community and SysOp perspective while remaining independent of the official Mystic BBS project.

Mystic BBS software, names, and associated trademarks remain the property of their respective rights holders.

## License

Documentation in this repository is provided under the [MIT License](LICENSE).
