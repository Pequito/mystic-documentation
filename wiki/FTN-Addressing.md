# FTN Addressing

FTN addresses identify systems and, optionally, point systems within an FTN network.

> **Documentation status**
>
> Initial conceptual documentation. Mystic-specific address limits and configuration fields should be verified against the Mystic release being documented before exact limits are added.

## Basic Address Format

```text
Zone:Net/Node
```

Example:

```text
21:1/100
```

The components are:

- **Zone** — broad network grouping
- **Net** — network grouping within a zone
- **Node** — individual FTN system

## Point Address

A point number can be appended:

```text
Zone:Net/Node.Point
```

Example:

```text
1:123/456.7
```

## AKAs

**AKA** means "also known as." In FTN usage, an AKA is an FTN address assigned to a system.

A Mystic BBS may participate in more than one FTN network or may require more than one address. Each address must be associated with the correct network configuration.

## Domains

A domain distinguishes one FTN network from another when numeric addresses alone are not sufficient.

Conceptually:

```text
Address: 21:1/100
Domain:  example-network
```

Do not assume that two matching numeric addresses belong to the same FTN if their domains differ.

## Next Pages

- [FTN Networking](FTN-Networking)
- [Echomail and Netmail](Echomail-and-Netmail)
- [Mystic FTN Mail Flow](Mystic-FTN-Mail-Flow)
