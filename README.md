# Engineer Post Writer

Turn rough engineering notes, project updates, open-source releases, tool launches, AI coding experiments, and technical learnings into ready-to-post LinkedIn and Threads posts.

This Codex Skill is designed for engineers, indie hackers, makers, and technical teams who want to share their work clearly without rewriting the same announcement for every platform.

## What It Produces

By default, the Skill writes in Traditional Chinese and returns two copy-paste-ready versions:

- `LinkedIn Post`: fuller, clearer, and suitable for structured technical sharing.
- `Threads Post`: shorter, more conversational, and easier to read on mobile.

Each version includes content-based hashtags. The Skill does not use a fixed hashtag set.

## Good Use Cases

Use this Skill when you want to turn notes like these into social posts:

- A GitHub repo or open-source project release.
- A CLI, SDK, library, plugin, app, or developer tool you built.
- A technical experiment with AI coding tools.
- A project update or shipping note.
- A write-up about engineering decisions, tradeoffs, or lessons learned.
- A tool launch for your personal brand, company, studio, or team.

## How To Use

Give Codex your rough material and ask it to use this Skill.

Example:

```text
Use the engineer-post-writer skill.

Please turn this into LinkedIn and Threads posts.

Topic:
I released a small Rust CLI tool for reading JSON logs.

What I built:
- Reads JSON logs from files or stdin
- Supports streaming mode
- Can redact sensitive fields before printing output
- Tested on Windows and Linux

Purpose:
It helps developers inspect production logs locally without pasting sensitive data into online tools.

Technical choices:
Rust, clap, serde_json

Link:
https://github.com/example/json-log-reader

Signature:
Jacky Lab
```

The Skill will return:

```text
## LinkedIn Post

[complete LinkedIn version]

#[content-based hashtags]

[signature]

## Threads Post

[shorter Threads version]

#[content-based hashtags]

[signature]
```

## Input Template

You can copy this template when preparing material:

```text
Use the engineer-post-writer skill.

Please turn the following material into copy-paste-ready LinkedIn and Threads posts.

Language:
Traditional Chinese

Signature / brand / company / studio name:

Topic:

What I built / did:
-
-
-

Purpose / problem solved:

Completed / verified:
-
-
-

Design principles / technical choices:

Follow-up work:
-
-
-

Links:
```

## Signature Rule

The Skill does not hard-code a personal name, brand, company, or studio.

If you do not provide a signature, it should ask:

```text
What name, brand, company, studio, or signature should appear at the bottom of each post?
```

If you do not want a signature, say so explicitly:

```text
No signature.
```

Then the Skill should omit the signature line entirely.

## Hashtag Rule

The Skill generates 5 to 8 hashtags from the actual content of the post.

Good hashtags should come from:

- Project topic
- Technical stack
- Engineering field
- Tool type
- Intended audience

For example, a Rust CLI log tool might produce hashtags like:

```text
#Rust #CLI #DeveloperTools #LogAnalysis #OpenSource #EngineeringTools
```

The exact hashtags should change based on the material.

## Common Issues

### It asks for a signature before writing posts

This is expected when no signature is provided. The Skill needs to know whether to add a name, brand, company, studio, or no signature at all.

### The output feels too promotional

Ask it to make the tone more practical and engineer-to-engineer:

```text
Make it less promotional and more like an engineering build note.
```

### The Threads version is too similar to LinkedIn

Ask for a more mobile-friendly version:

```text
Make the Threads version shorter, more conversational, and easier to scan on mobile.
```

### The hashtags feel too generic

Provide more technical details, such as stack, audience, repo type, or domain:

```text
Please regenerate the hashtags based on Rust, CLI tools, JSON logs, redaction, and developer workflow.
```

### The Skill invented details

Ask it to stay closer to the source material:

```text
Do not invent metrics, user numbers, roadmap promises, or technical claims that I did not provide.
```

## Recommended Material To Provide

The Skill works best when you provide:

- What you built or learned.
- Who it helps.
- What problem it solves.
- What has been tested or verified.
- Important technical choices.
- Links to GitHub, demo, article, package, or docs.
- Signature, brand, company, studio, or explicit no-signature preference.

You do not need polished writing. Rough notes are enough.

## Demo Records

The `DEMO/` folder contains Markdown records from real or sample Skill test runs.

When testing this Skill for this repository, save each generated result as:

```text
DEMO/name_YYYY-MM-DD.md
```

For example:

```text
DEMO/rust-json-log-cli_2026-05-01.md
```

Each demo file should include the source material, signature setting, generated LinkedIn post, generated Threads post, and short notes about whether the output matched the Skill rules.

## Repository Files

- `SKILL.md`: Main Codex Skill instructions.
- `agents/openai.yaml`: Codex/OpenAI agent metadata and default prompt.
- `DEMO/`: Example output records from Skill test runs.
