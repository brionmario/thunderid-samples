# ThunderID Samples

Ready-to-run sample apps for ThunderID. Each sample is a standalone project that depends on
the published release of its SDK, so it runs on its own once copied out of this repository.

## Layout

Samples live at `<area>/<sample>`:

| Area | Holds |
|---|---|
| `quickstarts` | The minimal app per platform that the ThunderID docs quickstarts walk through |
| `integrations` | ThunderID used through a third-party library, such as Better Auth or flutter_appauth |
| `self-care` | Apps built on ThunderID's self-service features |
| `b2b` | Apps where an administrator manages an organization's ThunderID resources |

Each sample is released on its own, as a source zip tagged `sample/<area>/<sample>/v<version>`.
`.github/workflows/release.yml` builds the release and `pr-builder.yml` builds every sample
on a pull request.

## Where to look next

| Working on… | Read |
|---|---|
| Adding a sample, or creating or updating a README banner | [.agent/skills/sample-banner/SKILL.md](.agent/skills/sample-banner/SKILL.md) |

## Adding a sample

- Put it under the area it belongs to and give it a `README.md` that starts with its banner.
  Follow the sample-banner skill to render the banner and reference it.
- Depend on the published SDK release, never a workspace or local path.
- Add a row to the table in the root `README.md`.
- Keep its manifest (`package.json`, `pubspec.yaml`, `settings.gradle.kts`, or
  `Package.swift`) at the sample root. The pull request builder finds samples by that file
  at exactly `<area>/<sample>/`.

## Rules

- Always write `ThunderID`. Never use a bare `thunder`, `Thunder`, or `THUNDER` as a short
  form of the product name. Package names and identifiers such as `@thunderid/react` and
  `thunderid_flutter` are fine.
- No em dashes and no double hyphens in READMEs or UI copy. Use a comma or a period.
- Keep changes focused on the task. Do not refactor unrelated samples.
- Commit messages are short imperative sentences without conventional commit prefixes.
