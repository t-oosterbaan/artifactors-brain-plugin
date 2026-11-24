---
name: get-started
description: Get a new user started with Artifactors Brain. Use when the user wants to start with Artifactors Brain, set up a Brain or company knowledge base, create an Artifactors Brain account, connect the Brain for the first time, or asks how to begin, what to put in it first or how to invite colleagues.
---

# Get started with Artifactors Brain

Goal: in about ten minutes the user has an account, is connected, has answered a short interview, and has a first note in their own Brain. Then offer to invite colleagues.

Talk in the user's language. Keep every message short, ask one question at a time, and wait for the answer. This works in voice too: then spell email addresses back before you use them.

Use only the tools of the Artifactors Brain connector. Do not import or copy what you remember about the user from other conversations; only use what the user tells you in this conversation.

## 1. Account

Ask whether the user already has an Artifactors Brain account.

- **Has an account:** go to step 2.
- **No account:** ask, one at a time, for their name, their work email address and their company name. Confirm the email address. Then call `create_account` with `name`, `email`, `company` and `language` (`nl` for Dutch, otherwise `en`).
  - If `created` is true: tell the user to check their email for the temporary password. Never ask the user to type or paste the password into the chat.
  - If `created` is false: read out the message from the result and stop the onboarding. Do not retry with other details on your own.

The new Brain is a free 30-day trial with up to 100 notes, with the spaces Company, Processes and Decisions.

## 2. Connect

Call `list_spaces` to check the connection.

- If the app asks the user to connect or sign in: explain that they sign in once with their email address and the temporary password from the email, and then choose their own password. On claude.ai and in Cowork they connect the Artifactors Brain connector from the plugin's Connectors tab.
- When the call works: check the `account` field in the result and confirm with the user that this is the right account and organisation. If it is not, stop and let the user connect the right account first.

## 3. Short interview

Ask at most five short questions, one at a time, and skip what the user already told you:

1. What does the company do, and for whom?
2. Who are the most important people or roles?
3. Which customers, suppliers or systems does everyone need to know?
4. Which process or task do new colleagues ask about most?
5. Which recent decision should everyone know about?

Let the user skip any question. Do not ask for passwords, financial account numbers, health data or other sensitive personal data.

## 4. First note

Summarise the answers as one clear note with a title like "About <company>" and short sections per topic. Show the summary and ask if it is correct. Only after the user agrees, save it with `create_note`.

Then show what the Brain can do now: call `search` with a question about the company, for example "what does <company> do", and answer from the result, naming the note title as the source.

Tell the user where the note was saved (account, organisation and space). New notes are filed into the right space automatically within a minute.

## 5. Invite colleagues

Ask if the user wants to invite colleagues. If yes, per colleague ask for the email address, optionally the name, and the role: `member` (sees all spaces that are not restricted) or `owner` (can also manage members and access). Confirm the details, then call `invite_colleague`. Only owners can invite; if the tool says the user is not allowed, explain that and continue.

## 6. Close

End with three short tips:

- Say "remember that ..." or "save this in my Brain" to add knowledge.
- Ask questions about the company; answers come from the Brain with the note as the source.
- Ask for the latest notes to see what colleagues added.

Help and documentation: https://brain.artifactors.com/docs. Questions: hello@artifactors.com.
