# Artifactors Brain

Artifactors Brain is a shared knowledge base for your company: notes, decisions and process descriptions, grouped in spaces, that your AI assistant can search and add to. This plugin helps new users get started from a conversation with Claude.

## What is in the plugin

- **Connector:** the plugin uses the Artifactors Brain connector at `https://brain.artifactors.com/mcp`, the same server as the Artifactors Brain connector in the directory, so you see one set of tools.
- **Skill `get-started`:** guides a new user step by step. Claude creates an account (or connects an existing one), asks a few short questions about your company, saves your first note and offers to invite colleagues.

## What the connector's tools can do

Most tools only search and read your Brain. Some tools write, send, delete or change access. Claude uses them only when you ask, and asks you to confirm before anything is sent, deleted or changed for someone else.

**Send (emails go out from Artifactors to the address you give):**

- `create_account` creates a new Brain and emails a temporary password to the work email address you give.
- `invite_colleague` adds a colleague to your organisation and emails them an invitation with a temporary password.

**Write and publish inside your own organisation:**

- `create_note`, `append_to_note`, `update_note` and `capture_quick` save or change notes. Notes you save are visible to the members of your organisation who can see that space.
- `save_process_description`, `confirm_process`, `link_note_to_process`, `set_catalogue` and `update_catalogue` save and confirm process descriptions.
- `move_note`, `move_folder`, `merge_space`, `create_space` and `organise_inbox` reorganise notes and spaces.
- `review_suggestion` accepts or rejects suggestions to move, merge or mark notes outdated.
- Build list tools (`add_build_task`, `update_build_task`, `answer_build_question` and related tools) are only available to organisations that use a build list. Approving a build task means the organisation's own build agent may build the change and publish it to that organisation's own products.

**Delete:**

- `delete_note` moves a note to the trash. It can be restored for 30 days with `restore_note`; after that it is removed permanently. Claude deletes only after you confirm.
- `remove_member` removes a person from your organisation, so they lose access to its notes.

**Change access (owners only):**

- `change_member_role` changes a member's role (owner, member or consultant).
- `set_space_access` and `restrict_space` decide which members can see a space.

The connector cannot make payments. Which of these tools you see depends on your role and your organisation; members who are not owners cannot change access or remove people.

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
