# AIMER: AI-Assisted Software Analysis & Improvement Prompts

AIMER is a comprehensive collection of prompts designed to help developers analyze and improve software systems with the assistance of AI tools like Claude. These prompts are formatted as custom slash commands for Claude Code, making them easily accessible during your development workflow.

## Features
- Ready-to-use prompts for various software analysis tasks
- Workflow-optimized prompt templates for product and feature development
- Code analysis and improvement prompts
- Jobs-to-be-Done (JTBD) templates for product development
- All prompts available as Custom Slash Commands for Claude Code

## Installation

### Project-Specific Commands

To make AIMER prompts available within a specific project:

#### Option 1: Direct Clone

1. Clone this repository into your project's `.claude/commands` directory:

```bash
# Navigate to your project root
mkdir -p .claude/commands
git clone https://github.com/yourusername/aimer.git .claude/commands
```

2. Use the commands in Claude Code with the `/project:` prefix:

```
claude > /project:analyze-performance
```

#### Option 2: Git Submodule (Recommended)
Adding AIMER as a Git submodule allows you to track specific versions and update more easily:

1. Add the repository as a submodule in your project:

```bash
# Navigate to your project root
mkdir -p .claude/commands
git submodule add https://github.com/yourusername/aimer.git .claude/commands/aimer
```

2. Use the commands in Claude Code with the `/project:` prefix:

```
claude > /project:analyze-performance
```

3. Update the submodule when needed:

```bash
git submodule update --remote .claude/commands/aimer
```

### User-Specific Commands
To make AIMER prompts available for all your projects:

1. Clone this repository into your home Claude commands directory:

```bash
mkdir -p ~/.claude/commands
git clone https://github.com/yourusername/aimer.git ~/.claude/commands
```

2. Use the commands in Claude Code with the `/user:` prefix:

```
claude > /user:analyze-performance
```

## Usage Tips
- Command names are derived from the filename (e.g., `analyze-performance.md` becomes `/project:analyze-performance`)
- You can organize prompts in subdirectories for better categorization
- Project-scoped commands are shared with team members who have access to the repository
- User-scoped commands are only available to you across all projects
- Some prompts use `$ARGUMENTS` to accept additional contextual information

## Categories
- **Product Analysis**: Prompts for analyzing product requirements and features
- **JTBD Analysis**: Jobs-to-be-Done templates for understanding user needs
- **Workflow Optimization**: Prompts for improving development workflows
- **Code Analysis**: Deep-dive code analysis and improvement suggestions
- **Documentation**: Templates for generating and improving documentation

## Contributing
Contributions are welcome! Please feel free to submit a pull request with new prompts or improvements to existing ones.

## Maintainers
- Markus Harrer
- Roman Stranghöner
- Robert Glaser

## License
See the [LICENSE](LICENSE) file for details.