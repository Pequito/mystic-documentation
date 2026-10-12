# Documentation Status

This page tracks the broad coverage of the Mystic Documentation project.

## Status Levels

| Status | Meaning |
|---|---|
| Planned | Page or section has been identified but not written |
| Draft | Initial documentation exists and needs review or expansion |
| Needs verification | Documentation exists but behavior should be reproduced against a named Mystic version |
| Verified | Procedure or behavior has been tested and the environment is recorded |
| Version-specific | Confirmed only for a named Mystic release or platform |

## Phase 1: Foundation

| Page | Status | Verification | Notes |
|---|---|---|---|
| Getting Started | Draft | Needs verification | Phase 1 navigation and recommended learning path |
| What Is Mystic BBS? | Draft | Needs verification | Architecture and ecosystem overview |
| Installing Mystic | Draft | Needs verification | Fresh-install workflow and installer concepts |
| First SysOp Account | Draft | Needs verification | Local account creation and SysOp elevation |
| Mystic Directory Structure | Draft | Needs verification | Core paths and backup implications |
| Mystic Configuration System | Draft | Needs verification | Configuration areas and MUTIL distinction |
| Starting Mystic | Draft | Needs verification | Local mode, configuration mode, and MIS startup concepts |
| Backup and Upgrade | Draft | Needs verification | Backup, upgrade, verification, and rollback workflow |

## FTN Networking

| Area | Status | Notes |
|---|---|---|
| FTN Overview | Draft | Initial terminology and architecture |
| FTN Addressing | Draft | Initial zone/net/node/point/domain explanation |
| Echomail and Netmail | Draft | Initial conceptual comparison |
| Mystic FTN Mail Flow | Draft | Initial inbound/outbound processing model |
| BinkP | Planned | Dedicated page pending |
| EchoMail Nodes | Planned | Dedicated page pending |
| MUTIL | Planned | Dedicated networking/processing page pending |
| MIS POLL | Planned | Current FTN polling/transport documentation pending |
| Legacy FIDOPOLL | Planned | Historical/upgrade reference only |
| AreaFix | Planned | Dedicated page pending |
| FileFix | Planned | Dedicated page pending |
| TIC / File Echoes | Planned | Dedicated page pending |
| FTN Troubleshooting | Planned | Diagnostic workflow pending |

## Future Core Documentation

| Area | Status | Notes |
|---|---|---|
| Message Bases | Planned | Phase 2 |
| File Bases | Planned | Phase 2 |
| Menus and Themes | Planned | Phase 2 |
| Users and Security | Planned | Phase 2 |
| Network Services | Planned | Phase 2/3 |
| Administration | Planned | Phase 3 |
| Events and Semaphores | Planned | Phase 3 |
| General Troubleshooting | Planned | Phase 3 |

## Verification Policy

When documenting version-sensitive behavior, record the Mystic version and operating system used for testing whenever possible.

Do not mark a procedure **Verified** simply because the configuration appears plausible. Verification should include the expected runtime result.

A page may remain **Draft** while also stating that specific procedures still **Need verification**. Once a procedure has been reproduced, record the environment used and update the status accordingly.
