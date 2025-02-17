---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "gitea_git_hook Resource - terraform-provider-gitea"
subcategory: ""
description: |-
  gitea_git_hook manages git hooks on a repository.
---

# gitea_git_hook (Resource)

`gitea_git_hook` manages git hooks on a repository.

## Example Usage

```terraform
resource "gitea_org" "test_org" {
  name = "test-org"
}

resource "gitea_repository" "org_repo" {
  username = gitea_org.test_org.name
  name     = "org-test-repo"
}

resource "gitea_git_hook" "org_repo_post-receive" {
  name    = "post-receive"
  user    = gitea_org.test_org.name
  repo    = gitea_repository.org_repo.name
  content = file("${path.module}/post-receive.sh")
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `content` (String) Content of the git hook
- `name` (String) Name of the git hook to configure
- `repo` (String) The repository that this hook belongs too.
- `user` (String) The user (or organisation) owning the repo this hook belongs too

### Read-Only

- `id` (String) The ID of this resource.


