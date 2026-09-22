# Claude Code Plugin

The official SolWear plugin for [Claude Code](https://claude.com/claude-code)
lets you build SolWear apps by asking Claude, and gives SolWear OS contributors
the Architect and Reviewer workflow commands. It wraps the published
`@solwear/cli`, so it drives the whole developer loop — scaffold, build, run in
the host emulator, package, sign and publish — without leaving your editor.

## Install

In Claude Code, add the marketplace and install the plugin:

```
/plugin marketplace add SolWear/SolWear-Claude-Plugin
/plugin install solwear
```

The marketplace lives at
[SolWear/SolWear-Claude-Plugin](https://github.com/SolWear/SolWear-Claude-Plugin).

## Requirements

- [Claude Code](https://claude.com/claude-code).
- The SolWear CLI on your PATH:

  ```
  npm install --global @solwear/cli
  ```

  Installing the CLI also installs the host emulator, so `solwear run` works
  without a monorepo checkout. See [Installing the SDK](installing-the-sdk.md).

## What it provides

### Skill: `build-a-solwear-app`

Claude loads this automatically when you ask it to create, build, run, package,
sign or publish a SolWear app. It follows the CLI loop end to end:

- `solwear new` — scaffold an app, watchface or signer.
- `solwear build` — bundle the app against `@solwear/sdk`.
- `solwear run --profile <profile>` — open the app in the host emulator (use
  `--no-window` on a headless machine). See [Using the Emulator](using-the-emulator.md).
- `solwear package`, `keygen`, `sign`, `verify` — produce and sign a `.swa`.
  See [Package Format and Signing](package-format-and-signing.md).
- `solwear publish` — submit to the store. See
  [Publishing to the Store](publishing-to-the-store.md).

### Commands

- `/solwear:task` — act as the **Architect**: analyse a task and produce a
  scoped unit of work.
- `/solwear:review` — act as the **Reviewer**: review a diff for contract
  conformance, security, correctness and clarity.

The commands assume the SolWear OS monorepo; the skill only needs the CLI.

## Try it

Once installed, just ask:

> Build me a SolWear watchface that shows the time and battery, then run it on the
> round 480 profile.

Claude scaffolds the project, writes the app against the SDK, and opens it in the
host emulator for you.
