# Reader First

Two highly opinionated agent skills for contributions and documentation.

I made these because I kept giving AI agents the same brief on every project,
then cleaning up the results. They capture how I like to work so I can reuse
those preferences instead of explaining them again.

| Skill | Use it for |
| --- | --- |
| [contribution-conventions](skills/contribution-conventions/SKILL.md) | My contribution defaults: Conventional Commits, focused PRs, and no unsolicited AI co-author trailers or tool signatures. |
| [documentation-refactoring](skills/documentation-refactoring/SKILL.md) | The more broadly useful one: separate reader tasks, keep explanations in maintained homes, fix stale guidance and give prose a light style pass. |

Use either skill on its own or adapt it to your project. Project and user
instructions take precedence over my defaults. Neither skill grants permission
to push, publish or merge.

The foundations belong to their authors: **Daniele Procida (Diátaxis), GitHub and
awesome-copilot contributors, Samuel Berthe, Leonardo Flores / Softaworks,
William Strunk Jr., Google, Anthropic, Siqi Chen (Humanizer), AminBlg
(SimpleEnglish), dmythro and the Conventional Commits contributors**.
The [source and reuse records](SOURCES.md) credit each contribution and distinguish
inspiration, adaptation and direct reuse.

## Before and after

From this README:

**[Before](https://github.com/khawkins98/reader-first/blob/6d937cfcc60c923ba5a35920f67e45884f9b3e3d/README.md)**

> A curated, mixture-of-experts-style collection of agent skills for maintaining
> repository documentation. It brings together established specialists in document
> structure, audience, prose, reader review and contribution conventions, with a
> small layer for selecting and applying their methods to a project.

**[After](https://github.com/khawkins98/reader-first/blob/a25afe268fbcafa940b302902927af851c23cacf/README.md)**

> Two highly opinionated agent skills for contributions and documentation.

## Install and use

Use an installed, signed-in Claude Code or Codex that supports skills. The manual
commands below use Git and a macOS/Linux shell; on Windows, copy the same complete
folders with your file manager or equivalent shell commands. Node.js is needed
only for the optional Skills CLI route.

### Install a selected skill

1. Clone this public repository somewhere you keep tool checkouts:

   ```sh
   git clone https://github.com/khawkins98/reader-first.git
   ```

2. Choose your agent and installation scope. Project scope makes the skill
   available in that repository; personal scope makes it available across your
   projects. These are the native locations documented for
   [Claude Code](https://code.claude.com/docs/en/skills#choose-where-skills-load)
   and [Codex](https://learn.chatgpt.com/docs/build-skills).

   | Agent | Project directory | Personal directory |
   | --- | --- | --- |
   | Claude Code | `.claude/skills` | `~/.claude/skills` |
   | Codex | `.agents/skills` | `~/.agents/skills` |

3. From the repository you want to work on, copy one complete skill folder.
   Replace both absolute paths below. Set `skills_dir` to your chosen location;
   for personal scope use, for example, `"$HOME/.agents/skills"`. Set
   `skill_name` to `contribution-conventions` to install that skill instead, or
   repeat the copy for both.

   ```sh
   reader_first_checkout="/absolute/path/to/reader-first"
   skill_name="documentation-refactoring"
   skills_dir=".agents/skills"
   cd "/absolute/path/to/target-repository" &&
     mkdir -p "$skills_dir" &&
     test ! -e "$skills_dir/$skill_name" &&
     test ! -L "$skills_dir/$skill_name" &&
     cp -R "$reader_first_checkout/skills/$skill_name" "$skills_dir/$skill_name"
   ```

   The copy stops if the target directory is missing or that name already exists.
   Inspect the existing installation before replacing it. Copy the entire selected
   folder, including `references`,
   licence texts and notices; copying only `SKILL.md` loses required material.

### Verify and run a first task

Start a new agent session in the target repository after installation. In Claude
Code, type `/` and confirm the installed skill appears. In Codex, type `$` to
select it. If it is missing, check the scope, folder name and
`<skills directory>/<skill name>/SKILL.md`, then restart the session. If another
copy has the same name, inspect the project and personal locations before
choosing which to keep.

Send one of these complete requests. The first reviews a README; the second
prepares contribution text for an existing diff.

| Task | Claude Code request | Codex request |
| --- | --- | --- |
| Improve a README | `/documentation-refactoring Improve README.md for a first-time reader. Keep setup working, preserve required technical detail and verify the reader paths. Report changes and checks.` | `$documentation-refactoring Improve README.md for a first-time reader. Keep setup working, preserve required technical detail and verify the reader paths. Report changes and checks.` |
| Prepare a contribution | `/contribution-conventions Prepare a PR title and description for the current diff, following this repository's contribution rules. Report the checks run. Do not commit or publish.` | `$contribution-conventions Prepare a PR title and description for the current diff, following this repository's contribution rules. Report the checks run. Do not commit or publish.` |

Check that the agent loads the selected skill before assessing the result. Both
skills are independently useful and self-contained; each linked expert map
explains its specialist perspectives. The skills provide instructions, and the
agent still needs access to the files and tools required by your task.

### Update or remove an installation

For a manual installation, update your Reader First checkout with `git pull`
from that checkout. Back up any local edits in the installed skill, remove only
that selected skill folder from the location you chose, then repeat the complete
folder copy. Review the new version before adopting it. Updating the checkout
alone does not update a copied installation.

To uninstall, remove only the selected skill folder from that project or personal
skills directory. Leave unrelated skills in place and start a new agent session.
If the skill remains available, check for another copy in the other scope.

### Optional: use the Skills CLI

With Node.js 22.20 or later, run the
[Skills CLI](https://github.com/vercel-labs/skills#install-a-skill) from your target
repository. It prompts for your agent and installs into that project by default.
Add `-g` for personal scope. Install either skill or run both commands:

```sh
npx skills@1.9.0 add khawkins98/reader-first --skill documentation-refactoring
npx skills@1.9.0 add khawkins98/reader-first --skill contribution-conventions
```

To use a local Reader First checkout, replace `khawkins98/reader-first` with its
path. Verify discovery and invoke the skill as above. For installations from a
supported, tracked remote source, `npx skills@1.9.0 check` checks for updates and
`npx skills@1.9.0 update documentation-refactoring` updates that skill. These
commands do not update installations added from a local checkout: review and
update that checkout, back up local edits in the installed copy, then repeat the
same `add` command.

Use `npx skills@1.9.0 remove documentation-refactoring` to remove that skill.
Substitute `contribution-conventions` for the other skill. Match the original
project or personal scope; check each command's `--help` for scope options and
review its selection before changing installed skills.

To try once without installing the skill into your project:

```sh
npx skills@1.9.0 use khawkins98/reader-first@documentation-refactoring
```

This prepares temporary skill files and prints a prompt for a local agent. See
the [command reference](https://github.com/vercel-labs/skills/blob/main/docs/commands.md#skills-use)
for options to launch an agent directly.

## Develop the skills

[CONTRIBUTING](CONTRIBUTING.md) covers edits, validation and source reuse.
The [evaluation index](evals/README.md) links runnable scenarios and application
records with their checks, interventions and limitations. Syntax checks and these
same-project trials do not establish general effectiveness.

## License

Original prose uses [CC BY 4.0](LICENSE); code, executable fixtures and code/command
examples use [MIT](LICENSE-MIT). The [licence map](LICENSING.md) defines the split.
Third-party material retains its [upstream terms](THIRD_PARTY_NOTICES.md), and each
installable skill carries its own licence map and both full texts.
