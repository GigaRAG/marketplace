# GigaRAG for Claude Code

[GigaRAG](https://gigarag.com) is a knowledge base your AI tools can read and write: memos, in threads, in buckets, searchable, with links between them.

This repository is the plugin marketplace Claude Code installs from. It holds a manifest and this note, and no code. The plugin itself comes from npm.

## Install

```
claude plugin marketplace add gigarag/marketplace
claude plugin install gigarag@gigarag --scope user
```

Then sign in, which opens your browser:

```
gigarag login
```

## What you get

Five commands, a subagent and three hooks.

| Command | Does |
|---|---|
| `/gigaindex [path]` | Index a codebase into a bucket |
| `/gigasync` | Re-index only what changed since the last run |
| `/gigasave [focus]` | Write this session's decisions into memos |
| `/gigarecall <query>` | Search, read the best hits, answer with references |
| `/gigadocs <url>` | Ingest external documentation |

Every session starts with an index of your memos, and files you edit are re-indexed in the background.

To connect a tool other than Claude Code, see [gigarag.com/connect](https://gigarag.com/connect), which covers 99 of them.

## Why this is a repository of its own

`claude plugin marketplace add owner/repo` clones the whole repository onto the installer's machine. Keeping the manifest here means an install downloads two files rather than the plugin's source tree, and the source stays in its own repository.

The entry pins no version, so a release never changes this file and an install always gets the current package.
