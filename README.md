# Math Research Skills

Reusable Codex skills for mathematical research workflows.

## Skills

| Skill | Description |
| --- | --- |
| [`$explain-math-proof-idea`](docs/skills/explain-math-proof-idea.md) | Explains the decisive idea in the proof of one result from a mathematical research paper. |
| [`$learn-math-interactively`](docs/skills/learn-math-interactively.md) | Builds a serious understanding of mathematics through a paced, adaptive dialogue. |
| [`$learn-unfamiliar-math-interactively`](docs/skills/learn-unfamiliar-math-interactively.md) | Builds a usable map of unfamiliar mathematics for researchers entering a new field. |

Follow a skill link for usage examples, supported inputs, output behavior, and limitations. Agent instructions live in the corresponding `.agents/skills/<skill-name>/SKILL.md` file.

## Installation

### Use in this repository

Open this repository in Codex. Every skill under `.agents/skills/` is discovered automatically, including skills added later.

### Install one skill from GitHub

For personal use outside this repository, ask `$skill-installer` to install the directory for the skill you want:

```text
Use $skill-installer to install <skill-name> from
https://github.com/Yoaskay/math-research-skills/tree/main/.agents/skills/<skill-name>
```

Replace `<skill-name>` with a name from the table above. This pattern does not need to change when new skills are added.

### Link all skills for local development

During development, keep this repository as the source of truth and expose every skill globally with symbolic links:

```bash
repo_root="$PWD"
skill_target="$HOME/.agents/skills"

mkdir -p "$skill_target"
for skill_dir in "$repo_root"/.agents/skills/*; do
  [ -d "$skill_dir" ] || continue

  skill_name=$(basename "$skill_dir")
  destination="$skill_target/$skill_name"

  if [ -L "$destination" ]; then
    printf 'skip: symbolic link already exists: %s\n' "$destination"
    continue
  fi

  if [ -e "$destination" ]; then
    printf 'skip: destination already exists: %s\n' "$destination" >&2
    continue
  fi

  ln -s "$skill_dir" "$destination"
done
```

The loop automatically includes skills added later. It reports and skips any existing symbolic link, file, or directory instead of following or overwriting it. Inspect the links with:

```bash
for skill_dir in "$repo_root"/.agents/skills/*; do
  [ -d "$skill_dir" ] || continue

  skill_name=$(basename "$skill_dir")
  destination="$skill_target/$skill_name"

  if [ -L "$destination" ]; then
    ls -ld "$destination"
    readlink "$destination"
  else
    printf 'not linked: %s\n' "$destination" >&2
  fi
done
```

Codex supports repository-scoped skills under `.agents/skills/`, personal skills under `$HOME/.agents/skills/`, and symlinked skill directories. See the [official OpenAI documentation](https://learn.chatgpt.com/docs/build-skills).

### Distribution

A custom installer is not currently necessary: repository discovery, `$skill-installer`, and the generic symlink loop cover development and individual installation without a per-skill command list. If this collection is distributed broadly, package the skills as a Codex plugin rather than growing a repository-specific installer. Plugins are the recommended distribution mechanism for reusable collections of skills.

## Evaluation

Each skill's evaluation cases and scoring rubric live under `evals/<skill-name>/`. Validate each directory under `.agents/skills/` with the `quick_validate.py` script bundled with OpenAI's `skill-creator`.

## Contributing

Keep each change tied to a reproducible prompt. Update the relevant `SKILL.md`, add or revise a case under `evals/<skill-name>/`, run structural validation, and forward-test the changed behavior on raw source material.

Do not commit downloaded papers or copied TeX sources. Use public identifiers or minimal synthetic fixtures.

When adding a skill:

1. Add `.agents/skills/<skill-name>/SKILL.md` and its optional resources.
2. Add `docs/skills/<skill-name>.md` for user-facing usage and limitations.
3. Add `evals/<skill-name>/`.
4. Add one row to the skills table above.

## License

MIT
