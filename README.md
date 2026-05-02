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

### Recommended: use `npx skills`

安装整个仓库中的两个 skills：

```bash
npx skills add robinbg/algorithm-contest-Skills
```

也可以按目录安装单个 skill：

```bash
npx skills add robinbg/algorithm-contest-Skills/algorithm-contest-problemsetter
npx skills add robinbg/algorithm-contest-Skills/algorithm-contest-tester
```

常用选项：

```bash
# 查看仓库里有哪些 skills
npx skills add robinbg/algorithm-contest-Skills --list

# 只安装出题人
npx skills add robinbg/algorithm-contest-Skills --skill algorithm-contest-problemsetter

# 只安装验题人
npx skills add robinbg/algorithm-contest-Skills --skill algorithm-contest-tester

# 安装到全局，而不是当前项目
npx skills add robinbg/algorithm-contest-Skills -g

# 指定目标 agent，例如 Claude Code 或 Codex
npx skills add robinbg/algorithm-contest-Skills -a claude-code
npx skills add robinbg/algorithm-contest-Skills -a codex
```

### Manual install paths

这些 skills 采用通用的 `SKILL.md` 结构：YAML frontmatter + Markdown 指令。可在以下工具中使用：

| Tool | Manual location / usage |
|---|---|
| OpenAI Codex / Codex CLI | 推荐用 `npx skills add`。手动安装时放到 `$CODEX_HOME/skills/<skill-name>/SKILL.md`，通常是 `~/.codex/skills/<skill-name>/SKILL.md`。 |
| Claude Code | 个人 skills 放到 `~/.claude/skills/<skill-name>/SKILL.md`；项目 skills 放到 `.claude/skills/<skill-name>/SKILL.md`。 |
| Claude Desktop / Claude.ai Skills | 上传单个 `SKILL.md`，或上传包含 `SKILL.md` 的 skill 目录 ZIP。 |
| OpenClaw | 放到 `~/.openclaw/skills/<skill-name>/SKILL.md`、`~/.agents/skills/<skill-name>/SKILL.md`、`<workspace>/.agents/skills/<skill-name>/SKILL.md` 或 `<workspace>/skills/<skill-name>/SKILL.md`。 |
| Hermes Agent | 放到 `~/.hermes/skills/<skill-name>/SKILL.md`；也可放到项目 `skills/<skill-name>/SKILL.md`，取决于 Hermes 配置。 |
| Cursor / Windsurf | 可通过 `npx skills add` 尝试安装；若当前版本未自动识别，把 `SKILL.md` 内容作为 rules、context 或 agent instructions 引入。 |
| Cline / Roo Code / Continue | 把对应 `SKILL.md` 内容作为自定义指令或项目规则引用；不保证自动触发。 |
| Gemini CLI / Aider / other coding agents | 直接引用对应 `SKILL.md`，让 agent 按其中工作流执行。 |

如果工具支持“读取目录中的 `SKILL.md` 并按 `description` 自动触发”，可以直接作为 skill 使用；否则把 `SKILL.md` 当作专用 system prompt / project rule 使用。

### Verify installation

安装后新开一个 agent session，尝试：

```text
用算法竞赛出题人设计一道 CSP 提高难度的图论题，要求有部分分和数据范围。
```

或：

```text
用算法竞赛验题人检查这道题，重点找题面歧义、错误贪心反例和 checker 风险。
```

如果 agent 能引用出题人/验题人的工作流、心智模型和检查清单，说明 skill 已被加载。

## Usage

推荐流程：

1. 先用 `algorithm-contest-problemsetter` 产出题面、题解、标程思路和数据设计。
2. 再用 `algorithm-contest-tester` 攻击题目，输出风险报告。
3. 回到出题人修订题目。
4. 重复直到验题结论达到可发布状态。

常用提示词：

```text
用算法竞赛出题人设计一道 CSP 提高难度的图论题，要求有部分分、题解思路和数据生成建议。
```

```text
用算法竞赛验题人检查下面这道题，重点找题面歧义、错误贪心反例、弱数据和 checker 风险。
```

## Attribution

本仓库中的 skill 由 [女娲 · Skill造人术](https://github.com/alchaincyf/nuwa-skill) 蒸馏生成。

创建者：[花叔](https://x.com/AlchainHust)

## License

MIT — use it, modify it, build with it.

MIT License © [Huashu](https://github.com/alchaincyf)
