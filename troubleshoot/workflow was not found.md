Error reference https://github.com/e2eSolutionArchitect/terraform-aws-remote-backend/actions/runs/12829739375

Error
```
Invalid workflow file: .github/workflows/release-calling.yml#L6
error parsing called workflow
".github/workflows/release-calling.yml"
-> "TheSolutionArchitect/github-actions-shared-workflows/.github/workflows/release-shared-workflow.yml@main"
: workflow was not found. See https://docs.github.com/actions/learn-github-actions/reusing-workflows#access-to-reusable-workflows for more information.
```

Solution

# :rotating_light: IMPORTANT: :rotating_light:
## Allow Access Permission
Go to Shared workflow repository 'Settings' > Actions > General
Select 'Accessible from repositories owned by the user '<GitHubUser/GitHubOrg>''

It will allow other repositories to access the shared workflow. Shared workflow should be centralized in a shared repository. 
Else the calling workflow will give ERROR : 'workflow was not found'

## Allow Workflow Permission
Select 'Read and write permissions'
Select 'Allow GitHub Actions to create and approve pull requests'

Make sure calling and callable (shared) workflows , both are under same GitUser or same GitOrg. It can't access cross GitOrg or GitUser.
