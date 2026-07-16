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

## Commits and pull requests

When creating commits or opening a pull request:

- Make every commit message and the pull-request title conform to
  [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/):
  the first line must use `<type>[optional scope][!]: <description>`, with any
  body or footer following the specification.
- Use `feat` for a new feature and `fix` for a bug fix. Other clear types such
  as `docs`, `test`, `refactor`, `build`, `ci`, and `chore` may be used when
  appropriate.
- Before opening a pull request, inspect every commit included in it and do not
  open the pull request while any commit message is non-conforming. Do not
  rewrite another contributor's shared history without active human approval.
- If the work began from or is strongly related to a GitHub issue, formally
  link the pull request and issue. For a pull request that targets the default
  branch and resolves the issue, put a supported closing keyword such as
  `Closes #123` in the pull-request description, not only in a commit message.
  For a pull request that must not close the issue or does not target the
  default branch, use GitHub's Development sidebar to create the link and add
  `Related to #123` to the description for context.
- Verify that GitHub shows the relationship from both the pull request and the
  issue. GitHub creates the reciprocal link automatically when the relationship
  is established, so a separate issue comment is not required solely to add a
  backlink. See
  [Linking a pull request to an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue).
- Give every pull-request description exactly these five level-two sections in
  this order: `Summary`, `Root Cause`, `Implementation`, `Validation`, and
  `Testing`.
- Use `Validation` to report checks already performed by the agent, automation,
  or contributor, including results and anything that could not be run.
- Keep `Testing` as the final section. It must contain a GitHub task list of
  concrete steps for a human to perform manually to verify the implemented
  solution. Leave each item unchecked until a human confirms that specific
  step was completed; an agent must not claim human validation.

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
