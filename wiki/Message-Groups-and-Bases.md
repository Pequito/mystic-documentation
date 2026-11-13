# Message Groups and Bases

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic BBS release and platform.  
> **Screenshots:** Configuration and terminal-client captures from an existing BBS. The version and platform for the full set have not yet been verified. The names and layout shown are **site-specific examples**, not defaults.

## Purpose

Mystic's message system organizes places where users can read and write messages. This guide introduces the Message Group Editor, Message Base Editor, and the user-facing message area screens. It focuses on **local configuration and usability**. FTN mail transport, BinkP, and MUTIL processing are covered in separate networking documentation.

## Concepts

| Term | Meaning in this guide |
|---|---|
| Message Group | A higher-level grouping used to organize related message areas |
| Message Base | A configured individual message area or store within the messaging system |
| Message Area | The user-facing location where messages are browsed or posted; naming varies by theme/menu |
| Local messages | Messages operated within the BBS without assuming a network transport |
| Echomail | Networked conference-style messages; requires correct network/processing configuration |
| Netmail | Addressed network mail; delivery behavior must be verified using FTN-specific procedures |
| ACS / restrictions | Configuration conditions governing which users may view or interact with an area |

Do not equate the appearance of a network-related group in the user interface with successful FTN mail delivery. Import, export, scanning, and transport must each be checked separately.

## 1. Message Group Editor

The Message Group Editor lists named group entries and their IDs. The sample screenshot includes names such as `private.users`, `network.local`, and `network.araknet`. These are **names chosen for this BBS**, not required Mystic groups.

![Mystic Message Group Editor](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/message-group-editor.png)

*Figure 1 — Message Group Editor: group names and identifiers.*

### What to document for each group

- The group's intended audience (for example, local users or a particular network)
- Any relevant display or access settings
- How the group will appear in the BBS menus
- The relationship between the group and its member message bases
- Whether it is used in a real network configuration or only for local organization

**Additional capture required:** A group's edit/detail view. The list screenshot does not establish the actual field names, allowed edits, or access-condition syntax.

## 2. Message Base Editor

The Message Base Editor lists configured bases, including an ID, description, and a network-related column in the example screen.

![Mystic Message Base Editor](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/message-base-editor.png)

*Figure 2 — Message Base Editor: list view. Entries such as `{e-mail}`, `{netmail}`, and `{netspam}` belong to the demonstrated installation.*

A complete base configuration walkthrough should eventually record:

1. The group to which the base belongs.
2. Its name/description as presented to users.
3. Any message storage or location settings actually exposed by the editor.
4. Read, post, and other access conditions, where supported.
5. Local versus network-related configuration values.
6. The outcome of a read/post test using a nonprivileged account.

These fields are **documentation targets**, not a claim that every version presents a field under these exact names. The detail screen has not yet been supplied.

## 3. What Users See: Message Areas

An administrative group/base list and a user-facing message-area view answer different questions. The editor shows **configuration**; the terminal screens show **navigation and runtime behavior**.

![Mystic BBS message area list](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/bbs-message-areas.png)

*Figure 3 — Example terminal-client message-area view, including `total`, `new`, and `yours` counts. Terminal title-bar connection details have been removed.*

In the sample UI, an area list provides a way to select an area for reading and offers shortcuts for common messaging actions. The precise shortcuts and layout are theme/menu dependent; do not assume that the shown interface is Mystic's unmodified default.

![Mystic BBS message network selection](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/bbs-network-selection.png)

*Figure 4 — Example network/group-selection overlay in the user-facing interface.*

The additional forum-list screenshot illustrates a different message listing presentation:

![Mystic BBS forum listing](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/bbs-forum-list.png)

*Figure 5 — A separate forum/area listing example. Interface behavior can differ by theme, menu, client, or development state.*

**Caution:** The supplied editor screenshots and terminal screenshots are not established as captures of the exact same base configuration or the same moment in time. Do not claim a one-to-one mapping between a specific editor row and a specific runtime row without checking it in a controlled test.

## 4. Safe Local Message-Area Test

The following is a **verification plan** rather than a completed, version-tested procedure.

1. Confirm a current backup and record the running Mystic version.
2. Use a test BBS or a clearly named disposable message area; do not modify a live echomail area to experiment.
3. In the Message Group Editor, choose or create a **test-only** group and record its details.
4. In the Message Base Editor, choose or create a local test base associated with that group. Record all relevant settings using the actual editor labels.
5. Configure the intended read/post restrictions for the test base; record any ACS expression exactly as entered.
6. Log in as an authorized test user and confirm the group/base can be found through the BBS interface.
7. Post a synthetic message (for example, `Documentation test — no personal data`). Exit and re-enter the message area; verify it can be read.
8. Log in as a test user who should not have access, and observe whether the area is hidden or access is denied.
9. Check the appropriate local logs or output, record results, and remove the temporary test content according to the tested cleanup procedure.

Do not use an existing networked area for this test until its mail-routing and processing implications are understood.

## 5. Verification Matrix

| Item | Test | Expected result | Status |
|---|---|---|---|
| Group configuration | Group is saved and displayed on reopening editor | Configured group persists | Pending |
| Base configuration | Base is saved and can be reopened | Configured base persists | Pending |
| Area navigation | Authorized test account locates area | Test area is accessible | Pending |
| Local post/read | Synthetic message is posted and read back | Content persists without an error | Pending |
| Access restriction | Restricted test account attempts to open/post | Behavior matches the documented restriction | Pending |
| Recovery | Restore previous settings or remove temporary area | Original test configuration remains healthy | Pending |

## 6. Basic Troubleshooting

| Symptom | Investigate |
|---|---|
| Group missing from a menu | Group configuration, menu navigation, and account restrictions |
| Base listed in the editor but not visible to the user | Group association, access conditions, and menu/theme behavior |
| User can read but cannot post | Posting restrictions, account settings, and actual runtime message/error |
| A message does not remain visible | Base settings, storage permissions, and session logs; do not assume an FTN failure |
| Network message does not arrive remotely | FTN configuration and mail-processing chain; see dedicated FTN docs |
| Counts differ from expectations | Read-pointer state, selected area, and whether the view is filtered |

## 7. Separate FTN Workstream

Local message-base administration is not the same as FTN transport. The project already provides introductory FTN documentation:

- [FTN Networking](FTN-Networking)
- [FTN Addressing](FTN-Addressing)
- [Echomail and Netmail](Echomail-and-Netmail)
- [Mystic FTN Mail Flow](Mystic-FTN-Mail-Flow)

BinkP node configuration, MUTIL import/export, MIS polling, and routing should remain under that workstream and require their own tested examples.

## Verification Record

```text
Mystic version:   Not yet recorded for these captures
Operating system: Not yet recorded
Architecture:     Not yet recorded
Date tested:      Pending
Tested by:        Pending
Result:           Needs verification
Notes:            Config list and runtime UI screenshots reviewed; no create/post/ACS workflow independently reproduced
```

## Further Screenshots Needed

- Message Group Editor: detail/edit page
- Message Base Editor: detail/edit page including any location, network, and access settings
- Synthetic message being composed, posted, and read back
- Access allowed/denied test from two disposable accounts
- A verified capture identifying Mystic version and platform

Do not include real private messages, third-party participants, private addresses, or FTN node information without consent and a separate privacy review.

## Related Topics

- [Users and Security](Users-and-Security)
- [Mystic Configuration System](Mystic-Configuration-System)
- [FTN Networking](FTN-Networking)