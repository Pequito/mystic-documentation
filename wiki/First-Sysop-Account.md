# Creating the First SysOp Account

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic release and platform.

A fresh Mystic installation needs a user account that can be elevated to System Operator privileges. Create this account locally before opening the BBS to remote users.

## Prerequisites

Before continuing:

- Mystic has been installed successfully
- You can access the Mystic installation directory from a local terminal or command prompt
- No public-facing service is required for this procedure

## Step 1: Start a Local Session

Change to the Mystic installation directory and start Mystic in local mode.

Windows:

```text
mystic -l
```

Linux or another Unix-like system when running from the current directory:

```text
./mystic -l
```

Local mode is the preferred way to perform the initial user creation because it does not require a network connection.

## Step 2: Create Your User Account

Follow Mystic's new-user prompts and create the account you intend to use for SysOp administration.

Record the credentials securely. Use a strong password even if the BBS is not yet reachable from the network.

After the account is created and you reach the normal BBS menu, log out and return to the operating-system command prompt.

## Step 3: Open the Configuration System

Windows:

```text
mystic -cfg
```

Linux or another Unix-like system:

```text
./mystic -cfg
```

In the configuration system, open:

```text
Editors
  -> User Editor
```

Select the user account you just created.

## Step 4: Elevate the Account

In Mystic 1.12-era configuration screens, the User Editor provides an account-upgrade action using `Ctrl-U`.

Select the System Operator security level, traditionally level `255`, then save the user record before leaving the editor.

Because keyboard shortcuts and labels can change between builds, confirm the displayed action in the version you are running before saving.

## Step 5: Verify the Account

Exit the configuration system and start another local login:

```text
mystic -l
```

or on Unix-like systems:

```text
./mystic -l
```

Log in using the newly elevated account.

A successful verification should show that the account has SysOp-level access and can see administrative menu options that are hidden from ordinary users.

## Security Notes

- Do not use a trivial password because the system is "only local" during setup.
- Do not share the SysOp account with ordinary users.
- Create normal test accounts separately when validating menus and security levels.
- Do not assume that a menu item being visible means every underlying operating-system permission is correct.

## Next Step

Continue with [Mystic Directory Structure](Mystic-Directory-Structure) before making broader configuration changes.
