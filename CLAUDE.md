# CLAUDE.md

## What this repo is

A personal VS Code (and Cursor) **UI customization config** that makes the editor
minimalistic, transparent, and "glassy". It is **not an application** — there is
nothing to build, compile, run, or test. It is a set of CSS stylesheets and JSON
settings that are injected into VS Code's internal Monaco DOM by the
[Custom UI Style+](https://marketplace.visualstudio.com/items?itemName=subframe7536.custom-ui-style)
extension.

## How the pieces fit together

- **`vscode-settings.json`** — the VS Code user `settings.json`. Users copy this
  into `~/Library/Application Support/Code/User/settings.json`. It configures the
  editor, disables most UI backgrounds via `workbench.colorCustomizations`, and
  wires up the Custom UI Style extension.
- **`vscode-styles.css`** — the core stylesheet: transparency/blur, pane split
  lines, cursor color, terminal borders, window-drag fixes, color-shade mixing.
- **`features/*.css`** — modular, **opt-out** feature stylesheets. Each is loaded
  independently so a user can disable one by commenting out its import:
  `tabs`, `terminal`, `explorer`, `command-palette`, `hide-editor-buttons`,
  `project-title-glow`, `focus-glow`.
- **`cursor-styles.css`** — extra overrides specific to the Cursor editor fork.
- **`keybindings.json`** — companion keybindings.
- **`README.md`** — end-user install/customization docs. **`Preview.png`** — screenshot.

### Critical: stylesheets are loaded from GitHub `raw` URLs

`custom-ui-style.external.imports` in `vscode-settings.json` references the CSS
files by **absolute `raw.githubusercontent.com/men232/vscode-config/refs/heads/main/...`
URLs**, with `"loadStrategy": "refetch"`. This means:

- Editing a CSS file locally has **no effect until it is committed and pushed to
  `main`** — the extension fetches the published version, not the working copy.
- **Any new `features/*.css` file must be added to the `imports` array** in
  `vscode-settings.json`, or it will never load.
- Renaming/moving a CSS file requires updating its import URL too.

## Conventions

- **Custom CSS variables use the `--al-` prefix** (author's initials), e.g.
  `--al-transparency-percent`, `--al-tab-height`, `--al-project-icon`. User-tunable
  values are set in the `"body .monaco-workbench"` string inside
  `custom-ui-style.stylesheet` (settings), and consumed with inline fallbacks:
  `var(--al-tab-height, 38px)`.
- **Comment every rule with `/** type(scope) description */`** mirroring the
  conventional-commit style used in git history (`style(...)`, `fix(...)`,
  `feat(...)`, `styles(...)`). Note whether a rule is Cursor-specific.
- **Commit messages** follow conventional commits: `type(scope): message`
  (e.g. `style(explorer): improve title contrast`).
- Modern CSS is used heavily and intentionally: `color-mix()`, `oklch()`,
  relative color syntax (`rgb(from ... r g b / ...)`), and `@property`. Keep to
  these when adding effects.

## Working notes / gotchas

- Selectors target **VS Code's private Monaco DOM** (`.monaco-workbench`,
  `.monaco-editor`, `.part.panel`, `aria-label^="Explorer Section:"`, …). These
  are undocumented and can break on VS Code updates — expect to re-inspect the DOM
  when a version bump breaks a rule.
- Styles are meant to work across themes but are **tuned for the PurpleSchool
  theme**; theme-specific tweaks live under `"[PurpleSchool Theme]"` in settings and
  `[PurpleSchool Theme]` color blocks. Use fallback chains
  (`var(--vscode-terminalCursor-foreground, var(--vscode-editorCursor-foreground))`)
  so other themes degrade gracefully.
- `!important` is often required to beat VS Code's own inline/theme styles.
- Full setup depends on external tooling the user must install: the Custom UI
  Style+ extension, Symbols icon theme, PurpleSchool theme, and the Maple Mono font
  (see `README.md`).

## Typical task workflow

1. Edit the relevant `vscode-styles.css` or `features/<x>.css` rule.
2. If adding a new feature file, add its raw-URL import to `vscode-settings.json`.
3. Commit and push to `main` (users' editors refetch from `main`).
4. Reload the VS Code window to see the change (the extension is set to
   `reloadWithoutPrompting`).
