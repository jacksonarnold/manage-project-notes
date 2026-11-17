# Manage Project Notes for Codex

A single local, file-based project workflow skill for Codex. `manage-project-notes` covers project initialization, discovery, delivery planning, status, task starts, durable decisions, explicit handoffs, and requested note maintenance. Its `references/` and `assets/templates/` directories support those workflows within the same skill.

## Install

Copy the `manage-project-notes` directory into your Codex skills directory (usually `~/.codex/skills/`). Keep its relative layout intact.

```sh
cp -R manage-project-notes ~/.codex/skills/
```

Then restart Codex or refresh its skills list. Invoke `manage-project-notes` for the workflow.

This repository contains only the skill and its supporting files, not any project's notes.
