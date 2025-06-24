# Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)

## Current behavior

With default versioning:

- `github-actions.yml`: Renovate proposes to [migrate v3 action checkout to v4](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:588) preserving the major version format 1-digit only.
- `pom.xml`: Renovate proposes to migrate from `6.1` to `6.1.21` (for [patch update](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:678)) and from `6.1` to `6.2.8` (for [minor update](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:692) ; in both cases it adds a patch version, turning the 2 digits version into a 3 digits version.
- `github-actions.yml`: Renovate proposes to [migrate v43.0.0 renovate bot to v43.0.1](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851512827/job/44685935010#step:3:624) preserving the major.minor.patch 3 digits version.

With `docker` [versioning](https://docs.renovatebot.com/configuration-options/#versioning) applied to `pom.xml` / maven:

- Renovate [does not propose any upgrade](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15860063567/job/44714802776#step:3:656). It's what I want to achieve for patch update (staying on `6.1` i.e. 2 digits version), but I would have wanted it to propose minor update (from `6.1` to `6.2`).

## Wished behavior

When I set the version to `6.1`, I would like that renovate proposes upgrade to 2 digits only, preserving my version format, not adding patch version.
So for a minor update (for a current value of `6.1`), it would propose `6.2` instead of `6.2.8`, and for a patch update, it would not propose any new version, keeping the current version `6.1`.

That would be homogeneous with the behavior of the 1 digit version, where Renovate proposes to upgrade `v3` to `v4` (nor `v4.0.0`, neither `v4.0`).

For instance, we could have an option `keepVersionFormat` and that would keep the version format as it is, without adding digit to the version.

## Link to the Renovate issue or Discussion

Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)
