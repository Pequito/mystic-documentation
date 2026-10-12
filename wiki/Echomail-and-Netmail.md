# Echomail and Netmail

Echomail and netmail are two fundamental FTN message types. They use the same broader FTN ecosystem but serve different purposes.

> **Documentation status**
>
> Initial conceptual documentation. Routing and Mystic-specific processing details will be expanded and version verified separately.

## Echomail

Echomail is shared discussion traffic distributed among systems linked to the same message area.

```text
                 Shared Echo Area
                       |
           +-----------+-----------+
           |           |           |
         BBS A       BBS B       BBS C
           |           |           |
         Users       Users       Users
```

A message posted on one participating system can be exported and distributed to the other linked systems.

Typical concepts include:

- Echo area name or tag
- Linked nodes
- Import and export processing
- Duplicate detection
- Seen-by and path information
- AreaFix subscription management

## Netmail

Netmail is addressed FTN mail intended for a specific FTN destination rather than a shared echo area.

```text
User
 |
BBS A
 |
Uplink / Routing
 |
FTN Network
 |
BBS B
 |
Recipient
```

Typical concepts include:

- Source FTN address
- Destination FTN address
- Routing rules
- Direct versus routed delivery
- Crash, hold, or other delivery attributes where supported

## Key Difference

| Echomail | Netmail |
|---|---|
| Shared discussion | Addressed message |
| Distributed to linked systems | Routed toward a destination |
| Associated with an echo area | Associated with an FTN recipient/address |
| Commonly subscription based | Commonly route based |

## Next Page

See [Mystic FTN Mail Flow](Mystic-FTN-Mail-Flow) for how these concepts fit into Mystic processing.
