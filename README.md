# Algorithm Contest Skills

两个面向算法竞赛工作流的 Codex Skills：

- `algorithm-contest-problemsetter`：算法竞赛出题人。用于 CSP、NOI、ICPC/CCPC、校赛、训练赛、LeetCode 竞赛等场景的造题、改题、题面打磨、数据范围设计、部分分设计、题解和标程规划。
- `algorithm-contest-tester`：算法竞赛验题人。用于验题、找漏洞、构造反例、对拍、审查标程、题解、数据、checker、validator 和 special judge。

核心分工：

| Skill | 关注点 | 产物 |
|---|---|---|
| `algorithm-contest-problemsetter` | 创造算法观察和区分度 | 题面、题解、标程规划、数据设计、部分分 |
| `algorithm-contest-tester` | 攻击漏洞和不一致 | 反例、hack、对拍方案、风险报告、checker/validator 审查 |

## Installation

安装整个仓库中的两个 skills：

```bash
npx skills add robinbg/algorithm-contest-Skills
```

也可以按目录安装单个 skill：

```bash
npx skills add robinbg/algorithm-contest-Skills/algorithm-contest-problemsetter
npx skills add robinbg/algorithm-contest-Skills/algorithm-contest-tester
```

## Compatible Tools

这些 skills 采用通用的 `SKILL.md` 结构：YAML frontmatter + Markdown 指令。可在以下工具中使用：

| Tool | Usage |
|---|---|
| OpenAI Codex / Codex CLI | 推荐。可通过 `npx skills add robinbg/algorithm-contest-Skills` 安装，触发词由 `SKILL.md` 的 `description` 控制。 |
| OpenClaw | 可直接使用。OpenClaw 支持 AgentSkills-compatible skill folders，可放在 `~/.openclaw/skills`、`~/.agents/skills`、`<workspace>/.agents/skills` 或 `<workspace>/skills`。 |
| Hermes Agent | 可直接使用。Hermes skills 是包含 `SKILL.md` 的目录，可放在 `~/.hermes/skills/<skill-name>/SKILL.md`。 |
| Claude Code | 可用。将对应 skill 目录放入 Claude Code 的 skills 目录，或在项目中引用 `SKILL.md`。 |
| Claude Desktop / Claude.ai Skills | 可用。按 Anthropic Skills 的方式导入包含 `SKILL.md` 的目录。 |
| Cursor / Windsurf | 可手动使用。把对应 `SKILL.md` 作为 rules、context 或 agent instructions 引入；不保证自动触发。 |
| Cline / Roo Code / Continue | 可手动使用。把 `SKILL.md` 内容作为自定义指令或项目规则引用；不保证自动触发。 |
| Gemini CLI / Aider / other coding agents | 可手动使用。直接引用对应 `SKILL.md`，让 agent 按其中工作流执行。 |

如果工具支持“读取目录中的 `SKILL.md` 并按 `description` 自动触发”，可以直接作为 skill 使用；否则把 `SKILL.md` 当作专用 system prompt / project rule 使用。

## Usage

示例：

```text
用算法竞赛出题人设计一道 CSP 提高难度的图论题，要求有部分分和数据范围。
```

```text
用算法竞赛验题人检查这道题，重点找题面歧义、错误贪心反例和 checker 风险。
```

推荐流程：

1. 先用 `algorithm-contest-problemsetter` 产出题面、题解、标程思路和数据设计。
2. 再用 `algorithm-contest-tester` 攻击题目，输出风险报告。
3. 回到出题人修订题目。
4. 重复直到验题结论达到可发布状态。

## Attribution

本仓库中的 skill 由 [女娲 · Skill造人术](https://github.com/alchaincyf/nuwa-skill) 蒸馏生成。

创建者：[花叔](https://x.com/AlchainHust)

## License

MIT — use it, modify it, build with it.

MIT License © [Huashu](https://github.com/alchaincyf)
