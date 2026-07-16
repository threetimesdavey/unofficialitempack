# Contributing to BG2:EE Unofficial Item Pack

[README](README.md) ·
[Changelog](CHANGELOG.md) ·
[Contributing](CONTRIBUTING.md) ·
[AI setup](AI-CONFIGURATION.md) ·
[Contributors](CONTRIBUTORS.md) ·
[Maintenance notice](MAINTENANCE-NOTICE.md)

Thank you for helping preserve and improve **BG2:EE Unofficial Item Pack**.

Contributions may include code, WeiDU improvements, compatibility fixes,
translations, testing, documentation, item descriptions, installation
research, historical material, or carefully discussed new content.

This project began as Edvin’s work. Every contribution must preserve that
authorship and follow the stewardship principles described in
[MAINTENANCE-NOTICE.md](MAINTENANCE-NOTICE.md).

> [!IMPORTANT]
> Before submitting original mod files, game assets, third-party code, images,
> or translations, make sure that you have the right to contribute and
> redistribute them.
>
> Repository visibility does not by itself establish an open-source license.
> See [Rights, permissions, and contributed material](#rights-permissions-and-contributed-material).

## Table of contents

- [Before contributing](#before-contributing)
- [Ways to contribute](#ways-to-contribute)
- [Choosing the right workflow](#choosing-the-right-workflow)
- [Reporting a bug](#reporting-a-bug)
- [Reporting a compatibility problem](#reporting-a-compatibility-problem)
- [Proposing balance changes or new content](#proposing-balance-changes-or-new-content)
- [Contributing a translation](#contributing-a-translation)
- [WeiDU and Infinity Engine development guidelines](#weidu-and-infinity-engine-development-guidelines)
- [Testing requirements](#testing-requirements)
- [Git and pull-request workflow](#git-and-pull-request-workflow)
- [Pull-request checklist](#pull-request-checklist)
- [Documentation standards](#documentation-standards)
- [Credit and attribution](#credit-and-attribution)
- [Rights, permissions, and contributed material](#rights-permissions-and-contributed-material)
- [Community conduct](#community-conduct)

## Before contributing

Please read:

1. [README.md](README.md), for the mod’s scope, components, installation, and
   known compatibility notes;
2. [MAINTENANCE-NOTICE.md](MAINTENANCE-NOTICE.md), for project stewardship and
   original-author policy;
3. [CHANGELOG.md](CHANGELOG.md), for release history and current unreleased
   changes;
4. [CONTRIBUTORS.md](CONTRIBUTORS.md), for attribution practices.

Search existing issues and pull requests before opening a new one. A problem or
proposal may already be under discussion.

## Ways to contribute

Useful contributions include:

- reproducible bug reports;
- corrections to missing or invalid resources;
- safer WeiDU patching;
- compatibility improvements;
- installation-order testing;
- BG2:EE and EET testing;
- additional translations;
- documentation corrections;
- historical release information;
- accessibility improvements;
- item-description corrections;
- balance analysis;
- new item concepts that fit the mod’s original purpose;
- screenshots for the item gallery;
- release packaging and verification.

Small documentation corrections may be submitted directly as pull requests.

Code changes, balance changes, new items, component restructuring, and changes
that affect compatibility should normally begin with a GitHub issue.

## Choosing the right workflow

### Open an issue first when the contribution:

- changes item statistics, usability, placement, price, or lore;
- adds or removes an item;
- changes a component number or component boundary;
- changes installation order or compatibility behavior;
- patches a shared creature, store, script, spell, dialogue, or area;
- changes a resource name;
- adds a new dependency;
- changes translation encoding or file structure;
- affects saved-game compatibility;
- changes the repository’s licensing or maintenance policy.

### A direct pull request is normally suitable for:

- spelling and grammar corrections;
- broken documentation links;
- image alt text;
- confirmed historical corrections with a source;
- narrowly scoped translation corrections;
- tests or documentation for an already approved change.

When uncertain, open an issue and describe the intended result before investing
in a large implementation.

## Reporting a bug

A useful bug report should contain enough information for another person to
reproduce the problem.

Please include:

- **Game:** BG2:EE, EET, or another supported installation;
- **Game version:** the complete version number;
- **Operating system:** Windows, Linux, or macOS;
- **Mod version:** release number, Git tag, or commit;
- **Installed components:** every Unofficial Item Pack component selected;
- **Other mods:** relevant mods and versions;
- **Installation order:** preferably the relevant portion of `WeiDU.log`;
- **Location:** area, creature, store, dialogue, or encounter involved;
- **Steps to reproduce:** a numbered sequence starting from a reliable state;
- **Expected result:** what should have happened;
- **Actual result:** what happened instead;
- **Error output:** WeiDU errors, console messages, or crash details;
- **Supporting files:** save game, screenshot, log, or minimal reproduction when
  useful.

Do not post private information, account credentials, or copyrighted game files
that are not required and authorized for redistribution.

### Example bug-report title

`[BG2:EE] Circlet of the Cynosure cannot be equipped by the intended character`

### Good reproduction sequence

1. Install the specified components in the stated order.
2. Begin a new game or load the attached clean test save.
3. Acquire the affected item from the named store or creature.
4. Attempt the relevant action.
5. Record the displayed message and the expected behavior.

## Reporting a compatibility problem

Compatibility reports should identify both mods and the exact installation
order.

Please include:

- the version of each mod;
- the components installed from each mod;
- which mod was installed first;
- whether the installation completed without WeiDU errors;
- whether the problem occurs in a new game;
- the resource or gameplay behavior that differs;
- whether reinstalling in another order changes the result;
- the relevant section of `WeiDU.log`.

When possible, determine whether the conflict results from:

- two mods changing the same item;
- a complete resource overwrite;
- a store or creature replacement;
- duplicate imported SoD content;
- an invalid usability restriction;
- a missing EFF, SPL, ITM, BAM, or other dependent resource;
- a script or dialogue state conflict;
- hard-coded string references;
- a component being installed on an unsupported game.

Compatibility fixes should prefer cooperative patching over forcing users to
choose one mod.

## Proposing balance changes or new content

The original project focused on giving overlooked, underused, and quest-related
items a meaningful place in BG2:EE. New proposals should remain recognizably
connected to that purpose.

A proposal should explain:

- the item or gameplay problem;
- why the existing item is overlooked or underused;
- the proposed statistics and abilities;
- intended character classes or builds;
- acquisition method and game chapter;
- price and availability;
- lore justification;
- interaction with existing BG2:EE items;
- interaction with Item Revisions or other major item mods;
- whether the change affects Shadows of Amn, Throne of Bhaal, or both;
- whether a new game is required;
- possible balance risks;
- alternative implementations considered.

Avoid adding power solely for its own sake. The objective is to create useful,
interesting choices without invalidating existing equipment or trivializing
encounters.

Large changes should be implemented as optional components whenever practical.

## Contributing a translation

Translations are welcome.

Before starting a new language, open an issue so that translators can coordinate
file ownership, encoding, terminology, and testing.

### Translation requirements

- Translate text through the mod’s TRA files rather than hard-coding strings in
  TP2, D, BAF, or other source files.
- Preserve all string placeholders, variables, formatting tokens, and WeiDU
  syntax.
- Preserve item names consistently across descriptions, setup prompts,
  readmes, and changelogs.
- Do not translate resource names or internal identifiers.
- Use the encoding expected by the supported Enhanced Edition games and the
  project’s conversion workflow.
- Test a complete installation in the translated language.
- Check apostrophes, accented characters, gendered language, line breaks, and
  dialogue-window readability.
- Note whether the translation covers every component.
- Add the translator’s preferred credit to `CONTRIBUTORS.md`.
- Update `CHANGELOG.md` under `[Unreleased]`.

### Translation pull requests should state

- the language and locale;
- translator name or handle;
- source-language version used;
- files translated;
- components covered;
- game installation used for testing;
- whether native-language proofreading was completed.

Machine translation may be used as a private drafting aid, but an unreviewed
machine-generated translation should not be submitted as a completed
localization.

## WeiDU and Infinity Engine development guidelines

Changes should be safe to install, uninstall, reinstall, and combine with other
mods whenever the engine and affected resource permit it.

### Patch existing resources

Prefer WeiDU patching such as `COPY_EXISTING`, `ALTER_*`, `ADD_*`, or targeted
binary patch operations over distributing complete replacements for existing
game resources.

Avoid replacing an entire creature, item, store, script, spell, dialogue, or
area merely to change one field.

A full replacement may erase changes made by mods installed earlier and may
prevent later mods from finding expected content.

When a full replacement is unavoidable:

- explain why targeted patching is insufficient;
- identify the affected resource;
- document known compatibility consequences;
- add a test for the intended result where possible;
- discuss the approach in an issue before merging.

### Use unique resources

- Reuse the project’s established resource prefix where one exists.
- Discuss and document a prefix before adding resources if the historical
  project does not use a consistent one.
- Check new resource names for collisions.
- Remember that classic Infinity Engine resource names are limited in length.
- Do not rename historical resources without a migration and compatibility
  reason.

### Preserve stable components

- Keep existing component numbers stable.
- Do not silently move content between components.
- Use `DESIGNATED` numbers where the project’s TP2 structure supports them.
- Record new dependencies and incompatibilities.
- Make optional or controversial content separately selectable when practical.
- Avoid changing default installation behavior without discussion.

### Use translation files

- Put player-visible text in TRA files.
- Avoid hard-coded string references.
- Preserve all supported languages when adding strings.
- Use temporary placeholder translations only when clearly marked and tracked
  by an issue.
- Do not remove an existing language because a new string is temporarily
  untranslated.

### Patch by intent

A patch should check that the expected resource structure exists before
changing it.

Where practical:

- use `PATCH_IF` or equivalent guards;
- check whether another mod has already added the intended effect;
- avoid adding duplicate abilities, inventory entries, or store items;
- make patches idempotent where WeiDU permits;
- fail with a useful message when a required resource is missing;
- skip optional content safely when running on an unsupported game;
- log compatibility decisions clearly.

### Preserve source and release separation

Normal pull requests should contain source files, documentation, tests, and
authorized assets.

Do not update generated release archives or installer binaries unless the pull
request specifically concerns release infrastructure and has been coordinated
with a maintainer.

Release packaging should be reproducible from repository contents.

## Testing requirements

The amount of testing should match the risk of the change.

### Minimum documentation test

For documentation-only changes:

- preview the rendered Markdown;
- verify headings and internal links;
- verify relative file and image paths;
- check spelling of item and component names.

### Minimum translation test

For translation changes:

- complete a WeiDU installation in the affected language;
- inspect setup prompts;
- inspect affected item names and descriptions in game;
- verify special characters;
- uninstall and reinstall the component.

### Minimum code test

For source changes:

- install on a clean supported BG2:EE installation;
- test installation, uninstallation, and reinstallation;
- begin a new game when the component changes stores, creatures, areas, or item
  placement;
- acquire or create the affected item;
- test every changed ability;
- verify usability restrictions;
- verify identified and unidentified names and descriptions;
- verify item icons and ground icons;
- verify charges, stacking, prices, lore, and flags where relevant;
- inspect the resulting resource with an Infinity Engine editor when useful;
- review `SETUP-*.DEBUG` for warnings.

### Additional compatibility testing

Changes affecting shared resources should also be tested, where practical,
with:

- EET;
- Item Revisions;
- Cowled Menace;
- common tweak collections;
- other mods named in the related issue.

A pull request does not need to test every possible mod combination, but it must
state what was and was not tested.

## Git and pull-request workflow

1. Fork the repository.
2. Create a focused branch from the current default branch.
3. Make one logically related change.
4. Test the change.
5. Update documentation and the changelog.
6. Push the branch to your fork.
7. Open a pull request.
8. Respond to review comments with additional commits.
9. Avoid rewriting shared history after review has begun unless necessary.

Suggested branch names:

- `fix/<short-description>`;
- `feature/<short-description>`;
- `compat/<mod-name>`;
- `translation/<language>`;
- `docs/<short-description>`;
- `release/<version>`.

Examples:

- `fix/circlet-usability`;
- `compat/item-revisions`;
- `translation/italian`;
- `docs/item-gallery`.

Commit messages should be clear and specific.

Prefer:

- `Fix missing EFF dependency for imported SoD item`
- `Patch MAGE18Z instead of replacing the creature`
- `Add Italian strings for Reworked Free Action`
- `Document EET component conflict`

Avoid:

- `Update files`
- `Fix stuff`
- `Changes`
- `Final version`

## Pull-request checklist

Before requesting review, confirm that:

- [ ] The pull request addresses one clearly defined problem or proposal.
- [ ] A related issue is linked when the change is substantial.
- [ ] Existing authorship and credits are preserved.
- [ ] I have the right to contribute every included file.
- [ ] Existing game resources are patched rather than replaced where possible.
- [ ] New resources use collision-resistant names.
- [ ] Existing component numbers remain stable.
- [ ] Player-visible strings use TRA files.
- [ ] Existing languages were preserved.
- [ ] Installation succeeds without unexpected WeiDU errors.
- [ ] Uninstallation and reinstallation were tested when applicable.
- [ ] Gameplay behavior was tested in game.
- [ ] A new game was used when required.
- [ ] Known compatibility implications are documented.
- [ ] `README.md` was updated if installation, components, or compatibility
      changed.
- [ ] `CHANGELOG.md` was updated under `[Unreleased]`.
- [ ] `CONTRIBUTORS.md` was updated when a new contributor should be credited.
- [ ] The pull request explains what was tested.
- [ ] The pull request identifies anything that remains untested.

## Documentation standards

Repository documentation should:

- use descriptive headings;
- use repository-relative links for repository files and images;
- use one sentence per line only when it improves diffs without harming
  readability;
- use `BG2:EE` consistently;
- use `EET` consistently;
- spell `WeiDU` with its established capitalization;
- preserve official item names;
- preserve intentionally unusual historical names, such as **Wizzard Hat**,
  while noting that the spelling comes from the original mod;
- distinguish confirmed behavior from proposals;
- distinguish fixed issues from reported issues;
- avoid presenting planned content as released content;
- use ISO-style dates;
- provide alt text for images;
- avoid unnecessary raw HTML except where Markdown cannot provide the required
  layout.

Historical documentation should cite its source.

## Credit and attribution

Authorship credit is not optional.

- Edvin must remain identified as the original creator.
- Existing copyright or authorship notices must not be removed.
- Contributors should be credited by their preferred public name or handle.
- Significant accepted contributions should be recorded in
  `CONTRIBUTORS.md`.
- Release-specific contributions should also be summarized in release notes.
- Git history remains the detailed record of individual changes.

A contributor may request correction of their display name or profile link.

Credits should describe what a person contributed without implying ownership of
work they did not create.

## Rights, permissions, and contributed material

This contribution guide is not a license or copyright assignment.

Do not submit:

- files copied from another mod without permission;
- game resources that the project has no right to redistribute;
- artwork or screenshots that cannot legally be included;
- translations copied from another person without attribution and permission;
- code whose license is incompatible with the project;
- private correspondence without the sender’s permission;
- personal information;
- leaked or unlawfully obtained material.

By opening a pull request, you confirm that:

- you created the contribution or have the right to submit it;
- you have disclosed relevant third-party sources and license terms;
- the project may review and reproduce the contribution as part of the
  pull-request process;
- accepted material may be distributed as part of the project only under the
  repository’s documented permission and licensing terms.

If the project’s redistribution or licensing status does not permit a proposed
contribution to be merged, maintainers may keep the issue open while seeking
permission or may ask for a clean-room replacement.

No contributor is required to transfer ownership merely by participating.
Specific future licensing terms must be documented transparently.

## Community conduct

Be respectful and focus discussion on the work.

- Critique code, design, or documentation rather than people.
- Explain disagreement with evidence and alternatives.
- Do not harass contributors or pressure the original author.
- Do not claim that inactivity invalidates another person’s authorship.
- Avoid entitlement toward volunteer maintainers, translators, and testers.
- Give contributors a reasonable opportunity to correct mistakes.
- Keep public discussion free of private or identifying information.

Maintainers may close contributions that are abusive, legally problematic,
unrelated to the project, or incompatible with its documented purpose.
