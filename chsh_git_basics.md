# Git Basics

* TOC (placeholder for the automatic creation of a Table of contents)
{:toc}

## Getting help

Equivalent ways to get the comprehensive manual page (manpage) help for any of the Git commands:

- `git help <verb>`
- `git <verb> --help`
- `man git-<verb>`

Quick help:

- `git <verb> -h`


## Configuration

List all settings:
: `git config --list`

List all settings and where they are coming from:
: `git config --list --show-origin`

Check specific config:
: `git config {property}`

Set a setting:
: `git config --[system | goblal | local] propertyName propertyValue`
: Example: `git config --global user.name "Xuan Roces"`

Important properties:

- `user.name`
- `user.email`
- `core.editor`
- `init.defaultBranch`

