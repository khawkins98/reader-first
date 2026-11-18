# Installed-skill checks

18 November 2026. Reader First baseline: `f233671`.
Both skill packages are unchanged. The [README](../README.md#install-and-use) now owns complete
native installation, first invocation, update and removal instructions.

## Conditions

Testing used disposable Git projects outside the source repository, with a
fictional Python text-preview tool and complete copies of
`documentation-refactoring` and `contribution-conventions`. A third package,
Journey First, helped check that removal preserved unrelated installations.
No personal skill directories or credential settings were changed.

| Check | Actual outcome |
| --- | --- |
| Native README commands | Executed for both skill names in both `.agents/skills` and `.claude/skills`; every file, reference, reused notice and licence matched the selected source package |
| Existing-copy guard | Repeating the copy refused without overwriting or creating a nested folder |
| Codex 0.167.0 discovery | Isolated app-server discovery listed both packages enabled at repository scope without package errors |
| Codex explicit task | A read-only session invoked both skills, reviewed an actual synthetic README diff and drafted a Conventional Commit PR title and description; it read installed style, expert-map and upstream type references |
| Claude Code 2.1.322 discovery | Startup registered both names as skills and slash commands in the disposable project |
| Claude task execution | The account's weekly usage limit blocked the attempted task; this does not establish successful execution of either Reader First skill in Claude |
| Skills CLI 1.9.0 install | Local-source copies for both agents retained the full packages; a separate GitHub install of documentation-refactoring also succeeded |
| Remote update checks | `check` and selected-name `update -p -y` fetched the public repository and reported it up to date; no changed remote revision was needed or tested |
| Local update boundary | Local-source installations were skipped by `check` and `update`; repeating `add` refreshed an installed package instead |
| Selected removal | Removing Journey First by name cleared its two agent copies and preserved both Reader First packages byte for byte |
| One-off use | `use khawkins98/reader-first@documentation-refactoring` prepared a prompt without changing the disposable project's working tree; it did not launch a model session |

Codex discovery used a temporary configuration directory without a model request.
The task run reused normal authentication, ignored user configuration and used a
read-only sandbox. The two skills were invoked together, so this is not a
separate first-use execution result for each. The fictional tool was inspected
statically; its program was not run and no repository edits or remote writes were
made by the model. Claude used project settings, read/skill tools, no MCP servers
and no persistent session. Startup registration was inspected as metadata; its
interactive menu was not visually exercised.

## Documentation decision and limits

Native copy instructions now give the target working directory, scope and
complete-folder boundary. Both skills remain independently selectable. Optional
CLI guidance stays available and distinguishes local refresh from supported
remote update checks. Existing origin, before/after example, author credits,
licensing and one-off use remain at the entrance. No new installer, platform
adapter or universal skill instruction was justified.

Personal-scope installation, implicit selection, successful Claude execution,
interactive selectors and a changed-remote update were not exercised. Remote
installation used the public Reader First repository; companion Journey First
checks used an authenticated checkout of its private repository. These are local
installation smoke checks, not a general effectiveness or human usability study.
Raw CLI output and synthetic workspaces remain in untracked local test storage;
no credentials or model transcript are distributed in this repository.

## Red-team follow-up

A fresh reviewer reproduced a failed-target-directory case in the original copy
example: after `cd` failed, the remaining commands installed into the caller's
current directory and returned success. The example now chains directory change,
directory creation, destination guards and copy, and quotes the target path.
A failed directory change stops installation. The original positive checks above
did not cover this case; this follow-up records the added coverage.

The revised README blocks were executed for all three companion packages in both
agent directories, using disposable source and target paths containing spaces.
Complete package bytes matched; repeated copies, existing files, broken symlinks
and directory symlinks were refused without altering their contents or targets.
Missing target directories returned failure and wrote no installation in the
caller's directory. No personal installations or model calls were needed for
these command checks. No additional correctness blocker was identified.
