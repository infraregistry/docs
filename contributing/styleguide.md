---
icon: scale-balanced
---

# Styleguide

## Frontend

* Svelte version is `5.0.0-next.262`.
* `package-lock.json` must be maintained by `npm.`

### `pre-commit` requirements

* `eslint` honoring the rules located [here](https://github.com/infraregistry/spa/blob/999195a0d164506d24e5ff69c7ee0d0b3c4ee8bb/.eslintrc.cjs).
* `prettier` honoring the rules located [here](https://github.com/infraregistry/spa/blob/999195a0d164506d24e5ff69c7ee0d0b3c4ee8bb/.prettierrc).

### Shared Components

Shared components should live under `src/lib/components/`.

### Routes

Routed components should live under `src/pages/<path>/<path>/<path>..`.

## Backend

* Go version is 1.23.0.
* `go fmt` run on very pre-commit.
