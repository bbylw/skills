> **Note:** This repository originated from Anthropic's implementation of skills for Claude, and is now documented to be broadly reusable across AI assistants. For information about the Agent Skills standard, see [agentskills.io](http://agentskills.io).

# Skills
Skills are folders of instructions, scripts, and resources that an AI assistant can load dynamically to improve performance on specialized tasks. Skills teach assistants how to complete specific tasks in a repeatable way, whether that's creating documents with your company's brand guidelines, analyzing data using your organization's specific workflows, or automating personal tasks.

For more information, check out:
- [Agent Skills Specification](./spec/agent-skills-spec.md)
- [Anthropic: What are skills?](https://support.claude.com/en/articles/12512176-what-are-skills)
- [Anthropic: Using skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [Anthropic: How to create custom skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [Equipping agents for the real world with Agent Skills](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

# About This Repository

This repository contains skills that demonstrate what is possible with an agent skills system. These skills range from creative applications (art, music, design) to technical tasks (testing web apps, MCP server generation) to enterprise workflows (communications, branding, etc.).

Each skill is self-contained in its own folder with a `SKILL.md` file containing the instructions and metadata that an AI assistant uses. Browse through these skills to get inspiration for your own skills or to understand different patterns and approaches.

Many skills in this repo are open source (Apache 2.0). We've also included the document creation & editing skills that power [Claude's document capabilities](https://www.anthropic.com/news/create-files) under the hood in the [`skills/docx`](./skills/docx), [`skills/pdf`](./skills/pdf), [`skills/pptx`](./skills/pptx), and [`skills/xlsx`](./skills/xlsx) subfolders. These are source-available, not open source, but we wanted to share these with developers as a reference for more complex skills that are actively used in a production AI application.

## Cross-Platform Compatibility Notes

These skills are written to be portable:
- Keep triggers in `description` model-agnostic (e.g., “use when editing DOCX with tracked changes”) instead of product-specific.
- Prefer phrases like **"the assistant"**, **"the agent"**, or **"your AI runtime"** over vendor names unless an integration truly requires one.
- Document provider-specific setup in clearly labeled sections (for example, "Claude-specific setup").
- Keep reusable logic in scripts under `scripts/` so multiple AI environments can invoke the same deterministic workflow.

## Disclaimer

**These skills are provided for demonstration and educational purposes only.** Implementations and behaviors may differ by model, provider, orchestration framework, and runtime environment. These skills are meant to illustrate patterns and possibilities. Always test skills thoroughly in your own environment before relying on them for critical tasks.

# Skill Sets
- [./skills](./skills): Skill examples for Creative & Design, Development & Technical, Enterprise & Communication, and Document Skills
- [./spec](./spec): The Agent Skills specification
- [./template](./template): Skill template

# Platform-specific setup examples

## Claude Code / Claude.ai / Claude API

If you are using Claude products, you can use the following Anthropic-specific workflows.

### Claude Code
You can register this repository as a Claude Code Plugin marketplace by running:
```
/plugin marketplace add anthropics/skills
```

Then, to install a specific set of skills:
1. Select `Browse and install plugins`
2. Select `anthropic-agent-skills`
3. Select `document-skills` or `example-skills`
4. Select `Install now`

Alternatively, directly install either plugin via:
```
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

### Claude.ai
These example skills are available to paid plans in Claude.ai.

To use any skill from this repository or upload custom skills, follow [Using skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b).

### Claude API
You can use Anthropic's pre-built skills, and upload custom skills, via the Claude API. See the [Skills API Quickstart](https://docs.claude.com/en/api/skills-guide#creating-a-skill).

## Other AI platforms

For non-Claude environments, use the [Agent Skills specification](./spec/agent-skills-spec.md) and adapt integration points (triggering, packaging, and tool/runtime binding) to your target assistant framework.

# Creating a Basic Skill

Skills are simple to create - just a folder with a `SKILL.md` file containing YAML frontmatter and instructions. You can use the **template-skill** in this repository as a starting point:

```markdown
---
name: my-skill-name
description: A clear description of what this skill does and when to use it
---

# My Skill Name

[Add your instructions here that the assistant will follow when this skill is active]

## Examples
- Example usage 1
- Example usage 2

## Guidelines
- Guideline 1
- Guideline 2
```

The frontmatter requires only two fields:
- `name` - A unique identifier for your skill (lowercase, hyphens for spaces)
- `description` - A complete description of what the skill does and when to use it

The markdown content below contains the instructions, examples, and guidelines the assistant will follow.

# Partner Skills

Skills are a great way to teach AI assistants how to get better at using specific pieces of software. As we see awesome example skills from partners, we may highlight some of them here:

- **Notion** - [Notion Skills for Claude](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
