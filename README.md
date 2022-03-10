# Pull Request Action

☞ Github Actions to create pull request ⤵️ 

_**Note**: This action is supported on **all runners** operating systems (`ubuntu`, `macos`, `windows`)_

Inspired from [https://github.com/repo-sync/pull-request](https://github.com/repo-sync/pull-request)
## 📚 Usage

### Minimum

```yaml
    - uses: GuillaumeFalourd/pull-request-action@v1
      with:
        destination_branch: "main"
        github_token: ${{ secrets.GITHUB_TOKEN }}
```

### Maximum

```yaml
    - name: pull-request
      uses: GuillaumeFalourd/pull-request-action@v1
      uses: repo-sync/pull-request@v2
      with:
        source_branch: ""                                 # If blank, default: triggered branch
        destination_branch: "main"                        # If blank, default: main
        pr_title: "Pulling ${{ github.ref }} into main"   # Title of pull request
        pr_body: "An automated PR"                        # Full markdown support, requires pr_title to be set
        pr_template: ".github/PULL_REQUEST_TEMPLATE.md"   # Path to pull request template, requires pr_title to be set, excludes 
        pr_reviewer: "john, britney"                      # Comma-separated list (no spaces)
        pr_assignee: "john"                               # Comma-separated list (no spaces)
        pr_label: "auto-pr"                               # Comma-separated list (no spaces)
        pr_milestone: "Milestone 1"                       # Milestone name
        pr_draft: true                                    # Creates pull request as draft
        pr_allow_empty: true                              # Creates pull request even if there are no changes
        github_token: ${{ secrets.GITHUB_TOKEN }}         # If blank, default: GITHUB_TOKEN (can use PAT)
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
