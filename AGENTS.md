# Mooncraf agent instructions

This file is the canonical source for AI assistant operating rules in this repository.

## Runtime safety

- Never stop, restart, recreate, attach to, or otherwise touch the running Minecraft server or Docker container unless the user explicitly asks.
- Assume players may be online. Prefer read-only inspection when runtime impact is uncertain.
- Do not run commands that can interrupt gameplay or mutate live server state unless explicitly requested.

## Secrets

- Keep secrets in a local `.env` file and do not commit them to Git.
- Treat passwords, tokens, keys, and similar credentials as local-only unless the user explicitly asks for a different arrangement.

## Version control scope

- Version-control `docker-compose.yml`, `commands.txt`, durable server configuration, and admin/config files under `data/`.
- Do not version-control world data, logs, caches, downloaded libraries/mods, crash reports, or other runtime-generated files.
- When changing ignore rules, preserve the distinction between durable configuration and backup/runtime data.

## Editing approach

- Prefer minimal, reversible changes.
- Avoid changes that require a server restart unless the user explicitly asks for that work.
- If a requested change would affect the running server, call that out clearly before making it.