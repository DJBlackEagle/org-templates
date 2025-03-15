# Welcome to 'Template for a new repository' <!-- omit in toc -->

Default repository for community health files.

## Table of Contents <!-- omit in toc -->

- [Benefits of this repository?](#benefits-of-this-repository)
- [How to use to this repository](#how-to-use-to-this-repository)
- [Getting started](#getting-started)
  - [Folder](#folder)
  - [Dependabot configuration](#dependabot-configuration)
  - [GitHub Action `actions/stale`](#github-action-actionsstale)
  - [GitHub Action `micnncim/action-label-syncer`](#github-action-micnncimaction-label-syncer)
    - [Explanation configuration Settings](#explanation-configuration-settings)
    - [Explanation of the label settings](#explanation-of-the-label-settings)
  - [Branch Rule Sets](#branch-rule-sets)
  - [Template Variables](#template-variables)

## Benefits of this repository?

This repository is used as a template, for new repositories on GitHub. So thats not all must created by scratched. 😀

## How to use to this repository

You can clone this repository or download it as archive.

Clone via SSH

```sh
git clone git@github.com:DJBlackEagle/org-templates.git
```

Clone via HTTPS

```sh
git clone https://github.com/DJBlackEagle/org-templates.git
```

Clone via GitHub CLI

```sh
gh repo clone DJBlackEagle/org-templates
```

As Zip archive

```text
https://github.com/DJBlackEagle/org-templates/archive/refs/heads/main.zip
```

## Getting started

### Folder

- `templates/repository` is for new repositories and have all files which is needed (README.md etc.).

### Dependabot configuration

You need to edit the `dependabot.yml` file and configure to update your dependencies.

### GitHub Action `actions/stale`

The GitHub Action `actions/stale` is used to automatically mark inactive issues and pull requests in a repository as "stale" and optionally close them. It helps keep the repository clean and organized by highlighting topics that show no active discussion or progress.

Here are the key configurations for the GitHub Action `actions/stale` explained:

1. **repo-token:**  
   Authentication token required to interact with the repository, typically `${{ secrets.GITHUB_TOKEN }}`.
2. **days-before-issue-stale:**  
   Number of inactive days before an issue is marked as "stale."
3. **days-before-issue-close:**  
   Number of days after an issue is marked "stale" before it is closed.
4. **days-before-pr-stale:**  
   Number of inactive days before a pull request (PR) is marked as "stale."
5. **days-before-pr-close:**  
   Number of days after a pull request is marked "stale" before it is closed.
6. **remove-stale-when-updated:**  
   If set to `true`, the "stale" label is removed if activity occurs on a marked issue or PR.
7. **stale-issue-label:**  
   Label applied to issues that are marked as "stale" (e.g., "stale").
8. **exempt-issue-labels:**  
   Comma-separated list of labels that prevent issues from being marked as "stale."
9. **stale-issue-message:**  
   Message posted as a comment when an issue is marked as "stale."
10. **close-issue-message:**  
    Message posted as a comment when an issue is closed due to inactivity.
11. **stale-pr-label:**  
    Label applied to pull requests that are marked as "stale" (e.g., "stale").
12. **exempt-pr-labels:**  
    Comma-separated list of labels that prevent pull requests from being marked as "stale."
13. **stale-pr-message:**  
    Message posted as a comment when a pull request is marked as "stale."
14. **close-pr-message:**  
    Message posted as a comment when a pull request is closed due to inactivity.

The configuration can be found at: `templates/repository/.github/workflows/stale.yml`.

### GitHub Action `micnncim/action-label-syncer`

#### Explanation configuration Settings

Here are the key configuration settings for using the GitHub Action:

1. **manifest:**  
   The path to the YAML file containing the label definitions (default: `.github/labels.yml`).
2. **github-token:**  
   The GitHub authentication token, typically `${{ secrets.GITHUB_TOKEN }}`.
3. **dry-run:** *(optional)*  
   Defaults to `false`. If set to `true`, the action runs in simulation mode and does not make any actual changes.
4. **prune:** *(optional)*  
   Defaults to `true`. If enabled, labels not defined in the `manifest` file are removed from the repository.
5. **allow-added-labels:** *(optional)*  
   Defaults to `false`. If set to `true`, labels can be added manually without being removed during synchronization.
6. **log-level:** *(optional)*  
   Sets the verbosity of the logs. Can be `info`, `warn`, or `debug` (default: `info`).

#### Explanation of the label settings

1. **name:**  
   The name of the label (e.g., `bug`, `documentation`).
2. **description:**  
   A short description of the label explaining its purpose (e.g., "Something isn't working").
3. **color:**  
   The color of the label in hexadecimal format without `#` (e.g., `d73a4a` for red).
4. **prune:** *(optional)*  
   Defaults to `true`. Specifies whether labels not defined in the YAML file should be removed from the repository.
5. **aliases:** *(optional)*  
   An array of alternative names for a label that will be treated as substitutes for the main label.

### Branch Rule Sets

For detailed information about the branch rule sets, please refer to the [Branch Rule Sets Documentation](./github/branch-rulesets/README.md).

### Template Variables

Some files, which have a package name, URL in there. For this, exists some template variables. So you need only search and replace. 😀

List of the template variables:

| Template Variable                   | Example                                                                          | Description                                                                              |
| ----------------------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| { TPL^ASSIGNEE_DEPENDABOT }         | MyAccount                                                                        | The default assignee, then the dependabot makes a pull request.                          |
| { TPL^ASSIGNEE_ISSUE }              | MyAccount                                                                        | The default assignee for new issues. It's stays in the issue template files.             |
| { TPL^DATE_CURRENT_YEAR }           | 2025                                                                             | The current year (like for Copyright).                                                   |
| { TPL^EMAIL_ADDRESS_COD }           | <test@localhost.local>                                                           | The e-mail address in 'Code of Conduct'.                                                 |
| { TPL^EMAIL_ADDRESS_OWNER }         | <test@localhost.local>                                                           | The e-mail address of the owner of this project and repository.                          |
| { TPL^EMAIL_ADDRESS_SECURITY }      | <test@localhost.local>                                                           | The e-mail address for reporting security issues related to this project and repository. |
| { TPL^EMAIL_NAME_COD }              | My name                                                                          | The e-mail address in 'Code of Conduct'.                                                 |
| { TPL^EMAIL_NAME_SECURITY }         | My name                                                                          | The e-mail address for reporting security issues related to this project and repository. |
| { TPL^FILE_MD_CHANGELOG }           | CHANGELOG.md                                                                     | The filename of the changelog.                                                           |
| { TPL^FILE_MD_CODE_OF_CONDUCT }     | CODE_OF_CONDUCT.md                                                               | The filename of the 'Code of Conduct'.                                                   |
| { TPL^FILE_MD_CONTRIBUTING }        | CONTRIBUTING.md                                                                  | The filename of the contributing.                                                        |
| { TPL^FILE_MD_DEVELOPMENT }         | DEVELOPMENT.md                                                                   | The filename of the development.                                                         |
| { TPL^FILE_MD_LICENSE }             | LICENSE.md                                                                       | The filename of the license.                                                             |
| { TPL^FILE_MD_README }              | README.md                                                                        | The filename of the readme.                                                              |
| { TPL^FILE_MD_SECURITY }            | SECURITY.md                                                                      | The filename of the security.                                                            |
| { TPL^PACKAGE_FULLNAME }            | @MyAccount/my-new-project                                                        | The full package name of this project.                                                   |
| { TPL^PACKAGE_FULLNAME_MINUSMINUS } | @MyAccount/my--new--project                                                      | The full package name of this project (if - exists, then do double --).                  |
| { TPL^PROJECT_OWNER_NAME }          | Max Mustermann                                                                   | The owner name of the project.                                                           |
| { TPL^URL_ACTIONS }                 | <https://localhost/MyAccount/my-new-project/actions>                             | The URL to the GitHub actions.                                                           |
| { TPL^URL_CODESTYLE }               | <https://localhost/MyAccount/my-new-project>                                     | The URL to the Code-Style repository.                                                    |
| { TPL^URL_COMMITS }                 | <https://localhost/MyAccount/my-new-project/commits/main>                        | The URL to the commit of the GIT repository.                                             |
| { TPL^URL_GIT }                     | <https://localhost/MyAccount/my-new-project>                                     | The URL to the GIT repository.                                                           |
| { TPL^URL_ISSUE_LIST }              | <https://localhost/MyAccount/my-new-project/issues>                              | The URL to the list of issues.                                                           |
| { TPL^URL_ISSUE_NEW }               | <https://localhost/MyAccount/my-new-project/issues/new/choose>                   | The URL of creating a new issue.                                                         |
| { TPL^URL_MD_CHANGELOG }            | <https://localhost/MyAccount/my-new-project/blob/main/CHANGELOG.md>              | The URL to the changelog.                                                                |
| { TPL^URL_MD_CODE_OF_CONDUCT }      | <https://localhost/MyAccount/my-new-project/blob/main/CODE_OF_CONDUCT.md>        | The URL to the 'Code of Conduct' file.                                                   |
| { TPL^URL_MD_CONTRIBUTING }         | <https://localhost/MyAccount/my-new-project/blob/main/CONTRIBUTING.md>           | The URL to the contributing file.                                                        |
| { TPL^URL_MD_DEVELOPMENT }          | <https://localhost/MyAccount/my-new-project/blob/main/DEVELOPMENT.md>            | The URL to the development.                                                              |
| { TPL^URL_MD_LICENSE }              | <https://localhost/MyAccount/my-new-project/blob/main/LICENSE.md>                | The URL to the license file.                                                             |
| { TPL^URL_MD_README }               | <https://localhost/MyAccount/my-new-project/blob/main/README.md>                 | The URL to the readme.                                                                   |
| { TPL^URL_MD_SECURITY }             | <https://localhost/MyAccount/my-new-project/blob/main/SECURITY.md>               | The URL to the security file.                                                            |
| { TPL^URL_NPMJS_PACKAGE }           | <https://www.npmjs.com/package/scope/my-new-project>                             | Ther URL to the NPM package on npm.                                                      |
| { TPL^URL_PULLREQUEST }             | <https://localhost/MyAccount/my-new-project/pulls>                               | The URL to the pull requests.                                                            |
| { TPL^URL_VULNERABILITY }           | <https://localhost/MyAccount/my-new-project/security>                            | The URL to the vulnerability.                                                            |
| { TPL^URL_VULNERABILITY_NEW }       | <https://localhost/MyAccount/my-new-project/security/advisories/new>             | The URL of creating a new vulnerability.                                                 |
| { TPL^URL_WORKFLOW_CODEQL }         | <https://localhost/MyAccount/my-new-project/actions/workflows/WORKFLOW_NAME.yml> | The GitHub workflow URL. WORKFLOW_NAME stays for the name of the workflow.               |
| { TPL^URL_WORKFLOW_CQAT }           | <https://localhost/MyAccount/my-new-project/actions/workflows/WORKFLOW_NAME.yml> | The GitHub workflow URL. WORKFLOW_NAME stays for the name of the workflow.               |
| { TPL^USER_CODE_OWNER }             | @MyAccount                                                                       | The 'Code Owner' of the repository (full).                                               |
