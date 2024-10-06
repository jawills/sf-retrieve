# Salesforce Retrievement Github Action

Retrive Salesforce metadata using the SF CLI and commit to a branch

## Inputs

```yml
SFDX_AUTH_URL:
  description: "The auth url tied to your deployment environment"
  type: string
  required: true
BRANCH_NAME:
  description: "The name of the branch you want to backup the code to"
  type: string
  required: true
GITHUB_USER_NAME:
  description: "Name tied to the git deployments"
  type: string
  default: "github-actions[bot]"
GITHUB_USER_EMAIL:
  description: "Email tied to the git deployments"
  type: string
  default: "github-actions[bot]@users.noreply.github.com"
SOURCE_DIR:
  description: "File paths for source to retrieve from the org. The supplied paths can be to a single file (in which case the operation is applied to only one file) or to a folder (in which case the operation is applied to all source files in the directory and its subdirectories)."
  type: string
METADATA:
  description: "Metadata component names to retrieve. Wildcards (`*`) supported as long as you use quotes, such as `ApexClass:MyClass*`."
  type: string
MANIFEST_DIR:
  description: "File path for the manifest (package.xml) that specifies the components to retrieve. If you specify this parameter, don't specify METADATA or SOURCE_DIR"
  type: string
IGNORE_CONFLICTS:
  description: "Ignore conflicts and retrieve and save files to your local filesystem, even if they overwrite your local changes. This flag applies only to orgs that allow source tracking. It has no effect on orgs that don't allow it, such as production orgs."
  type: boolean
```

## Getting the SFDX Auth URL

To get the `SFDX_AUTH_URL`, enter the following command in your terminal:

```bash
sf org display --verbose --json -o <MY_TARGET_ORG_ALIAS>
```

Copy down the value of `sfdxAuthUrl` for later.

## Usage

You can see how these work by checking my [write-up]() or [YouTube video]().
