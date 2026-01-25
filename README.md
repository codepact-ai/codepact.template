# CodePact Configuration Repository

This repository stores the governance configuration for your organization. CodePact uses the `codepact.yaml` file in this repository as the **Organization Baseline**.

## How it works

1.  **Modify Policies**: Edit `codepact.yaml` to change governance rules (e.g., increase required approvals, enable strict status checks).
2.  **Pull Request**: Create a Pull Request with your changes.
3.  **Review & Merge**: once merged, CodePact will detect the change.
4.  **Propagation**: CodePact will automatically propose updates to the `codepact.yaml` file in all managed repositories to match this baseline.

## File Structure

- `codepact.yaml`: The main configuration file defining policies.

## Key Settings

- `enforcement_mode`:
    - `audit`: Violations are reported but not blocked (good for starting out).
    - `enforce`: Violations are actively corrected (e.g., branch protection is re-applied if changed).

- `branch_protection`: Defines the rules for the default branch (e.g., `main` or `master`).

## Support

For more information, visit the [CodePact Documentation](https://codepact.ai/docs).
