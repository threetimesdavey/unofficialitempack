# Configuring AI agents for repository development

[README](README.md) ·
[Changelog](CHANGELOG.md) ·
[Contributing](CONTRIBUTING.md) ·
[AI setup](AI-CONFIGURATION.md) ·
[Contributors](CONTRIBUTORS.md) ·
[Maintenance notice](MAINTENANCE-NOTICE.md)

This guide configures local AI coding agents to locate legally installed copies
of BG:EE and BG2:EE without storing contributor-specific absolute paths in the
repository.

The same environment-variable names are used on Windows, macOS, and Linux.
Installation locations may differ freely between contributors and storefronts.

## Required variables

| Variable | Required value |
|---|---|
| `BGEE_GAME_ROOT` | BG:EE installation directory containing `chitin.key` |
| `BG2EE_GAME_ROOT` | BG2:EE installation directory containing `chitin.key` |

Set only the games installed on the machine. A missing variable means that
tasks requiring that game cannot be validated locally.

Do not point a variable at the game executable, a save directory, the user
documents directory, or a subdirectory such as `data` or `lang`.

## Windows setup

### Persistent user variables with PowerShell

Replace the example paths with the actual installation directories:

```powershell
[Environment]::SetEnvironmentVariable(
    "BGEE_GAME_ROOT",
    "C:\Games\Baldur's Gate Enhanced Edition",
    [System.EnvironmentVariableTarget]::User
)

[Environment]::SetEnvironmentVariable(
    "BG2EE_GAME_ROOT",
    "C:\Games\Baldur's Gate II Enhanced Edition",
    [System.EnvironmentVariableTarget]::User
)
```

Close and reopen terminals, editors, and AI applications after setting
persistent variables. Already-running applications normally retain their old
environment.

For a temporary PowerShell session instead:

```powershell
$env:BGEE_GAME_ROOT = "C:\Games\Baldur's Gate Enhanced Edition"
$env:BG2EE_GAME_ROOT = "C:\Games\Baldur's Gate II Enhanced Edition"
```

Temporary values are inherited only by applications launched from that
PowerShell session and disappear when the session closes.

### Verify on Windows

```powershell
Test-Path -LiteralPath (Join-Path $env:BGEE_GAME_ROOT "chitin.key")
Test-Path -LiteralPath (Join-Path $env:BG2EE_GAME_ROOT "chitin.key")
```

Each configured game should return `True`.

## macOS and Linux setup

For the current shell session:

```sh
export BGEE_GAME_ROOT="/absolute/path/to/Baldur's Gate Enhanced Edition"
export BG2EE_GAME_ROOT="/absolute/path/to/Baldur's Gate II Enhanced Edition"
```

To make the variables persistent, add the exports to the startup file used by
the shell that launches the AI tool. Common examples include `~/.zprofile`,
`~/.zshrc`, `~/.bash_profile`, and `~/.bashrc`.

After editing the startup file, open a new terminal and restart the editor or AI
application. When an application does not inherit shell startup variables,
launch it from a configured terminal or use the application's supported
environment configuration.

### Verify on macOS or Linux

```sh
test -n "$BGEE_GAME_ROOT" &&
  test -f "$BGEE_GAME_ROOT/chitin.key" &&
  echo "BG:EE configured"

test -n "$BG2EE_GAME_ROOT" &&
  test -f "$BG2EE_GAME_ROOT/chitin.key" &&
  echo "BG2:EE configured"
```

## Verify from the AI agent

After restarting the AI tool, ask it:

> Verify that `BGEE_GAME_ROOT` and `BG2EE_GAME_ROOT` point to directories
> containing `chitin.key`. Do not modify either directory.

The repository's `AGENTS.md` instructs agents to validate the variables without
guessing installation locations. Agents must treat both directories as
read-only unless a human actively approves a write operation in the current
task.

If an agent reports that a variable is unavailable:

1. verify it in a new terminal;
2. restart the AI application;
3. confirm that the AI tool inherits the environment of the process that
   launches it;
4. if Codex uses a restrictive `shell_environment_policy`, ensure its
   environment allowlist includes `BGEE_GAME_ROOT` and `BG2EE_GAME_ROOT`.

Cloud-hosted agents cannot access installations stored only on a contributor's
computer. Do not upload proprietary game files merely to make them available to
a cloud task.

## Purpose of `.env.example`

The tracked `.env.example` documents the variable names expected by this
repository and provides a template for future local tooling.

It does not contain real paths and is not loaded automatically. Do not edit it
with personal installation paths. The ignored `.env` and `.env.local` names are
reserved for optional local configuration and future tooling.

Until the repository provides a loader, configure the variables through the
operating system or the process that launches the AI tool.

## Safety rules

- Keep local absolute paths out of commits, issues, logs, and screenshots when
  they are not needed.
- Treat game installations as read-only by default.
- Obtain active human approval before an agent runs any operation that may
  write inside a game directory.
- Do not commit game resources unless the repository has confirmed permission
  to redistribute them.
- Report game-dependent tests as not run when the required variable or write
  approval is unavailable.
