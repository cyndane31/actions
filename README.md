# cyndane31/actions

Central repository for reusable GitHub Actions and Workflows.

## Usage

Reference a workflow from this repo in any of your own repositories:

```yaml
jobs:
  sync-files:
    uses: cyndane31/actions/.github/workflows/sync-upstream-files.yml@main
    with:
      upstream_repo: cyndane31/proxmox-packer-templates
      upstream_branch: main
      file_map: |
        templates/packer.json:packer.json
        docs/packer-templates.md:README.md
        ansible/roles/common/tasks/main.yml:ansible/roles/common/tasks/main.yml
```

## Best Practices

- Store reusable workflows in `.github/workflows/`.
- Name files in `kebab-case` by their function, e.g. `sync-upstream-files.yml`.
- Document usage and parameters in this README.
- Use a central actions repo for maintainability and sharing across multiple projects.

## Security

If you need to fetch files from private repos, see [GitHub Actions documentation on authentication](https://docs.github.com/en/actions/security-guides/automatic-token-authentication).
