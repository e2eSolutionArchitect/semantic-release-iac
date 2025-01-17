# Semantic Release Pipeline Setup Guide

Please refer working copy [here](https://github.com/TheSolutionArchitect/tf-aws-template-core-live/actions)

- **Step 1** : Creare ./.github/workflows/release.yml (with the below content or [refer here](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/.github/workflows/release-calling-workflow.yml)) in the repository where the release pipeline to setup. This workflow is calling a callable workflow from [here](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/.github/workflows/release-shared-workflow.yml). Currently both are in the same repository but usually 'callable workflow' should be in a separate shared repository. 
- **Step 2** : Create .releaserc file at repository root. refer to the file content [here](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/.releaserc)

Content of [release.yml](https://github.com/TheSolutionArchitect/github-actions-shared-workflows/blob/main/.github/workflows/release-calling-workflow.yml)
```
name: Release Calling Workflow
on:
  workflow_dispatch:
jobs:
  call-shared-workflow:
    uses: TheSolutionArchitect/github-actions-shared-workflows/.github/workflows/release-shared-workflow.yml@main
    
```
Commit and Push to the repository.

Go to 'Actions' > Select 'Release Calling Workflow' under the left panel 'All Workflows' >  Click 'Run Workflow'.

Please refer [Semantic Release guide here](https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/README.md)

**NOTE** : We don't need to add secret GITHUB_TOKEN explicitly under secrets or pass from calling workflow. GITHUB_TOKEN is inherited from GitHub by default. 
