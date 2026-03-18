# Banned Words Lists for Repository Filters

A curated collection of banned words in multiple languages.

This repository is designed for teams who want to automatically detect and block unwanted words in pull requests, commits, issue comments, chat pipelines, or any custom moderation workflow.

## What this repository contains

- Language-specific text files under `Banned-words-list/`.
- One banned word per line (plain `.txt` format).
- Files that can be used directly in scripts, CI jobs, bots, and repository governance tools.

## Available languages

The repository includes separate files for many languages (for example: Arabic, Czech, French, Italian, Japanese, Russian, Ukrainian, and others).

Browse all lists in:

- `Banned-words-list/`

## Format rules

To keep the dataset consistent and automation-friendly, each list should follow these rules:

1. One word per line.
2. No duplicate entries.
3. Use lowercase where applicable.
4. Avoid leading/trailing spaces.

These rules match the contribution guidelines and help keep filters predictable.

## Typical use cases

- Protecting repository discussions from toxic language.
- Enforcing communication policies in open-source projects.
- Pre-commit or CI checks for restricted terms.
- Building moderation bots for multilingual communities.

## Quick start

1. Pick the language file(s) you need from `Banned-words-list/`.
2. Load each file into your filter tool.
3. Compare normalized text (trimmed and lowercased) against the list.
4. Block, flag, or report matches based on your policy.

## Example (pseudo-code)

```text
banned = load_lines("Banned-words-list/en.txt")
input_words = tokenize(user_text)

for word in input_words:
  normalized = lowercase(trim(word))
  if normalized in banned:
    reject("Contains banned word")
```

## Contributing

Contributions are welcome.

Before opening a pull request:

- Read `CONTRIBUTING.md`.
- Ensure the file remains one-word-per-line.
- Remove duplicates.
- Keep words in lowercase where it makes sense for the language.

## Important note

Word lists are context-limited and can produce false positives.
Use them as a baseline signal, and combine them with contextual moderation when possible.
