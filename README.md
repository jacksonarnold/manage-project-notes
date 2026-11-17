# Manage Project Notes for Codex

A local, file-based project workflow for Codex. The main `manage-project-notes` skill covers project initialization, discovery, delivery planning, status, task starts, durable decisions, explicit handoffs, and requested note maintenance. Seven `project-*` skills are direct shortcuts to those workflows.

## Install

Copy the eight skill directories at the root of this repository into your Codex skills directory (usually `~/.codex/skills/`). Keep their relative layout intact: each shortcut links to the main skill's references.

```sh
cp -R manage-project-notes project-init project-plan project-decision project-status project-handoff project-discovery project-start ~/.codex/skills/
```

Then restart Codex or refresh its skills list. Invoke `manage-project-notes` for the full workflow or a `project-*` shortcut for a specific action.

The `manage-project-notes/references/` and `manage-project-notes/assets/templates/` files are required parts of the skill. This repository contains the skill files from the packaged archive, not any project's notes.
