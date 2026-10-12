# Contributing

Contributions to Mystic Documentation are welcome.

The goal is to build clear, practical, community-maintained documentation for Mystic BBS without simply reproducing existing manuals or release notes.

## Useful Contributions

Useful contributions include:

- Installation and upgrade procedures
- Configuration explanations
- FTN networking documentation
- Echomail and netmail examples
- BinkP, MUTIL, and FIDOPOLL procedures
- Message-base and file-base documentation
- Troubleshooting procedures
- Version-specific notes
- Tested examples
- Corrections to existing pages
- Diagrams and screenshots that clarify a workflow

## Writing Style

Prefer documentation that follows this sequence:

1. Explain the purpose.
2. Explain the relevant concepts.
3. Show the configuration or procedure.
4. Explain what should happen.
5. Show how to verify it.
6. Document known limitations or version-specific behavior.

Avoid presenting unverified assumptions as established behavior.

## Verification

When behavior may vary by Mystic version or operating system, record what was tested when possible:

```text
Mystic version:
Operating system:
Architecture:
Date tested:
Tested by:
Result:
Notes:
```

Use **Needs verification** when a page contains behavior that still requires testing.

## MPL Documentation

Language-level Mystic Programming Language material belongs in:

- https://github.com/Pequito/mystic-mpl-docs

General Mystic configuration and integration material belongs in this repository.

## Documentation Source

Wiki-style source pages are kept under `wiki/` so they remain reviewable through normal Git history, branches, and pull requests.
