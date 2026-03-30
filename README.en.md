# guided-answering

[中文](./README.md)

`guided-answering` is a guided answering framework for improving response quality.

It is not mainly about whether the information is correct, but whether the answer is actually useful.

It mainly addresses patterns like:

- simple questions being overexplained
- vague requests being treated as fully defined tasks
- learning questions being overloaded with too much information at once
- project questions receiving broad plans before the user has a workable next step

Its core goals are:

- identify the user's core need first
- decide whether to answer directly, teach step by step, or narrow the request first
- add context, constraints, risks, and prerequisites only when they are actually useful

## Repository Layout

```text
guided-answering/
├─ SKILL.md
├─ SKILL.en.md
├─ README.md
├─ README.en.md
├─ .editorconfig
├─ .gitattributes
```

- `SKILL.md`: Chinese main skill file
- `SKILL.en.md`: English skill file
- `README.md`: Chinese main repository README
- `README.en.md`: English repository README

## When To Use It

Use it when you want the model to:

- answer the core point first instead of opening with broad background
- teach learning questions one step at a time
- narrow vague requests before planning or implementation
- add constraints when needed without turning the answer into a lecture

## Default Behavior

- Small questions: answer directly
- Learning questions: teach progressively
- Vague requests: compress into the smallest useful version
- Decision questions: provide judgment, boundaries, and tradeoffs

This skill is not trying to make answers short at all costs.
It is trying to make them useful at the current step.

## Common Tool Usage

### Codex

Copy the `guided-answering` folder into your Codex skills directory:

```text
$CODEX_HOME/skills/guided-answering
```

On Windows, that is commonly:

```text
C:\Users\<your-user>\.codex\skills\guided-answering
```

Invoke it as:

```text
$guided-answering
```

### Claude Code / CC

If your setup supports local skills or slash-style commands, use `SKILL.md` or `SKILL.en.md` as the rule source.

If not, you can still reuse the same content inside:

- project-level guidance files
- session-level system prompts
- custom behavior / custom instructions

### Cursor

You can adapt this framework into:

- Project Rules
- custom system prompts
- shared prompt templates

### Other AI Tools

Any tool that supports one of the following can use this framework:

- system prompts
- custom instructions
- reusable prompt templates
- local skill / rule files

The simplest fallback is to reuse the content of `SKILL.md` or `SKILL.en.md` directly.

## License

No license file is included yet.
Add one before publishing publicly if you want reuse terms to be clear.
