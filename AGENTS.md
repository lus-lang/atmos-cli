# AGENTS.md

This repository, `lus-lang/atmos-cli`, is the `cli` package of the atmosphere registry. Programs load it with `require("https://atmosp.here/2.0/cli.lus")`.

## Scope

Parses command line arguments into commands, options, and arguments, in the manner of commander. The public API is every function that `cli.lus` returns in its module table. A change to that API needs a new entry in `CHANGELOG.md` and a version change in the header.

## Layout

- `cli.lus` is the whole package. Its header doc comment carries the package metadata and the declared permissions.
- `tests/*_test.lus` are the tests. They load the package from the parent directory through `TEST_DIR`.

## Dependencies

None.

## Commands

```sh
lus test tests          # run the tests
lus check cli.lus     # lint
lus doc cli.lus       # print the reference
```

## Rules

- Every public function has a doc comment that states each result and each error, following `spec/design/style.md` of the Lus repository.
- The package never calls `pledge`. A new permission is declared in the header and in the README.
- Prose has no dashes and no semicolons, and never names the Roblox Lua dialect.
- Every bug fix comes with a test that fails without it.
