# Starting Mystic

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic release and platform.

Mystic can be started in different modes depending on whether you are configuring the BBS, logging in locally, or providing network services to remote users.

## Configuration Mode

Use configuration mode when changing Mystic settings:

Windows:

```text
mystic -cfg
```

Linux or another Unix-like system:

```text
./mystic -cfg
```

This opens the Mystic configuration system rather than a normal user session.

## Local Login

Use local mode when logging into the BBS directly from its host computer.

Windows:

```text
mystic -l
```

Linux or another Unix-like system:

```text
./mystic -l
```

Local login is useful for:

- Creating the first user account
- Testing menus
- Testing security levels
- Performing SysOp work without using a network connection

Starting Mystic locally does not by itself expose a Telnet, SSH, or other network listener.

## Network Services and MIS

MIS is Mystic's Internet/server component. When configured server instances are active, MIS is responsible for providing those services.

A typical foreground server start in the Mystic directory is conceptually:

Windows:

```text
mis server
```

Linux or another Unix-like system:

```text
./mis server
```

The exact command and service-management method should be verified for the Mystic release and operating system being used.

For a production system, MIS is normally treated as a long-running service rather than something started manually in an interactive terminal after every reboot.

Operating-system service integration will be documented separately.

## Do Not Start With Privileged Ports

During initial testing, prefer unprivileged/high-numbered ports where practical.

On Unix-like systems, binding low-numbered ports can require additional privileges or capabilities. Do not permanently run the entire BBS as `root` simply to bind a familiar port such as 23.

First verify the service on a high port. Service hardening, capabilities, firewall rules, and port forwarding can be addressed after the application itself is working correctly.

## Basic Startup Verification

### Local Mystic

A local-session test is successful when:

- Mystic starts without a fatal error
- The login or new-user process is displayed
- Your SysOp account can log in
- Menus display correctly

### MIS

An initial MIS test is successful when:

- MIS starts without immediately exiting because of a configuration error
- The intended server instance is enabled
- The expected port is listening
- A connection from an allowed test client reaches the correct Mystic login flow
- Relevant logs show the connection and do not show repeated startup errors

Do not open a router or firewall to the public Internet until local or LAN testing succeeds.

## Stop and Review on Errors

If Mystic or MIS reports a path, permission, port, or data-file error, correct that problem before enabling additional services.

Avoid changing several unrelated configuration areas at once. A single controlled change is much easier to troubleshoot.

## Related Topics

- [Creating the First SysOp Account](First-Sysop-Account)
- [Mystic Configuration System](Mystic-Configuration-System)
- [Mystic Directory Structure](Mystic-Directory-Structure)
- [Backup and Upgrade](Backup-and-Upgrade)
