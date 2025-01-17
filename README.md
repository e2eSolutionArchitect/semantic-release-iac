# Semantic Release for Infra as Code ( Terraform )

**IMPORTANT**
To avoid creating release version on every commit/pull request, please keep the release pipeline as 'workflow_dispatch'. As it is in .github/workflow/release.yml


# Semantic Release

To maintain consistency and ensure smooth Semantic Release automation, developers should follow a standardized commit message format. The commit messages should follow the **Conventional Commits** specification.


# How to Implement Semantic Release - [Please refer here](https://github.com/TheSolutionArchitect/github-actions-shared-workflows/blob/main/release-pipeline-setup.md)

NOTE: To avoid creating a release version on every commit/pull request, please keep the release pipeline as 'workflow_dispatch'. As it is in .github/workflow/release.yml

## Here’s a guide for developers to write commit messages:

---

### **Git Commit Message Format**

A commit message should have the following structure:

```
<type>(<scope>): <short description>
```

---

### **Types**
The `<type>` defines the purpose of the change. Here are the common types:

- **feat**: A new feature.
- **fix**: A bug fix.
- **docs**: Changes to documentation only.
- **style**: Code style changes (white-space, formatting, etc.) that do not affect functionality.
- **refactor**: Code changes that neither fix a bug nor add a feature.
- **perf**: Performance improvements.
- **test**: Adding or modifying tests.
- **build**: Changes to the build process or dependencies.
- **ci**: Changes to CI/CD pipeline configuration.
- **chore**: Maintenance tasks that don't modify `src` or `test` files.
- **revert**: Reverts a previous commit.

---

### **Examples of Valid Commit Messages**

1. **Feature**:
   ```
   feat(auth): Add JWT-based authentication
   ```

2. **Bug Fix**:
   ```
   fix(ui): Correct button alignment issue in header
   ```

3. **Documentation**:
   ```
   docs: Update README with installation instructions
   ```

4. **Breaking Change**:
   ```
   feat(api): Migrate user endpoint to v2

   BREAKING CHANGE: The `/user` endpoint has been replaced with `/v2/user`.
   ```

5. **Chore**:
   ```
   chore(deps): Update Terraform AWS provider to v3.2.0
   ```

---

### **Why This Matters**
- Following this structure allows Semantic Release to generate meaningful version numbers (major, minor, patch) and changelogs automatically.
- It ensures clarity and consistency across the team, making it easier to review and trace changes.
