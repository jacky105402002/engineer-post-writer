# Engineer Post Writer

Turn rough engineering notes, project updates, open-source releases, tool launches, AI coding experiments, and technical learnings into ready-to-post LinkedIn and Threads posts.

> 中文說明：這是一個 Codex Skill，可以把工程師的粗略筆記、專案更新、開源工具發布、AI coding 實驗或技術心得，整理成可以直接複製發布的 LinkedIn 與 Threads 貼文。

This Codex Skill is designed for engineers, indie hackers, makers, and technical teams who want to share their work clearly without rewriting the same announcement for every platform.

> 適合對象：工程師、獨立開發者、開源維護者、技術團隊，或任何想把自己做的工具/專案講清楚的人。

## What It Produces

By default, the Skill writes in Traditional Chinese and returns two copy-paste-ready versions:

- `LinkedIn Post`: fuller, clearer, and suitable for structured technical sharing.
- `Threads Post`: shorter, more conversational, and easier to read on mobile.

中文補充：

- `LinkedIn Post` 會比較完整，適合放技術脈絡、完成項目、設計取捨與連結。
- `Threads Post` 會比較短、比較口語，適合手機閱讀與快速分享進度。

Each version includes content-based hashtags. The Skill does not use a fixed hashtag set.

Hashtags 會依照貼文內容產生，不會固定塞同一組標籤。

## Good Use Cases

Use this Skill when you want to turn notes like these into social posts:

- A GitHub repo or open-source project release.
- A CLI, SDK, library, plugin, app, or developer tool you built.
- A technical experiment with AI coding tools.
- A project update or shipping note.
- A write-up about engineering decisions, tradeoffs, or lessons learned.
- A tool launch for your personal brand, company, studio, or team.

中文情境範例：

- 你剛整理好一個 GitHub repo，想發 LinkedIn/Threads。
- 你做了一個 CLI、SDK、plugin、app、內部工具或開源小工具。
- 你想分享一次 AI coding、Codex、Claude Code、Cursor 或其他開發流程實驗。
- 你想把「今天做了什麼」整理成比較像工程師分享，而不是廣告文。
- 你想同時產出偏正式的 LinkedIn 版本與偏口語的 Threads 版本。

## How To Use

Give Codex your rough material and ask it to use this Skill.

使用方式很簡單：把你的粗略素材貼給 Codex，並要求使用 `engineer-post-writer` skill。

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

你不需要先把內容寫得很漂亮。越像工程師筆記也沒關係，Skill 會幫你整理成可發布版本。

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

輸出會盡量維持「可直接複製貼上」，不額外加一堆解釋。

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

中文欄位說明：

- `Signature / brand / company / studio name`：貼文底部署名，可以是你的名字、品牌、公司、工作室，也可以明確寫 `No signature`。
- `Topic`：這次想分享的主題或專案名稱。
- `What I built / did`：你做了什麼，可以直接列 bullet。
- `Purpose / problem solved`：這個工具或心得解決什麼問題、幫助誰。
- `Completed / verified`：已完成或測試過的項目。
- `Design principles / technical choices`：技術選型、設計原則、限制或取捨。
- `Follow-up work`：接下來想補的功能或後續計畫。
- `Links`：GitHub、demo、文章、套件頁、文件等。

## Signature Rule

The Skill does not hard-code a personal name, brand, company, or studio.

中文說明：這個 Skill 不會寫死任何人的名字，例如不會自動加上特定作者名。因為這個 repo 是給其他工程師也能拿去用自己的品牌、公司或工作室。

If you do not provide a signature, it should ask:

```text
What name, brand, company, studio, or signature should appear at the bottom of each post?
```

If you do not want a signature, say so explicitly:

```text
No signature.
```

Then the Skill should omit the signature line entirely.

如果你不想要署名，請直接寫 `No signature.`，Skill 就應該完全省略署名行。

## Hashtag Rule

The Skill generates 5 to 8 hashtags from the actual content of the post.

中文說明：hashtags 會根據內容產生 5 到 8 個，不使用固定組合。

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

如果素材是 AI coding 實驗，hashtags 可能會偏向 `#AICoding`、`#DeveloperWorkflow`、`#PromptEngineering`。如果素材是 Rust CLI，hashtags 就應該偏向 `#Rust`、`#CLI`、`#DeveloperTools`。

## Common Issues

### It asks for a signature before writing posts

This is expected when no signature is provided. The Skill needs to know whether to add a name, brand, company, studio, or no signature at all.

中文：這是正常行為。因為 Skill 不應該猜你的署名，也不應該硬塞預設作者名。

### The output feels too promotional

Ask it to make the tone more practical and engineer-to-engineer:

```text
Make it less promotional and more like an engineering build note.
```

中文：如果你覺得太像廣告，可以要求它改成比較像「工程師開發紀錄」。

### The Threads version is too similar to LinkedIn

Ask for a more mobile-friendly version:

```text
Make the Threads version shorter, more conversational, and easier to scan on mobile.
```

中文：Threads 版本應該更短、更口語，不應只是 LinkedIn 版本壓縮。

### The hashtags feel too generic

Provide more technical details, such as stack, audience, repo type, or domain:

```text
Please regenerate the hashtags based on Rust, CLI tools, JSON logs, redaction, and developer workflow.
```

中文：如果 hashtags 太泛，可以補充技術棧、工具類型、目標使用者或專案領域。

### The Skill invented details

Ask it to stay closer to the source material:

```text
Do not invent metrics, user numbers, roadmap promises, or technical claims that I did not provide.
```

中文：如果輸出自行補了你沒有提供的數據、使用者數、效果承諾或 roadmap，要要求它回到原始素材。

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

中文提醒：不用把素材整理成文章。只要提供工程師筆記、完成項目、技術選型、連結和署名偏好，就足夠開始。

## Demo Records

The `DEMO/` folder contains Markdown records from real or sample Skill test runs.

中文說明：`DEMO/` 用來放實際測試產出的紀錄，方便 GitHub 上的其他人參考這個 Skill 的效果。

When testing this Skill for this repository, save each generated result as:

```text
DEMO/name_YYYY-MM-DD.md
```

For example:

```text
DEMO/rust-json-log-cli_2026-05-01.md
```

Each demo file should include the source material, signature setting, generated LinkedIn post, generated Threads post, and short notes about whether the output matched the Skill rules.

之後如果在這個 repo 裡測試或 demo 這個 Skill，請在 `DEMO/` 建立 `name_YYYY-MM-DD.md`，把輸入素材、署名設定、產出的 LinkedIn/Threads 貼文與測試備註都記錄下來。

## Repository Files

- `SKILL.md`: Main Codex Skill instructions.
- `agents/openai.yaml`: Codex/OpenAI agent metadata and default prompt.
- `DEMO/`: Example output records from Skill test runs.

中文檔案說明：

- `SKILL.md`：Skill 的主要規則，Codex 會依照這裡的工作流程產文。
- `agents/openai.yaml`：OpenAI/Codex agent 顯示名稱與預設 prompt。
- `DEMO/`：測試輸出範例，之後可以放到 GitHub 給其他人參考。
