# Django Skills for AI Agents

A collection of AI agent skills for Django projects. Built for developers who want Claude Code (or similar AI coding assistants) to help with Django development, common workflows, and best practices.

## What are Skills?

Skills are markdown files that give AI agents specialized knowledge and workflows for specific tasks. When you add these to your project, agents like Claude Code can recognize when you're working on a Django task and apply the right frameworks and best practices.

## Available Skills

| Skill | Description | Triggers |
|-------|-------------|----------|
| [fix-types](skills/fix-types/SKILL.md) | Interactively fix type checking issues in Python code | `/fix-types`, working on mypy errors |

## Installation

### Option 1: CLI Install (Recommended)

Use the [Skills CLI](https://github.com/vercel-labs/skills) to install skills directly:

```bash
# Install all skills
npx skills add saaspegasus/django-skills

# Install specific skills
npx skills add saaspegasus/django-skills --skill skill-name

# List available skills
npx skills add saaspegasus/django-skills --list

# Install globally (available across all projects)
npx skills add saaspegasus/django-skills --global
```

This automatically installs to your `.claude/skills/` directory (or `~/.claude/skills/` for global installs).

### Option 2: Claude Code Plugin Marketplace

Claude Code has a built-in [plugin marketplace](https://code.claude.com/docs/en/discover-plugins) for discovering and installing skills:

```bash
# Add the marketplace
/plugin marketplace add saaspegasus/django-skills

# Install all skills from the marketplace
/plugin install django-skills

# Or use the interactive UI
/plugin
# Then go to the Discover tab to browse and install
```

This integrates with Claude Code's plugin system and supports auto-updates.

### Option 3: Clone and Copy

Clone the entire repo and copy the skills folder:

```bash
git clone https://github.com/saaspegasus/django-skills.git
cp -r django-skills/skills/* .claude/skills/
```

### Option 4: Git Submodule

Add as a submodule for easy updates:

```bash
git submodule add https://github.com/saaspegasus/django-skills.git .claude/django-skills
```

Then reference skills from `.claude/django-skills/skills/`.

### Option 5: Fork and Customize

1. Fork this repository
2. Customize skills for your specific needs
3. Clone your fork into your projects

## Usage

Once installed, just ask Claude Code to help with Django tasks. Skills are automatically triggered based on context.

You can also invoke skills directly:

```
/skill-name
```

### Skill File Structure

Each skill is a directory containing a `SKILL.md` file:

```
skills/
  skill-name/
    SKILL.md
```

The `SKILL.md` file follows this format:

```markdown
---
name: skill-name
description: One-line description for skill selection
---

# Skill Name

[Full instructions for the AI agent]
```

## Contributing

Contributions are welcome! If you have a Django workflow that would benefit from AI assistance, consider adding a skill.

## License

MIT - Use these however you want.
