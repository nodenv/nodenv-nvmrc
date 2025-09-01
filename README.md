# nodenv-nvmrc

A [nodenv][] plugin to activate Node version from `.nvmrc`.

[![Tests](https://img.shields.io/github/actions/workflow/status/nodenv/nodenv-nvmrc/test.yml?label=tests&logo=github)](https://github.com/nodenv/nodenv-nvmrc/actions/workflows/test.yml)
[![Latest GitHub Release](https://img.shields.io/github/v/release/nodenv/nodenv-nvmrc?label=github&logo=github&sort=semver)](https://github.com/nodenv/nodenv-nvmrc/releases/latest)
[![Latest Homebrew Release](<https://img.shields.io/badge/dynamic/regex?label=homebrew-nodenv&logo=homebrew&logoColor=white&url=https%3A%2F%2Fraw.githubusercontent.com%2Fnodenv%2Fhomebrew-nodenv%2Frefs%2Fheads%2Fmain%2FFormula%2Fnodenv-nvmrc.rb&search=archive%2Frefs%2Ftags%2Fv(%3F%3Cversion%3E%5Cd%2B.*).tar.gz&replace=v%24%3Cversion%3E>)](https://github.com/nodenv/homebrew-nodenv/blob/main/Formula/nodenv-nvmrc.rb)
[![Latest npm Release](https://img.shields.io/npm/v/@nodenv/nodenv-nvmrc?logo=npm&logoColor=white)](https://www.npmjs.com/package/@nodenv/nodenv-nvmrc/v/latest)

This is a plugin for [nodenv](https://github.com/nodenv/nodenv)
that detects the node version based on the current tree's .nvmrc. `.node-version` files still take precedence.

When .nvmrc is configured with a range this plugin chooses the greatest installed version matching the range or exits with an error if none match.

## Installation

### Installing with git

```sh
$ git clone https://github.com/nodenv/nodenv-nvmrc.git $(nodenv root)/plugins/nodenv-nvmrc
```

### Installing with Homebrew

Mac OS X users can install [many nodenv plugins](https://github.com/nodenv/homebrew-nodenv) with [Homebrew](http://brew.sh).

*This is the recommended method of installation if you installed nodenv with
Homebrew.*

```sh
$ brew tap nodenv/nodenv
$ brew install nodenv-nvmrc
```

## Usage

Once you've installed the plugin you can verify that it's working by `cd`ing into a project that has a `.nvmrc` file and does not have a `.node-version` file.  From anywhere in the project's tree, run `nodenv which node`.

## Gotcha

Due to the limitaion of nodenv's plugin system, some commands were not reading the version from `.nvmrc`.
- `nodenv install` without version is not able to install new Node version specified in `.nvmrc`.
- `nodenv local` without version is not able to retrieve the version specified in `.nvmrc`

## Contributing

To run tests, install [bats](https://github.com/sstephenson/bats) and [nodenv](https://github.com/nodenv/nodenv), then run `bats test`  in the base directory of this plugin

## Credits

This project is heavily inspired by nodenv-package-json-engine[[1]](https://github.com/nodenv/nodenv-package-json-engine).

Shell semver range support provided by [sh-semver](https://github.com/qzb/sh-semver).

[nodenv]: https://github.com/nodenv/nodenv
