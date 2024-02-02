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

## Create a Repository

Create a new repository from scratch
: `git init [project name]`

Download from an existing repository
: `git clone repo_url`

## Observe a Repository

Status
: `git status`

> Useful options:
> - `-s`: Short format.
> - `-b`: Show the branch.

Log
: `git log`

> Useful options:
> - `--format=<format>`: Pretty-print in a given format, where <format> can be one of oneline, short, medium, full, fuller, reference, email, raw.
> - `--format="<options>"`: Pretty-print in a user defined format.
> - `--abbrev-commit`: Show reduced hash.
> - `--oneline`: Shortand for `format=oneline --abbrev-commit`.
> - `--graph`: Show graph.
> - `--author <name>`: Filter commits by author.
> - `--committer <name>`: Filter commits by committer.
