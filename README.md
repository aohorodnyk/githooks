# Git Hooks

In this repo I'll collect custom git hooks that I use for my projects. Feel free to use them and contribute by creating a ticket or PR.

## Git hook prepare-commit-msg

`prepare-commit-msg` is a hook that adds the issue number to the commit message.

It supports the following formats:

* Jira tickets (PROJ-123):
  * `feature/PROJ-123-description`
  * `PROJ-123`
  * `prefix-PROJ-123-description`
  * `prefix-PROJ-123`
  * `PROJ-123-description`
* Version (only three digits: 0.0.1, 123.23.23, 1.231.2, etc.):
  * `v1.2.3`
  * `1.1.1`
  * `myversion1.2.3withsometext`
  * `feature/v1.2.3-ewrfef`
* GitHub issues (123, 1, 34), the issue number MUST be at the start of the mssage:
  * `123`
  * `123-description`
  * `feature/123-description`

## Contribution

### Branch Name

Before you start the contribution, make sure that you are on the correct branch. Branch name should start from the issue number dash and short explanation with spaces replaced by underscores. Example:

- `OD-1-my_feature`
- `OD-123-fix_bug`
- `OD-2343452-my_important_pr`

### Commit Message Format

Commit message should start with the issue number with `#` like `#123` or the issue id in brackets (if Jira or related project is used), like `[PROJ-123]`.

To simplify the development process, use please githooks from `.githooks` directory. It will automatically add the issue number to the commit message. If you don't want to use the githooks, please add the issue number manually.

Commit message should describe the changes in present tense. Example: **Add `.gitignore` file**.

### Git Hook

To configure the git hook, you need to simply run the command: `git config core.hooksPath hooks`

It will configure the git hook to run the `pre-commit` scripts. Source code of the hook is in `hooks/prepare-commit-msg`.

### Commit Signing

All **tags and commits** MUST be signed with **SSH (preferable)** or _GPG_ key. Read more [About commit signature verification](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification).

### Pull Request

All features and bug fixes should be done in the separate branch and delivered to the `main` branch via the pull request.
Pull request should be created from the branch with the same name as the issue number. Example: `1-my_feature`.

[nvm]: https://github.com/nvm-sh/nvm
[vscode]: https://code.visualstudio.com/
