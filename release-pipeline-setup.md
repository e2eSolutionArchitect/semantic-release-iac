# Semantic Release Pipeline Setup Guide

Please refer working copy [here](https://github.com/e2eSolutionArchitect/semantic-release-iac/actions)

- **Step 1** : Creare ./.github/workflows/release.yml (with the below content or [refer here](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/.github/workflows/release-calling-workflow.yml)) in the repository where the release pipeline to setup. This workflow is calling a callable workflow from [here](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/.github/workflows/release-shared-workflow.yml). Currently both are in the same repository but usually 'callable workflow' should be in a separate shared repository. 
- **Step 2** : Create .releaserc file at repository root. refer to the file content [here](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/.releaserc)

Content of [release.yml](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/.github/workflows/release-calling-workflow.yml)
```
name: Release Calling Workflow
on:
  workflow_dispatch:
jobs:
  call-shared-workflow:
    uses: e2eSolutionArchitect/semantic-release-iac/.github/workflows/release-shared-workflow.yml@main
```
Commit and Push to the repository.

Go to 'Actions' > Select 'Release Calling Workflow' under the left panel 'All Workflows' >  Click 'Run Workflow'.

Please refer [Semantic Release guide here](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/README.md)

**NOTE** : We don't need to add secret GITHUB_TOKEN explicitly under secrets or pass from calling workflow. GITHUB_TOKEN is inherited from GitHub by default. 

# :rotating_light: IMPORTANT: :rotating_light:
## Allow Access Permission
Go to Shared workflow repository 'Settings' > Actions > General
Select 'Accessible from repositories owned by the user '<GitHubUser/GitHubOrg>''

It will allow other repositories to access the shared workflow. Shared workflow should be centralized in a shared repository. 
Else the calling workflow will give ERROR : 'workflow was not found'

## Allow Workflow Permission
Select 'Read and write permissions'
Select 'Allow GitHub Actions to create and approve pull requests'

## Same Repository
```
uses: ./.github/workflows/release-shared-workflow.yml
```

## Different Repository
```
uses: <GitUser>/<GitRepositoryName>/.github/workflows/<workflow yml file name>@<ref>
# {ref} could be branch name, release tag, Commit SHA

uses: e2eSolutionArchitect/semantic-release-iac/.github/workflows/release-shared-workflow.yml@main
uses: e2eSolutionArchitect/semantic-release-iac/.github/workflows/release-shared-workflow.yml@1.0.0
```
