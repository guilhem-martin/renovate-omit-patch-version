# Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)

## Current behavior

- `github-actions.yml`: Renovate proposes to [migrate v3 action checkout to v4: preserves the major version digit only](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:588).
- `pom.xml`: Renovate proposes to migrate from `6.1` to `6.1.21` (for [patch update](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:678)) and from `6.1` to `6.2.8` (for [minor update](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:692) ; in both cases it adds a patch version, turning the 2 digits version into a 3 digits version.
- `github-actions.yml`: Renovate proposes to [migrate v43.0.0 renovate bot to v43.0.1: preserves the major.minor.patch 3 digits version](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:624).

## Wished behavior

When I set include version to `6.1`, I would like that renovate proposes upgrade to 2 digits only, not adding patch version.
So for a minor update, it would propose `6.2` instead of `6.2.8`, and for a patch update, it would not propose any new version, keeping the current version `6.1`.

That would be homogeneous with the behavior of the 1 digit version, where Renovate proposes to upgrade `v3` to `v4` (nor `v4.0.0`, neither `v4.0`).

## Link to the Renovate issue or Discussion

Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)
