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
npx skills add robinbg/algorithm-contest-skills
```

也可以按目录安装单个 skill：

```bash
npx skills add robinbg/algorithm-contest-skills/algorithm-contest-problemsetter
npx skills add robinbg/algorithm-contest-skills/algorithm-contest-tester
```

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
