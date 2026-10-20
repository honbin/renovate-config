# renovate-config

Shared Renovate preset for consistent dependency updates across repositories.

## Usage

`renovate.json` in each repository:

```json
{ "extends": ["github>honbin/renovate-config"] }
```

Changes here apply to every repository on its next Renovate run.

## Policy

- No automerge: a passing build doesn't guarantee the output is unchanged, so every PR is reviewed.
- Stable (>= 1.0) minor and patch updates are grouped per ecosystem; 0.x updates and majors get their own PRs, since a 0.x minor bump can break.
- Lockfile maintenance runs monthly, separately from regular updates.

Security alerts come from Dependabot alerts, not from this preset.

## Overriding

Settings in a repository's `renovate.json` take precedence over the preset, and its `packageRules` are applied after the preset's.
