# Structure & Responsibilities

**Date**: 2026-07-31

## Top-level Folder Responsibilities

| Folder          | Purpose                                      | What belongs here                              | What does NOT belong here                     |
|-----------------|----------------------------------------------|------------------------------------------------|-----------------------------------------------|
| `vibe-unpack/`  | The actual development subject (core)        | SKILL.md, design docs, examples, templates, core logic | General project planning, external references |
| `docs/`         | Project-level documentation                  | Product planning, process, architecture, handover, operations | The core skill definition and its examples    |
| `references/`   | External material for learning & inspiration | Full clones of reference projects + indexes    | Our own design docs or examples               |
| `archive/`      | Discarded / historical / experimental        | Old versions, dead experiments, deprecated material | Anything still actively used                  |

## Why this split

- `vibe-unpack/` must remain the obvious, clean home of the main work.
- We deliberately do **not** put the core skill inside a generic "project documentation" folder.
- References are kept separate so they don't pollute the main development subject.
- Archive exists so we can throw things away without losing history.

## Quick Navigation

- I want to work on the actual skill → go to `vibe-unpack/`
- I want to understand the project direction / history → go to `docs/`
- I want to study external ideas → go to `references/`
- I want to look at old/dead stuff → go to `archive/`
