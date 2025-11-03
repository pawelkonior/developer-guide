## Branch Types and Naming Conventions

| **Branch Type** | **Example**                      | **Description** |
|------------------|----------------------------------|------------------|
| `feature/`       | `feature/add-login-endpoint`     | New functionality or feature implementation |
| `fix/`           | `fix/user-auth-bug`              | Bug fix (non-production) |
| `refactor/`      | `refactor/cleanup-services`      | Technical code changes that do not alter behavior |
| `chore/`         | `chore/setup-pre-commit`         | Maintenance tasks, CI/CD setup, dependency updates |
| `docs/`          | `docs/add-api-readme`            | Documentation updates or additions |
| `test/`          | `test/add-unit-tests`            | Adding or improving test coverage |
| `release/`       | `release/2.0.0`                  | Preparing a new production release |
| `hotfix/`        | `hotfix/fix-prod-error`          | Urgent fix applied directly to production |


## Commands:

## 🚀 GitFlow Command List

| **Command** | **Description** |
|--------------|-----------------|
| `git flow init` | Initialize GitFlow in the current repository (sets up main/develop branches). |
| `git flow feature start <name>` | Create a new feature branch from `develop`. |
| `git flow feature publish <name>` | Push the feature branch to the remote repository. |
| `git flow feature pull origin <name>` | Pull an existing remote feature branch. |
| `git flow feature finish <name>` | Merge the feature branch back into `develop` and delete it locally. |
| `git flow bugfix start <name>` | Create a new bugfix branch from `develop`. |
| `git flow bugfix publish <name>` | Push the bugfix branch to the remote repository. |
| `git flow bugfix finish <name>` | Merge the bugfix branch into `develop` and delete it locally. |
| `git flow release start <version>` | Create a release branch from `develop` for preparing a new version. |
| `git flow release publish <version>` | Push the release branch to the remote repository. |
| `git flow release finish <version>` | Merge the release into `main` and `develop`, tag it, and delete the branch. |
| `git flow hotfix start <version>` | Create a hotfix branch from `main` to fix production issues. |
| `git flow hotfix publish <version>` | Push the hotfix branch to the remote repository. |
| `git flow hotfix finish <version>` | Merge the hotfix into both `main` and `develop`, tag it, and delete the branch. |
| `git flow support start <version>` | Create a support branch for maintaining older releases. |
| `git flow support publish <version>` | Push the support branch to the remote repository. |
| `git flow support finish <version>` | Merge and close the support branch (rarely used). |
| `git flow config` | Show the current GitFlow configuration (branch prefixes, etc.). |
| `git flow version` | Display the installed GitFlow version. |
| `git flow help` | Show the GitFlow help menu with all available commands. |