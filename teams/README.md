# Team Configurations

Each subdirectory corresponds to a GitHub team (by slug) and can contain:

```
teams/
└── <team-slug>/
    ├── codepact.yaml    # Team governance pact (inherits org baseline)
    └── files/           # Team-specific file distribution
```

## Creating a Team Pact

1. Create a directory named after your team's slug (e.g., `platform-engineering`)
2. Add a `codepact.yaml` with a pact that inherits the org baseline
3. Optionally add a `files/` directory for team-specific file distribution
4. Push to the default branch — CodePact picks it up automatically

## Example

See `example-team/` for a starter template.
