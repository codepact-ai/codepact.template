# Org-Wide File Distribution

Place files here to distribute them across **all** repositories in your organization.

Files mirror their destination paths. For example:

```
files/
├── .github/
│   ├── CODEOWNERS           → distributed to .github/CODEOWNERS in each repo
│   └── pull_request_template.md
└── .editorconfig            → distributed to .editorconfig in each repo
```

## Distribution Modes

Configure distribution behavior in `codepact.yaml` under `file_distribution`:

| Mode   | Behavior                                        |
| ------ | ----------------------------------------------- |
| `pr`   | Opens a Pull Request for each change (default)  |
| `sync` | Pushes directly to the default branch           |
| `seed` | Creates the file once; skips if it already exists |

## Priority

Org-level files have the **lowest priority** in the three-tier hierarchy:

1. Repo-local files (highest — preserved by default)
2. Team-level files (`teams/<slug>/files/`)
3. **Org-level files** (this directory)
