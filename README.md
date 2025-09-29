# KNXT Workbench

This repository contains the necessary tooling to work on KNXT projects. It uses git submodules to manage multiple repositories in a single workspace.

## Repositories

- **knxt-api**: API specifications and schemas
- **knxt_referentiels**: Documentation and referential data

## Setup Instructions

### For New Users

1. Clone this repository with submodules:
   ```bash
   git clone --recursive git@github.com:KeeSystemOrg/knxt-workbench.git
   cd knxt-workbench
   ```

### For Existing Users

1. Clone the repository:
   ```bash
   git clone git@github.com:KeeSystemOrg/knxt-workbench.git
   cd knxt-workbench
   ```

2. Initialize and update submodules:
   ```bash
   git submodule init
   git submodule update
   ```

## Working with Submodules

### Quick Commands

| Action | Command |
|--------|---------|
| Work on submodule | `cd knxt-api` → make changes → `git add .` → `git commit` → `git push` |
| Update workspace | `cd ..` → `git add knxt-api` → `git commit` → `git push` |
| Get latest changes | `git submodule update --remote` |
| Check status | `git submodule status` |
| Switch submodule branch | `cd knxt-api` → `git checkout branch-name` |
| Update parent workspace | `cd ..` → `git add knxt-api` → `git commit` → `git push` |
| Check submodule branch | `cd knxt-api` → `git branch` |
| Configure default branch | `git config -f .gitmodules submodule.knxt-api.branch branch-name` |

### Updating Submodules

To update all submodules to their latest commits:
```bash
git submodule update --remote
```

To update a specific submodule:
```bash
git submodule update --remote knxt-api
git submodule update --remote knxt_referentiels
```

### Making Changes

1. Navigate to the submodule directory:
   ```bash
   cd knxt-api  # or knxt_referentiels
   ```

2. Make your changes and commit them in the submodule:
   ```bash
   git add .
   git commit -m "Your changes"
   git push
   ```

3. Return to the main workspace and commit the submodule update:
   ```bash
   cd ..
   git add knxt-api  # or knxt_referentiels
   git commit -m "Update knxt-api to latest version"
   git push
   ```

### Branch Management

Submodules are not locked to the main branch. You can switch branches within submodules:

```bash
# Switch to a different branch in submodule
cd knxt-api
git checkout feature/new-endpoint

# Update parent workspace to reflect branch change
cd ..
git add knxt-api
git commit -m "Switch knxt-api to feature/new-endpoint branch"
git push origin main
```

**Important**: The parent workspace records specific commit hashes, not branch names. Always commit branch changes in the parent workspace.

## Cursor IDE Integration

This workspace is optimized for Cursor IDE. Both repositories will be available in the file explorer, and you can:

- Navigate between repositories seamlessly
- Use Cursor's AI features across both codebases
- Maintain separate git histories for each repository
- Work on multiple repositories simultaneously

## Repository Structure

```
knxt-workbench/
├── knxt-api/           # API specifications
├── knxt_referentiels/  # Documentation and referentials
└── README.md          # This file
```

## Best Practices

1. **Always commit submodule changes twice**:
   - Once in the submodule
   - Once in the parent workspace

2. **Use descriptive commit messages**:
   - In submodule: "Add new API endpoint for user management"
   - In workspace: "Update knxt-api to include new user endpoint"

3. **Regular updates**: Run `git submodule update --remote` regularly to stay current

4. **Team coordination**: Communicate when you're updating submodules so team members know to pull changes

5. **Document branch changes**: Use clear commit messages when switching branches

6. **Coordinate with team**: Let others know when you're switching submodule branches

7. **Use consistent branching**: Consider using the same branch names across submodules

8. **Regular updates**: Run `git submodule update --remote` to stay current with branch changes
