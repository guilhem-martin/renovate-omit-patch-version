# Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)

## Current behavior

### With default versioning:

| File | Update Type | Current Version | Proposed Version | Version Format Behavior |
|------|-------------|-----------------|------------------|------------------------|
| `github-actions.yml` | Major | v3 | [v4](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:588) | Preserves 1-digit format |
| `pom.xml` | Patch | 6.1 | [6.1.21](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:678) | Adds patch version (2→3 digits) |
| `pom.xml` | Minor | 6.1 | [6.2.8](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:692) | Adds patch version (2→3 digits) |
| `github-actions.yml` | Patch | v43.0.0 | [v43.0.1](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:624) | Preserves 3-digit format |

### With `docker` [versioning](https://docs.renovatebot.com/configuration-options/#versioning) applied to `pom.xml` / maven:

| File | Update Type | Current Version | Proposed Version | Version Format Behavior |
|------|-------------|-----------------|------------------|------------------------|
| `pom.xml` | Any | 6.1 | [No upgrade proposed](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15860063567/job/44714802776#step:3:656) | Stays on 2-digit version (desired for patch, but minor update to `6.2` would be wanted) |

## Wished behavior

When I set the version to `6.1`, I would like that renovate proposes upgrade to 2 digits only, preserving my version format, not adding patch version.
So for a minor update (for a current value of `6.1`), it would propose `6.2` instead of `6.2.8`, and for a patch update, it would not propose any new version, keeping the current version `6.1`.

That would be homogeneous with the behavior of the 1 digit version, where Renovate proposes to upgrade `v3` to `v4` (nor `v4.0.0`, neither `v4.0`).

For instance, we could have an option `keepVersionFormat` and that would keep the version format as it is, without adding digit to the version.

## Link to the Renovate issue or Discussion

Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)
