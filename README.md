# Pull Request Action

[![Action test on Ubuntu](https://github.com/GuillaumeFalourd/pull-request-action/actions/workflows/ubuntu_action_test.yml/badge.svg)](https://github.com/GuillaumeFalourd/pull-request-action/actions/workflows/ubuntu_action_test.yml) [![Action test on MacOS](https://github.com/GuillaumeFalourd/pull-request-action/actions/workflows/macos_action_test.yml/badge.svg)](https://github.com/GuillaumeFalourd/pull-request-action/actions/workflows/macos_action_test.yml) [![Action test on Windows](https://github.com/GuillaumeFalourd/pull-request-action/actions/workflows/windows_action_test.yml/badge.svg)](https://github.com/GuillaumeFalourd/pull-request-action/actions/workflows/windows_action_test.yml)

![](https://user-images.githubusercontent.com/22433243/157692326-2e75f43d-e563-4fa9-8947-67c06e4e469f.png)

☞ Github Actions to create pull request using Github CLI ⤵️ 

_**Note**: This action is supported on **all runners** operating systems (`ubuntu`, `macos`, `windows`)_

_Inspired from [https://github.com/repo-sync/pull-request](https://github.com/repo-sync/pull-request)_

## 📝 Features

- Create pull requests

- Add reviewers, assignees, labels, or milestones

- Customize pull request title and body

- Fail silently when a pull request already exists

## 📚 Usage

- This action uses [Github CLI](https://cli.github.com/) to create a Pull Request.

- [According to the documentation](https://docs.github.com/en/actions/using-workflows/using-github-cli-in-workflows), to authenticate on the workflow using Github CLI, you need to set the GITHUB_TOKEN context variable as environment variable.

- Note that if you need specific permissions, you can also set a [Personal Access Token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) instead.

### Minimum configurations

```yaml
    - uses: GuillaumeFalourd/pull-request-action@v1
      with:
        destination_branch: "main"
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### Full configurations

```yaml
    - uses: GuillaumeFalourd/pull-request-action@v1
      uses: repo-sync/pull-request@v2
      with:
        source_branch: "main"                             # If blank, default: triggered branch
        destination_branch: "feature"                     # If blank, default: main
        pr_title: "Pulling ${{ github.ref }} into main"   # Title of pull request
        pr_body: "An automated PR"                        # Full markdown support, requires pr_title to be set
        pr_reviewer: "john, britney"                      # Comma-separated list (no spaces)
        pr_assignee: "john"                               # Comma-separated list (no spaces)
        pr_label: "auto-pr"                               # Comma-separated list (no spaces)
        pr_milestone: "Milestone 1"                       # Milestone name
        pr_draft: true                                    # Creates pull request as draft
        pr_allow_empty: true                              # Creates pull request even if there are no changes
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}         # Can use PAT as secret
```

## 🤝 Contributing

☞ If you're interested in contributing to this repository, please follow the [guidelines](https://github.com/GuillaumeFalourd/pull-request-action/blob/main/CONTRIBUTING.md)

## 🏅 Licensed

☞ This repository uses the [Apache License 2.0](https://github.com/GuillaumeFalourd/pull-request-action/blob/main/LICENSE)

<!-- ### Contribuidores

<a href="https://github.com/GuillaumeFalourd/pull-request-action/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=GuillaumeFalourd/pull-request-action" />
</a>

(Criado com [contributors-img](https://contrib.rocks)) -->
