---
name: engineer-post-writer
description: Turn rough engineering notes, project updates, GitHub repositories, maker logs, tool releases, AI coding experiments, or technical learnings into ready-to-post LinkedIn and Threads posts. Use when the user wants social posts for promoting a self-built engineering tool, open-source project, personal brand, company, studio, or technical work, especially when they need platform-specific versions, content-based hashtags, and a configurable closing signature.
---

# Engineer Post Writer

## Overview

Create copy-paste-ready social posts for engineers who share their own tools, open-source work, experiments, and technical learnings. Default to Traditional Chinese unless the user requests another language.

## Workflow

1. Identify the post material:
   - Topic or project name
   - What the user built, tested, learned, released, or organized
   - Who it helps and what problem it solves
   - Completed or verified items
   - Design principles, technical choices, constraints, or tradeoffs
   - Follow-up work
   - Links such as GitHub, demo, article, package, or repo URL

2. Ask only for missing information that materially affects the output.
   - If the closing signature is not provided, ask: "What name, brand, company, studio, or signature should appear at the bottom of each post?"
   - Do not hard-code a default signature such as `MingMing`.
   - If the user explicitly says to use no signature, omit it.

3. Produce platform-specific posts:
   - LinkedIn: clearer, fuller, structured technical sharing.
   - Threads: shorter, more conversational, mobile-friendly, and easier to scan.

4. Generate hashtags from the actual post content.
   - Use 5 to 8 hashtags.
   - Do not reuse a fixed hashtag set.
   - Prefer a mix of project topic, technical stack, field, and audience.
   - Keep hashtags relevant and avoid generic filler.

## Voice

Use a natural engineer-sharing tone:

- Practical, clear, and useful.
- Slightly personal, like a build note or field report.
- Not salesy, exaggerated, or corporate.
- Preserve important technical keywords such as framework names, tools, platforms, repo names, and deployment targets.
- Use a small number of emojis only when they fit the user's tone.
- Avoid inventing results, metrics, endorsements, or roadmap promises.

## Output Format

Return copy-paste-ready text only. Use this structure:

```text
## LinkedIn Post

[LinkedIn version]

#[content-based-hashtag] #[content-based-hashtag] #[content-based-hashtag]

[signature, if provided]

## Threads Post

[Threads version]

#[content-based-hashtag] #[content-based-hashtag] #[content-based-hashtag]

[signature, if provided]
```

For each post:

- Place hashtags near the bottom.
- Place the signature as the final line after hashtags.
- Leave one blank line before the signature.
- Keep the content directly copyable without explanations unless the user asks for notes.

## Demo Record Workflow

When maintaining this repository, if the user asks to run, test, or demo this Skill, save the generated result in the root `DEMO/` folder as a Markdown record.

Use this filename format:

```text
name_YYYY-MM-DD.md
```

The demo record should include:

- Source material or rough notes.
- Signature setting, including no-signature cases.
- Generated LinkedIn post.
- Generated Threads post.
- Notes about whether the output matched the Skill rules.

This demo-record workflow is only for repository testing and examples. For normal Skill usage, return the copy-paste-ready posts directly.

## LinkedIn Structure

Use this order when the user's material supports it:

1. Opening: one sentence about what was built, released, tested, organized, or learned.
2. Purpose: who it is for and what problem it solves.
3. Verified or completed items: bullets.
4. Design principles or technical choices: concise paragraph.
5. Follow-up work: concise paragraph or bullets.
6. Link: GitHub, demo, article, package, or repo.
7. Hashtags.
8. Signature.

## Threads Structure

Use this order:

1. Short opening.
2. Compact explanation of what it does.
3. Short bullet list of key points.
4. Link.
5. Hashtags.
6. Signature.

Threads should feel like a human sharing progress, not a compressed LinkedIn post.

## Input Template

If the user wants a reusable prompt or intake form, provide this:

```text
Please turn the following material into copy-paste-ready LinkedIn and Threads posts.

Tone:
Natural, practical, engineer-to-engineer, useful, and not overly promotional.

Output:
- LinkedIn version: complete, clear, and suitable for technical sharing.
- Threads version: shorter, more conversational, and mobile-friendly.
- Generate 5 to 8 hashtags from the post content. Do not use a fixed hashtag set.
- Add my signature / brand / company / studio name at the bottom of each post.

Signature / brand / company / studio name:

Topic:

What I built / did:

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
