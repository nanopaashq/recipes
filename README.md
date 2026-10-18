# nanopaashq/recipes

Official NanoPaaS recipes. A recipe is a project you can start from or deploy as is: a folder with a `nanopaas.json` that carries a `recipe` block (name, version, description, and the blanks you fill in, such as an admin IP range or a database choice), plus the app's code, an optional Dockerfile, seed data, and a test suite.

Status: empty. The first three recipes are the plan's success apps (a CRUD app on SQLite, WordPress on MariaDB, and Django with a Next.js frontend), added when the recipes unit lands (W23.24, Phase 3). The format is defined in [ADR 0041](https://github.com/nanopaashq/nanopaas/blob/main/docs/adr/0041-recipes.md).

Layout once populated:

```
<recipe-name>/
  nanopaas.json      # manifest with its recipe block
  README.md
  ...                # the app
index.json           # the list the CLI searches (`nanopaas recipe ls`)
```

Use one with `nanopaas init --recipe github.com/nanopaashq/recipes#<recipe-name>`. Your copy is yours: after `init`, nothing links it back to this repository.

Rules for every recipe here: no secret values (key names only), refs are pinned by commit when indexed, and each recipe passes `nanopaas recipe validate` and `nanopaas recipe test` in CI before it is listed.

Licensed under either of [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE), at your option.
