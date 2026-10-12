# Mystic Configuration System

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic release and platform.

Mystic provides an interactive configuration environment for most BBS settings. This is one of the primary tools a SysOp will use when building and maintaining a system.

## Starting Configuration Mode

From the Mystic installation directory:

Windows:

```text
mystic -cfg
```

Linux or another Unix-like system:

```text
./mystic -cfg
```

Configuration mode is separate from a normal user login.

## Main Configuration Areas

Mystic 1.12-era builds organize the configuration system into several broad areas.

### Configuration

System-wide BBS settings such as:

- System paths
- General settings
- Login and matrix behavior
- New-user defaults
- Password policy
- Message-base defaults
- File-base defaults

### Networking

Store-and-forward networking configuration such as:

- FTN addresses
- EchoMail nodes
- EchoMail groups
- AreaFix and FileFix support
- QWK networking settings

Detailed FTN configuration is covered separately in the [FTN Networking](FTN-Networking) section.

### Servers

Internet and network-service settings managed by MIS, including server definitions and general server behavior.

Possible server types depend on the Mystic release and can include Telnet, SSH, RLogin, BinkP, FTP, NNTP, SMTP, POP3, and HTTP.

A server appearing in the editor does not mean it should automatically be enabled or exposed to the Internet.

### Editors

Editors for structured Mystic configuration data, including items such as:

- Users
- Menus
- Themes and prompts
- Message bases and groups
- File bases and groups
- Security levels
- Archives and protocols
- Events

### Other

Miscellaneous operational tools and editors such as text/ANSI editing, log viewing, bad-name lists, bad-email lists, and version information.

Exact entries can vary by release.

## Configuration System vs. MUTIL

The configuration system and MUTIL serve different purposes.

```text
mystic -cfg
    Interactive system configuration and editors

mutil
    Utility and batch-processing operations
```

MUTIL is commonly used for maintenance, message processing, imports, exports, and automation. It should not be treated as a replacement for the interactive configuration system.

## Safe Change Practice

For significant changes:

1. Record the current setting.
2. Make one logical change at a time.
3. Save the configuration.
4. Test the affected function.
5. Review the relevant log if the result is unexpected.
6. Revert before making additional unrelated changes if the test fails.

This is especially important for network services, path changes, message storage, and events.

## Configuration Backups

Before large configuration changes, take a backup that includes the Mystic data path and any other persistent paths used by the system.

A screenshot or note of a setting is helpful, but it is not a substitute for a restorable backup.

## Next Step

Continue with [Starting Mystic](Starting-Mystic) to distinguish local BBS sessions from long-running network services.
