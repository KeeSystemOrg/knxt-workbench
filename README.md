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
