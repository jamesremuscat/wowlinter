# wowlint
## Linter for Words of Worship resource files

[![Build Status](https://travis-ci.org/jamesremuscat/wowlint.svg?branch=master)](https://travis-ci.org/jamesremuscat/wowlint)
[![Coverage Status](https://coveralls.io/repos/github/jamesremuscat/wowlint/badge.svg?branch=master)](https://coveralls.io/github/jamesremuscat/wowlint?branch=master)

[Words of Worship](http://www.wordsofworship.com) is a popular tool for
projecting song lyrics, liturgy and other textual media in churches and houses
of worship.

`wowlint` aims to provide a mechanism to assure quality and consistency of
the song and liturgy resource files, by automatically verifying things like:

 - Lines start with a capital letter
 - Copyright and author information is provided
 - Lines do not have trailing punctuation

The validation criteria are unashamedly based on the house style of
[St Aldates Church](https://github.com/staldates).

## Basic usage

```shell
$ wowlint [ options ] /path/to/some/wow/files/*.wow-song
```
For help with options, run:

```shell
$ wowlint --help
```

## Configuration

Per-lint configuration is possible by creating a `wowlintrc.yml` file in the
directory from which you run `wowlint`. This should be a YAML file with lint
names as keys and per-lint configuration as values.

All lints accept the `exclude` key, which should be a list of filenames to be
excluded from that lint. For example, to exclude the `test.wsg` file from the
`NoAuthorProvided` lint, your `wowlintrc.yml` should contain:

```yaml
NoAuthorProvided:
  exclude:
    - "test.wsg"
```

## Limitations

Currently this project is very young, and:
 - Only song files (`.wsg` and `.wow-song`) are supported
 - There's no way to specify custom validation or disable entire rules
 - Automating the running of `wowlint` is left as an exercise for the user

# Contributions

Contributions welcome: please fork the project and submit a pull request.
