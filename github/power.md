---
name: "github"
displayName: "Work with GitHub"
description: "Access GitHub repositories, issues, pull requests, and workflows with full MCP capabilities for repository management and CI/CD automation"
keywords: ["github", "git", "repository", "issues", "pull-requests", "actions", "ci-cd", "version-control", "code-review", "collaboration"]
author: "GitHub"
---

# Work with GitHub Power

The Work with GitHub Power provides comprehensive access to GitHub repositories and services through the Model Context Protocol (MCP). This power enables you to interact with GitHub repositories, manage issues and pull requests, run CI/CD workflows, and more, for streamlined development and collaboration.

## What Can You Do?

### 1. Repository Management
- Browse and search repositories
- Read and edit files in repositories
- View commit history and diffs
- Work with branches and tags
- Manage repository settings

**Example:** "Show me the recent commits in the main branch" or "List all branches in this repository"

### 2. Issues and Pull Requests
- Create, update, and close issues
- Manage pull requests
- Review code changes
- Add comments and labels
- Track project progress
g
**Example:** "Create an issue for the bug in authentication" or "Show me all open pull requests"

### 3. GitHub Actions
- View workflow runs and their status
- Access job logs and artifacts
- Monitor CI/CD pipelines
- Debug workflow failures

**Example:** "Show me the latest workflow run status" or "Get the logs for the failed build"

### 4. Read-Only Operations
- Safe querying without modification capabilities
- Perfect for auditing and monitoring
- No risk of accidental changes

**Example:** "List all issues created this month" (using github-readonly)

---

## Available MCP Configuration

This power is configured for full GitHub access according to your `mcp.json` file.
Edit `mcp.json` as needed to update these options.

### `github` - Full Access (from mcp.json)
- **MCP Server URL**: `https://api.githubcopilot.com/mcp/`
- **Headers**:
  ```json
  {
    "Authorization": "Bearer ${GITHUB_ACCESS_KEY}"
  }
  ```
- **Environment**: Set your token to the environment variable `GITHUB_ACCESS_KEY`
- **Use Case**: All GitHub repository management and CI/CD automation

**Example:**
```bash
export GITHUB_ACCESS_KEY=ghp_your_personal_access_token
```
You must ensure `${GITHUB_ACCESS_KEY}` is set to a valid GitHub Personal Access Token with the required scopes (e.g. `repo`, `workflow`).

---

## Quick Start

**Already have GitHub authentication configured?** Try these commands:

```
"List recent issues in this repository"
"Show me the latest pull requests"
"What workflow runs have failed recently?"
"Display the commit history for the last week"
```

---

## Onboarding

### Prerequisites

Before using the Work with GitHub Power, ensure you have:

1. **github-mcp-server** binary available in your PATH
   - Check: `github-mcp-server --version`
   - Install: Follow the installation instructions for your platform

2. **GitHub Personal Access Token**
   - Generate a token at: https://github.com/settings/tokens
   - Required scopes depend on your use case (e.g. repo, workflow)

### Step 1: Set Up Authentication

Set the `GITHUB_ACCESS_KEY` environment variable with your GitHub personal access token:

```bash
export GITHUB_ACCESS_KEY=ghp_your_token_here
```

For persistent configuration, add this to your shell profile (~/.bashrc, ~/.zshrc, etc.).

### Step 2: Start Using the Power

Once authentication is configured, you can immediately start using the power:
- "Show me open issues in my repository"
- "List the latest commits"
- "What's the status of the CI pipeline?"

---

## Common Workflows

### Repository Exploration
```
"Show me the directory structure of this repository"
"What files were changed in the last commit?"
"List all branches in this repository"
```

### Issue Management
```
"Create an issue titled 'Fix login bug' with description..."
"Show me all issues assigned to @username"
"Close issue #123 with a comment"
"Add label 'bug' to issue #456"
```

### Pull Request Operations
```
"List all open pull requests"
"Show me the diff for pull request #789"
"Get review comments for the latest PR"
"Check the CI status for pull request #101"
```

### CI/CD Monitoring
```
"Show me the latest workflow runs"
"What jobs failed in the last build?"
"Get the logs for job #12345"
"List all GitHub Actions workflows"
```

---

## Best Practices

### Security
- Use personal access tokens with minimal required scopes
- Never commit tokens to version control
- Rotate tokens regularly
- Use read-only configuration when write access isn't needed

### Efficiency
- Use specific configurations when appropriate
- Leverage filtering to reduce API calls
- Cache frequently accessed data

### Collaboration
- Add descriptive comments to issues and PRs
- Use labels consistently for organization
- Document workflow configurations
- Review changes before merging

---

## MCP Server Options

The github-mcp-server supports additional command-line options:

- `--gh-host`: Specify GitHub hostname (for GitHub Enterprise)
- `--log-file`: Path to log file for debugging
- `--read-only`: Restrict to read-only operations
- `--toolsets`: Comma-separated list of tool groups (default: all)
- `--dynamic-toolsets`: Enable dynamic toolsets
- `--enable-command-logging`: Log all command requests/responses

---

## Troubleshooting

### "Authentication Failed" Errors
- Verify your GitHub token is valid: Check at https://github.com/settings/tokens
- Ensure the token has required scopes for your operations
- Check that the `GITHUB_ACCESS_KEY` environment variable is set correctly

### "Rate Limit Exceeded"
- GitHub API has rate limits (5,000 requests/hour for authenticated requests)
- Wait for the rate limit to reset
- Consider using caching or reducing request frequency

### "Permission Denied"
- Verify your token has the necessary scopes
- Check repository access permissions
- Ensure you're authenticated as the correct user

---

## Learn More

- GitHub API Documentation: https://docs.github.com/en/rest
- GitHub MCP Server: https://github.com/github/github-mcp-server
- GitHub Personal Access Tokens: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

---

## Support

For issues with the Work with GitHub Power:
1. Verify your GitHub token is valid and has required scopes
2. Check that github-mcp-server is installed and accessible
3. Review the troubleshooting section above
4. Check the GitHub MCP server documentation for additional help
