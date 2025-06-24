# Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)

## Current behavior


[job example](https://github.com/guilhem-martin/renovate-omit-patch-version/actions/runs/15851335527/job/44685323183)

- github-actions.yml: Renovate proposes to migrate v3 action checkout to v4: OK, preserves the major version digit only.
- github-actions.yml: Renovate proposes to migrate v43.0.0 renovate bot to v43.0.1: OK, preserves the major.minor.patch 3 digits version.



## Wished behavior

When I set include version to `6.1`, I would like that renovate proposes upgrade to 2 digits version like `6.2` or `7.0` (in case there's a new major release), and not adding a patch version like `6.2.2`.

## Link to the Renovate issue or Discussion

Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)
