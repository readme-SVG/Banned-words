[![readme-SVG/Banned-words](https://raw.githubusercontent.com/OstinUA/Image-storage/main/readme/Banned-words/readme-SVG-Banned-words_readme.png)](https://github.com/OstinUA)

---

A curated collection of banned words in multiple languages.

This repository is designed for teams who want to automatically detect and block unwanted words in pull requests, commits, issue comments, chat pipelines, or any custom moderation workflow.

## What this repository contains

- Language-specific text files under `Banned-words-list/`.
- One banned word per line (plain `.txt` format).
- Files that can be used directly in scripts, CI jobs, bots, and repository governance tools.

## Available languages

The repository includes separate files for many languages (for example: Arabic, Czech, French, Italian, Japanese, Russian, Ukrainian, and others).

Browse all lists in:

<!-- WORD_TABLE_START -->
| File | Language | Words |
| --- | --- | ---: |
| `ar.txt` | Arabic | 58 |
| `bn.txt` | Bengali | 33 |
| `cs.txt` | Czech | 41 |
| `da.txt` | Danish | 20 |
| `de.txt` | German | 66 |
| `el.txt` | Greek | 48 |
| `emoji.txt` | emoji.txt | 151 |
| `en.txt` | English | 3267 |
| `eo.txt` | eo.txt | 37 |
| `es.txt` | Spanish | 520 |
| `fa.txt` | Persian | 45 |
| `federal_government.txt` | federal_government.txt | 381 |
| `fi.txt` | Finnish | 130 |
| `fil.txt` | fil.txt | 13 |
| `flags_all.txt` | flags_all.txt | 267 |
| `fr.txt` | French | 100 |
| `ga.txt` | Irish | 16 |
| `gu.txt` | Gujarati | 31 |
| `he.txt` | Hebrew | 49 |
| `hi.txt` | Hindi | 119 |
| `hu.txt` | Hungarian | 96 |
| `id.txt` | Indonesian | 68 |
| `it.txt` | Italian | 168 |
| `ja.txt` | Japanese | 180 |
| `kab.txt` | kab.txt | 21 |
| `kn.txt` | Kannada | 29 |
| `ko.txt` | Korean | 72 |
| `ms.txt` | Malay | 31 |
| `nl.txt` | Dutch | 190 |
| `no.txt` | no.txt | 40 |
| `pl.txt` | Polish | 54 |
| `pt.txt` | Portuguese | 76 |
| `ru.txt` | Russian | 4249 |
| `sv.txt` | Swedish | 43 |
| `test.txt` | test.txt | 29 |
| `th.txt` | Thai | 31 |
| `tlh.txt` | tlh.txt | 3 |
| `tr.txt` | Turkish | 142 |
| `ua.txt` | ua.txt | 136 |
| `vi.txt` | Vietnamese | 31 |
| `zh.txt` | Chinese | 335 |
<!-- WORD_TABLE_END -->

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
