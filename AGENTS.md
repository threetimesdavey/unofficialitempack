# Repository guidance for AI agents

## Start here

Before making substantive changes, read:

1. `README.md` for project scope, supported games, and compatibility notes.
2. `CONTRIBUTING.md` for development, testing, documentation, and pull-request
   requirements.
3. `MAINTENANCE-NOTICE.md` when a task involves authorship, redistribution,
   licensing, historical material, or third-party assets.
4. `AI-CONFIGURATION.md` when a task needs access to a local game installation.

Preserve Edvin's attribution as the original author and follow the repository's
community-maintenance policy.

## Repository conventions

- Prefer targeted WeiDU patching over replacing complete game resources.
- Preserve existing component numbers and translation structure unless a
  coordinated change explicitly requires otherwise.
- Put player-visible text in TRA files rather than hard-coding it.
- Do not add copyrighted game resources or third-party mod material without
  confirmed redistribution permission.
- Do not update generated release archives or installer binaries unless the
  task explicitly concerns coordinated release infrastructure.
- Update documentation and the `[Unreleased]` changelog when the change affects
  users, contributors, installation, compatibility, or repository workflow.
- Match the verification effort to the risk of the change and report any
  checks that could not be performed.

## Local game installations

Some development and validation tasks require legally installed copies of the
Infinity Engine games. Installation paths are machine-specific and must not be
committed to the repository.

Use these environment variables:

- `BGEE_GAME_ROOT`: root of the Baldur's Gate: Enhanced Edition installation.
- `BG2EE_GAME_ROOT`: root of the Baldur's Gate II: Enhanced Edition
  installation.

Each configured directory must contain `chitin.key`.

Treat the variable names and path handling as operating-system agnostic:

- read variables from the current process environment using facilities
  appropriate to the active shell or programming language;
- expect spaces, apostrophes, and platform-specific path separators;
- join paths safely instead of constructing them with a hard-coded separator;
- do not assume Steam, GOG, Beamdog, or any default installation location.

Before accessing a game installation, verify that the relevant variable is set,
points to a directory, and contains `chitin.key`.

Do not:

- hardcode an absolute game path in tracked files;
- search the user's filesystem for an installation when a variable is missing;
- copy proprietary game resources into the repository;
- expose a contributor's local installation path in committed output;
- treat `.env.example` as live configuration.

If a required variable is missing or invalid, continue with work that does not
depend on the installation. Clearly report that game-dependent validation was
not performed and identify the variable that must be configured.

## Read-only game-directory policy

Treat both game directories as read-only by default.

Reading or inspecting resources is allowed when relevant to the task. Any
operation that can create, modify, move, or delete files in a game directory
requires active approval from a human in the current task before it is run.

This includes, but is not limited to:

- copying the mod into a game directory;
- running WeiDU installation, uninstallation, or reinstallation;
- writing generated resources, logs, debug files, backups, or test artifacts;
- changing an existing modded installation.

A general request to edit this repository does not grant permission to write to
a game installation. When approval is absent, provide the exact manual test
that remains to be run.

## Verification and handoff

- Run repository-only checks that are safe and relevant.
- Do not claim in-game or installation testing unless it was actually
  performed.
- State which game, language, components, and installation state were tested
  when reporting game-dependent results.
- Summarize remaining manual validation in the final handoff.
