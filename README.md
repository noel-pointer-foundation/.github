# GitHub Actions Template: Add Issues to Project

This template repository provides a GitHub Actions workflow that automatically adds issues to an organization project board.

## What's Included

- **`.github/workflows/add-issues-to-project.yml`**: GitHub Actions workflow that triggers on issue events and adds issues to the specified project board

## Features

- Automatically adds issues to the Noel Pointer Foundation project board at https://github.com/orgs/noel-pointer-foundation/projects/1
- Triggers on issue opened, reopened, and transferred events
- Uses the official `actions/add-to-project@v1.0.2` action

## Setup Instructions

### 1. Use This Template

1. Click "Use this template" button on GitHub
2. Create a new repository from this template

### 2. Configure Secrets

The workflow requires a Personal Access Token (PAT) to add issues to the organization project:

1. Go to your repository's **Settings** > **Secrets and variables** > **Actions**
2. Click **New repository secret**
3. Name: `ADD_TO_PROJECT_PAT`
4. Value: A GitHub Personal Access Token with the following permissions:
   - `project` scope (to manage project boards)
   - `repo` scope (to access repository issues)

### 3. Customize (Optional)

To use a different project board, edit `.github/workflows/add-issues-to-project.yml` and update the `project-url` value.

## How It Works

When an issue is:
- Opened
- Reopened 
- Transferred to the repository

The workflow automatically runs and adds the issue to the specified project board.

## Requirements

- GitHub repository with Issues enabled
- `ADD_TO_PROJECT_PAT` secret configured
- Target project board must be accessible with the provided PAT

## Troubleshooting

- **Workflow fails**: Check that the `ADD_TO_PROJECT_PAT` secret is configured correctly
- **Issues not added**: Verify the PAT has the required `project` and `repo` scopes
- **Permission errors**: Ensure the PAT owner has access to the target project board