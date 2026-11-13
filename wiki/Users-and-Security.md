# Users and Security

> **Documentation status:** Draft  
> **Verification:** Needs verification against a named Mystic BBS release and platform.  
> **Screenshots:** Supplied from a working BBS; the capture version and platform have not yet been independently recorded. Values, descriptions, and menu names shown are **site-specific examples**, not recommended defaults.

## Purpose

This guide introduces Mystic's User Editor, Security Level Editor, new-user defaults, and new-user questions. It explains how these features relate to account management and access control, then provides a **safe test workflow** for checking behavior. It does not prescribe universal security settings.

## Before You Begin

- Have authorized SysOp access to the Mystic Configuration Editor.
- Record the installed Mystic version, host operating system, and architecture.
- Have a verified backup before modifying production account or access settings.
- Prefer a disposable test BBS or a dedicated test account for permission experiments. Do not use an existing real person's account.
- Avoid publishing private account attributes, passwords, tokens, recovery data, IP addresses, or hostnames in screenshots.

For configuration access, the existing project guide describes running `./mystic -cfg` from the Mystic directory on Linux and `mystic -cfg` on Windows. Confirm command usage for your installed release. See [Starting Mystic](Starting-Mystic).

## 1. User Editor: Account Information

The User Editor contains multiple pages of account information and preferences. Its first page can show fields such as handle, real name, address, city, postal code, phone numbers, email, validation date, birthdate, and connection details.

![Mystic User Editor information page with personal values redacted](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/user-editor-information-redacted.png)

*Figure 1 — User Editor, Information page. The heading and sensitive values are deliberately replaced for publication; `EXAMPLE USER` is an editorial label.*

**Documentation practice:** Explain each field by purpose, but use a synthetic account whenever demonstrating edits. Publishing a complete real account record is not necessary to teach the workflow.

### Suggested account-review workflow

1. Open the Configuration Editor using the method supported by your Mystic release.
2. Locate the User Editor under the relevant editor/configuration area.
3. Select a **test** account and inspect its information page.
4. Confirm which fields are required for your own registration policy; avoid collecting information with no operational justification.
5. Record any changes made to the test account and verify they persist after reopening the editor.

**Verification required:** The exact navigation path, edit keystrokes, validation behavior, and persistent data format must be captured from the target release. Do not assume the screenshot alone proves any of these details.

## 2. Security Levels: Named Access Profiles

The Security Level Editor displays numerical levels and administrator-provided descriptions. The sample installation shows levels `20`, `80`, `200`, and `255`. Their descriptions are specific to that BBS and **must not** be treated as Mystic's standard roles.

![Mystic Security Levels list](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/security-levels-list.png)

*Figure 2 — Security Level Editor, list view. The numerical levels and descriptions reflect the demonstrated installation.*

![Mystic Security Level details](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/security-level-details.png)

*Figure 3 — Security-level detail fields, including per-day limits, ratios, flags, expiration options, and a starting menu.*

The detail screen includes the following classes of settings:

| Setting | What to examine |
|---|---|
| Description | Human-readable label assigned to the level |
| Time / Calls per Day | Session-time and login-related limits |
| Post/Call and Upload/Download Ratios | Activity-based restrictions where supported |
| Download and upload/download size limits | Transfer quotas or ratios, with units displayed by the editor |
| Start Menu | Menu selected by the level's configuration |
| Expiration fields | When a level or entitlement expires or changes |
| Access Flags 1 and 2 | Flag sets relevant to access checks |
| Hard Flag Upgrade | Flag-related behavior that needs version-specific verification |

**Important:** The effect of `0`, blank values, and individual flags is not established by these screenshots. Verify the behavior against the Mystic release before documenting `0` as unlimited, disabled, or any other specific rule.

## 3. User Editor: Effective Account Settings

The User Editor also exposes account-specific values, including a numeric **Security** field, **Flags #1**, **Flags #2**, session-time information, theme, starting menu, and related preferences.

![Mystic User Editor security page with account identity redacted](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/user-editor-security-redacted.png)

*Figure 4 — User Editor, Security/Settings page. The account name has been replaced. A displayed level of `20` is an example, not a recommended permission level.*

A useful documentation distinction is:

- **Security-level definitions** describe named levels and associated settings.
- **User-account settings** show values stored or displayed for an individual account.
- **Access-control strings (ACS)** are conditions used to decide whether an account can reach a particular resource.

The precise precedence, inheritance, and evaluation behavior between these features is **not yet verified** here. A dedicated ACS page should eventually include a known test expression and observed allowed/denied results for a specified Mystic version.

### Recommended verification matrix

| Test account | Configured level | Test resource | Expected | Observed |
|---|---|---|---|---|
| Example low-access user | Record value | Public menu item | Allowed | Pending |
| Example low-access user | Record value | Restricted menu item | Denied | Pending |
| Example elevated test user | Record value | Same restricted item | Allowed only if configured to permit it | Pending |

Do not use a live administrative account to test denial paths or lockout behavior.

## 4. New-User Defaults

The **New User Settings** editor displays initial values for incoming accounts, including whether new-user registration is allowed, an initial security value, starting message/file groups, and related defaults.

![Mystic New User Settings defaults](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/new-user-defaults.png)

*Figure 5 — New User Settings defaults. The displayed values are those of the example installation.*

For a safe setup, review which privileges a newly registered user receives **before** enabling public registration. Test access using a new disposable account rather than assuming the configured number is sufficient.

### Default-account test

1. Record the current new-user settings without altering them.
2. In a test environment, set the intended starting security level and starting areas.
3. Create a disposable new-user account through the normal login/registration path.
4. Inspect the account using the User Editor and compare the resulting values to the configured defaults.
5. Test access to a public area and a restricted area.
6. Record the outcome and restore the original settings if the test altered an existing environment.

## 5. New-User Registration Questions

Mystic can ask a number of questions during registration, and the example screen shows settings related to names, alias, email, location, birthday, gender, and other preferences. Additional settings affect the initial interface and message experience.

![Mystic New User Settings registration questions](https://raw.githubusercontent.com/Pequito/mystic-documentation/main/assets/wiki/phase-2/new-user-questions.png)

*Figure 6 — Example registration questions and interface defaults. An enabled question in this screenshot is not a recommendation to collect that information.*

Only request personal information that the BBS has a clear reason to collect and protect. A public technical guide should not imply that real name, street address, birthday, or gender collection is mandatory. Avoid using real registration responses in documentation.

## 6. Troubleshooting and Recovery

| Symptom | Initial checks |
|---|---|
| User cannot enter a menu | Inspect the item's access condition, account level/flags, and the actual loaded menu |
| New account has unexpected permissions | Compare New User Settings against the created account's values and logs |
| A security change appears ineffective | Confirm which account was edited, whether changes were saved, and whether the session was restarted |
| New-user flow requests unwanted data | Review New User Settings registration-question options |
| User loses access during a test | Restore the test account from known settings; do not experiment using the sole SysOp account |

**Rollback:** Preserve the original configuration values before any test. Revert changes in the test environment and verify that a known working SysOp login remains available. Do not claim a recovery method is verified until it has been rehearsed.

## Verification Record

```text
Mystic version:   Not yet recorded
Operating system: Not yet recorded
Architecture:     Not yet recorded
Date tested:      Pending
Tested by:        Pending
Result:           Needs verification
Notes:            UI captures reviewed; no access-control behavior independently reproduced
```

## Further Screenshots Needed

- A synthetic user-account creation or edit workflow (with the actual navigation keys)
- One ACS condition in a menu/base editor, plus allowed and denied runtime results
- A documented test account after registration, showing the applied default settings
- Version display for the installation used to take the screenshots

## Related Topics

- [Starting Mystic](Starting-Mystic)
- [Mystic Configuration System](Mystic-Configuration-System)
- [First SysOp Account](First-Sysop-Account)
- [Message Groups and Bases](Message-Groups-and-Bases)