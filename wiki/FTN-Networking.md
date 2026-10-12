# FTN Networking

FTN stands for **Fido Technology Network**. It describes the addressing, message exchange, routing, and network conventions historically associated with FidoNet and now used by many independent BBS networks.

FidoNet is one FTN network. Mystic BBS can also participate in other FTN-style networks.

> **Documentation status**
>
> Initial conceptual documentation. Mystic-specific configuration pages will be added separately and verified against named releases.

## Core Concepts

An FTN system typically involves:

- **Node** — a BBS or system participating in the network
- **AKA** — an FTN address assigned to a system
- **Uplink** — another node from which a system receives or to which it sends network traffic
- **Echomail** — shared public message areas distributed among participating systems
- **Netmail** — addressed messages sent between FTN users or systems
- **Domain** — a name used to distinguish one FTN network from another
- **Packet** — a container used to transport FTN messages
- **BinkP** — a commonly used protocol for moving FTN traffic over TCP/IP

## Example FTN Address

```text
21:1/100
│  │ │
│  │ └── Node
│  └──── Net
└─────── Zone
```

A point address adds another component:

```text
1:123/456.7
│ │   │   │
│ │   │   └── Point
│ │   └────── Node
│ └────────── Net
└──────────── Zone
```

See [FTN Addressing](FTN-Addressing) for a more complete explanation.

## Mystic FTN Components

Mystic commonly uses several components when participating in FTNs:

| Component | General purpose |
|---|---|
| EchoMail Addresses | Defines local FTN identities / AKAs |
| EchoMail Nodes | Defines remote systems Mystic exchanges FTN traffic with |
| Message Bases | Stores local, echomail, and netmail messages |
| MUTIL | Performs message and file processing tasks |
| FIDOPOLL / polling functions | Moves or schedules FTN traffic between systems |
| BinkP | Network transport commonly used between FTN nodes |
| AreaFix | Manages echomail area subscriptions |
| FileFix | Manages file-echo subscriptions |
| TIC processing | Processes metadata associated with FTN file echoes |

The exact configuration and behavior can vary by Mystic release, so those topics will be documented on dedicated version-aware pages.

## Next Pages

- [FTN Addressing](FTN-Addressing)
- [Echomail and Netmail](Echomail-and-Netmail)
- [Mystic FTN Mail Flow](Mystic-FTN-Mail-Flow)
