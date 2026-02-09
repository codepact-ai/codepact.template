# CodePact Configuration Repository

This repository is the **central governance hub** for your organization, managed by [CodePact AI](https://codepact.ai). All governance policies, team configurations, and file distribution rules are defined here.

## How It Works

1. **Edit policies** in `codepact.yaml` (org baseline) or `teams/<slug>/codepact.yaml` (team overrides).
2. **Push to default branch** — CodePact detects the change automatically via webhook.
3. **Policies propagate** — effective policies are recalculated for all repositories.
4. **Files distribute** — any files in `files/` or `teams/<slug>/files/` are synced to target repos.

## Directory Structure

```
codepact/
├── codepact.yaml               # Organization baseline policy
├── files/                      # Org-wide file distribution
│   └── .github/CODEOWNERS      # Example: distributed to all repos
├── teams/
│   └── <team-slug>/
│       ├── codepact.yaml       # Team policy (inherits org baseline)
│       └── files/              # Team-specific file distribution
└── .teammap.yaml               # Team slug → ID mapping (auto-maintained)
```

## Key Settings

| Setting             | Values                    | Description                                    |
| ------------------- | ------------------------- | ---------------------------------------------- |
| `enforcement_mode`  | `audit`, `warn`, `enforced` | How violations are reported and handled       |
| `branch_protection` | nested config             | Rules for the default branch                   |
| `security`          | nested config             | Secret scanning, Dependabot, code scanning     |
| `file_distribution` | list of managed files     | Files to sync across repos (`sync`/`seed`/`pr`) |

## Three-Tier Override Hierarchy

1. **Repo-local** `codepact.yaml` — highest priority (preserved by default)
2. **Team policy** — `teams/<slug>/codepact.yaml`
3. **Org baseline** — root `codepact.yaml` (lowest priority)

## Support

For more information, visit the [CodePact Documentation](https://codepact.ai/docs).
