# Changelog

[README](README.md) ·
[Changelog](CHANGELOG.md) ·
[Contributing](CONTRIBUTING.md) ·
[Contributors](CONTRIBUTORS.md) ·
[Maintenance notice](MAINTENANCE-NOTICE.md)

All notable changes to **BG2:EE Unofficial Item Pack** are documented in this
file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

Future community releases should use
[Semantic Versioning](https://semver.org/spec/v2.0.0.html) once a stable
versioning policy has been established. Historical versions retain the labels
chosen by the original author, including `2.7b`.

> [!NOTE]
> The historical section was reconstructed from surviving release
> announcements, forum posts, archive names, and community reports.
>
> Some historical announcements identify only a month rather than a precise
> release day. In those cases, this changelog uses `YYYY-MM` rather than
> inventing a day.
>
> Historical notes may therefore be incomplete. Corrections supported by an
> original archive, release note, or dated forum post are welcome.

## [Unreleased]

### Added

- Established the GitHub repository as a public workspace for preservation,
  documentation, issue tracking, and community maintenance.
- Added `README.md` with installation information, component descriptions,
  item previews, compatibility notes, credits, and project links.
- Added `CONTRIBUTING.md` with contribution, testing, translation, and
  pull-request guidance.
- Added `CONTRIBUTORS.md` to preserve original authorship and record community
  contributions.
- Added `MAINTENANCE-NOTICE.md` to document the purpose and limits of the
  community-maintained continuation.
- Added this reconstructed historical changelog by the name of `CHANGELOG.md`.

### Changed

- Adopted version `2.7b` as the historical baseline for future maintenance.
- Separated information about the mod from repository governance and
  maintenance policy.

## Historical releases

## [2.7b] - 2017-11-08

### Fixed

- Corrected a number of typographical errors.
- Corrected a small number of item-related problems.
- Incorporated the final small maintenance changes publicly attributed to the
  `2.7b` package.

### Notes

- This is the latest publicly surviving release of the original mod found
  during the repository’s initial historical review.
- A larger version `3.0` was discussed by the original author, but no public
  `3.0` release has been identified.
- Future community work should preserve an unmodified copy or Git tag of this
  version as the historical baseline.

## [2.7] - 2016-09

### Added

- Added the optional **Reworked Free Action** component.
- Added **Kangaxx’s Robe** for evil-aligned arcane characters.

### Changed

- Revised selected Free Action items so that their protective effects no
  longer prevent characters from benefiting from haste effects.

### Notes

The Reworked Free Action component affected:

- Firecam Plate;
- Ixil’s Spike +6;
- Flail of Ages +5;
- Ring of Free Action.

## [2.6] - 2016-09

### Added

- Added **Key Ring** as a new drop from Ilyich.
- Added **Cloak of Balduran** as a new drop from Firkraag.
- Added **Hourglass of Gond** as a reward connected to a difficult hidden
  encounter.
- Added **Headband of Focus**.
- Added **Helm of Opposite Alignment**.
- Added **Girdle of Femininity/Masculinity**.
- Added **Ring of Superior Arcane Clumsiness**.
- Added **Bracers of the Blinding Strike** as a new drop from Drizzt.
- Added a difficult hidden encounter associated with one of the new rewards.

### Fixed

- Corrected problems affecting **Stalker Gauntlets**.
- Corrected problems affecting **Nimblefinger Gloves**.

## [2.5] - 2016-07

### Added

- Added **Daeros’ Full Plate +1**.
- Added **Guenhwyvar’s Figurine** as a new drop from Drizzt.
- Added **Tongue of Acid +3** as a new drop from Thaxll’ssillyia.
- Added **Silver Dragon Scales** as a new drop from Adalon.

### Fixed

- Corrected a problem affecting the new crossbow bolts.

### Removed

- Temporarily removed **Key Ring** after it was found to cause a game freeze.

## [2.0] - 2016-06

### Added

- Added **Girdle of Fortitude** to the reworked item selection.
- Added **Blackmist +4** to the reworked item selection.
- Added the optional **New Items** component.
- Added the optional **Siege of Dragonspear Items** component.
- Added the optional **Better Archery Shop** component.
- Added selected original items and rewards.
- Added selected equipment imported from *Siege of Dragonspear*.
- Added elemental bullets and bolts to the relevant archery merchant.

## [Initial public release] - 2016-05-09

### Added

- Released the first public version of **BG2:EE Unofficial Item Pack**.
- Added a modular WeiDU installation for *Baldur’s Gate II: Enhanced Edition*.
- Added reworks for underused, overlooked, and quest-related BG2:EE items.
- Added the **Scarlet Katana** component.
- Added the **Gourmet from Underdark** component.
- Added the **Holy Symbols** component.
- Added English and Czech text.

## Historical sources

- [Original Beamdog forum post and component list](https://forums.beamdog.com/discussion/56567/mod-bgii-ee-unofficial-item-pack/p1)
- [Beamdog discussion, page 5](https://forums.beamdog.com/discussion/56567/mod-bgii-ee-unofficial-item-pack/p5)
- [Beamdog discussion, page 6](https://forums.beamdog.com/discussion/56567/mod-bgii-ee-unofficial-item-pack/p6)
- [Beamdog discussion, page 9](https://forums.beamdog.com/discussion/56567/mod-bgii-ee-unofficial-item-pack/p9)
- [Beamdog discussion, page 10](https://forums.beamdog.com/discussion/56567/mod-bgii-ee-unofficial-item-pack/p10)

## Changelog maintenance rules

When preparing a pull request:

1. Add user-visible changes to the `[Unreleased]` section.
2. Use one of the standard headings where applicable:
   - `Added`;
   - `Changed`;
   - `Deprecated`;
   - `Removed`;
   - `Fixed`;
   - `Security`.
3. Describe the effect on players or modders rather than listing commit
   messages.
4. Do not create a new release heading inside a normal pull request unless the
   maintainer is preparing a release.
5. Preserve historical entries unless documentary evidence proves that a
   correction is necessary.
6. Link important compatibility changes to their GitHub issue or pull request
   when possible.