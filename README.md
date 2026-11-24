# Artifactors Brain

Artifactors Brain is a shared knowledge base for your company: notes, decisions and process descriptions, grouped in spaces, that your AI assistant can search and add to. This plugin helps new users get started from a conversation with Claude.

## What is in the plugin

- **Connector:** the plugin uses the Artifactors Brain connector at `https://brain.artifactors.com/mcp`, the same server as the Artifactors Brain connector in the directory, so you see one set of tools.
- **Skill `get-started`:** guides a new user step by step. Claude creates an account (or connects an existing one), asks a few short questions about your company, saves your first note and offers to invite colleagues.

## Install

In Claude Code:

```
/plugin install artifactors-brain --marketplace t-oosterbaan/artifactors-brain-plugin
```

On claude.ai and in Cowork, install Artifactors Brain from the plugin directory.

## Use it

Install the plugin, then say for example "Help me get started with Artifactors Brain" or "Set up a Brain for my company". On claude.ai and in Cowork, connect the Artifactors Brain connector from the plugin's Connectors tab when Claude asks you to. You sign in once with the temporary password from the welcome email and then choose your own password.

A new Brain starts with a free 30-day trial with up to 100 notes. After the trial you can still search and read everything.

## Data

The plugin itself runs no code and stores nothing. Everything goes through the Artifactors Brain connector at brain.artifactors.com:

- To create an account, Claude sends your name, work email address and company name. Artifactors emails a temporary password to that address; the password is never shown in the chat.
- Your interview answers and your first note are saved in your own organisation in Artifactors Brain, only when you agree.
- To invite a colleague, Claude sends their email address, name and role, only after you confirm them. They receive an email with a temporary password.

Organisations are strictly separated. Notes deleted through an AI assistant go to the trash first. Privacy statement: https://brain.artifactors.com/privacy. Terms: https://brain.artifactors.com/terms. Documentation: https://brain.artifactors.com/docs. Questions: hello@artifactors.com.
