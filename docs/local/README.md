# Local documentation

Everything in this folder except this README is local-only and must never be pushed.

## What belongs here

- Temporary development notes.
- Local environment details: paths, ports, machine-specific setup.
- Private project notes.
- Sensitive information that must never enter version control.

## What does not belong here

Anything the team needs permanently. Put that in the proper `docs/` folder. This folder is not a substitute for permanent documentation, and it must not be cited as a source of truth.

## How it stays out of Git

- The committed `.gitignore` ignores `docs/local/*` and keeps this README tracked.
- `.git/info/exclude` is not versioned, so it is not inherited when a repository is created from the template. Add the same rule in each clone:

```sh
printf 'docs/local/*\n!docs/local/README.md\n' >> .git/info/exclude
```

- `git add -f` bypasses both. Do not force-add files from this folder.
