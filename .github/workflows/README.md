# GitHub Actions for AIMER

## Claude Code Action (`claude.yml`)

This workflow enables Claude Code to respond to mentions in issues and pull requests. When you mention `@claude` in a comment, Claude will analyze the context and provide assistance.

### Usage:
- In any issue or PR, mention `@claude` followed by your request
- Claude will analyze the code/issue and respond with suggestions or implementations

## Prompt Validation Action (`prompt-validation.yml`)

This workflow automatically validates prompt changes against our quality guidelines when a pull request modifies prompt files.

### What it does:
1. Triggers on PRs that modify files in `commands/` or `prompt-guideline.md`
2. Uses Claude Code to validate changed prompts against our guidelines
3. Posts validation results as a PR comment
4. Helps maintain consistent prompt quality across the repository

### Validation checks:
- Required sections present (Purpose, Context, Instructions, etc.)
- No role-based prompting patterns
- Imperative, direct language usage
- Explicit output format specification
- $ARGUMENTS placeholder at the end

### Setup:
Both workflows require the `ANTHROPIC_API_KEY` secret to be configured in your repository settings:
1. Go to Settings → Secrets and variables → Actions
2. Add a new repository secret named `ANTHROPIC_API_KEY`
3. Set the value to your Anthropic API key

### Security:
The workflows have minimal permissions:
- Read access to repository contents
- Write access to issues and pull requests (for comments only)

These permissions ensure Claude can analyze code and provide feedback without making direct changes to the repository.