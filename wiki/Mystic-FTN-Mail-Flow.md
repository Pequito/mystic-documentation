# Mystic FTN Mail Flow

This page presents a conceptual model of how FTN traffic moves through a Mystic BBS system.

> **Documentation status**
>
> Draft architecture. Exact utility commands, semaphore behavior, paths, and processing options will be documented separately and verified against named Mystic releases.

## Incoming Echomail

A simplified incoming path is:

```text
Remote FTN Node
      |
    BinkP
      |
 Transport / Poller
      |
 Mystic Inbound
      |
    MUTIL
 ImportEchoMail
      |
 Packet Processing
      |
 Message Base
      |
     User
```

The important troubleshooting principle is that each stage is separate. A successful network connection does not necessarily mean the packet was imported successfully.

## Outgoing Echomail

A simplified outgoing path is:

```text
User Posts Message
       |
 Mystic Message Base
       |
 Export Processing
       |
      MUTIL
 ExportEchoMail
       |
 Packet / Bundle
       |
 Transport / Poller
       |
      BinkP
       |
     Uplink
```

## Diagnostic Model

When a message is missing, identify the last stage that completed successfully:

```text
Transport
   ↓
Inbound / Outbound Storage
   ↓
Packet Validation
   ↓
Import / Export Processing
   ↓
Area or Route Mapping
   ↓
Message Base / Destination
```

This approach is more reliable than changing multiple Mystic settings at once.

## Planned Expansion

Dedicated pages will document:

- EchoMail Addresses
- EchoMail Nodes
- BinkP
- MUTIL import and export
- FIDOPOLL and polling behavior
- AreaFix
- Netmail routing
- TIC and file-echo processing
- FTN logs and troubleshooting
