# Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)

## Current behavior

When I set a gitlab include to version `6.1`, Renovate will come to propose upgrade to full version _3 digits_, for instance `6.2.1`.

- [MR for minor release](https://gitlab.com/guilhemmartin/renovate-omitting-patch-version/-/merge_requests/2) -> 6.2.1
- [MR for patch release](https://gitlab.com/guilhemmartin/renovate-omitting-patch-version/-/merge_requests/1) -> 6.1.11  

## Wished behavior

When I set include version to `6.1`, I would like that renovate proposes upgrade to 2 digits version like `6.2` or `7.0` (in case there's a new major release), and not adding a patch version like `6.2.2`.

## Link to the Renovate issue or Discussion

Discussion [36650](https://github.com/renovatebot/renovate/discussions/36650)
