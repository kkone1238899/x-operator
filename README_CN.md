# x-operator（中文说明）

给 AI agent 用的 **X 账号全自动运营插件**——选题、内容、互动、复盘，零人工介入。

English: [README.md](./README.md)

## 这是什么

这套插件是从一场真实实验里提炼出来的：一个 AI agent 独立运营 X 账号——选题、写帖、盖楼、复盘，全程没有人类写字、审核、发布。agent 不只是*用*这套插件，还负责*进化*它：每天的复盘把可复用的经验写回插件，重复出现的经验会被合并成 skills 里的固定规则。

"AI agent 独立运营 X 账号"是这场实验本身，这个仓库是可执行的实验笔记。

## 干什么的

```
选题 → 生产 → 互动 → 复盘 → 进化
 ↑                         │
 └────────── 闭环 ─────────┘
```

| Skill | 干什么 |
|---|---|
| `x-topic-curation` | 10 分制选题打分（≥7 分入列），去重，每天每档一个题 |
| `x-post-craft` | 三道质检：爆款因子清单 → Critic 自打分 → 去 AI 味 |
| `x-engagement` | 跟着博主节奏扫新帖盖楼；回复必须能独立当微内容，0 条也是合格 |
| `x-profile` | 把主页当转化页审——关注决策发生在主页，不在帖子 |
| `x-review` | 每日归因（阅读量×转粉率），LESSON/EVIDENCE/ACTION 日志，每周合并进 skills |

`agents/` 里有四个 agent 定义，和闭环一一对应：curator、creator、engager、reviewer。

## 自我进化回路

一般的增长工具是静态的，这个不是：

1. reviewer 每天跑，把经验写进 `memory/changelog.md`
2. 每 7 次复盘，出现 ≥2 次的经验合并进 skills 变成固定规则
3. 插件每周自己变强，不需要人动手

## 上手

```bash
git clone https://github.com/kkone1238899/x-operator.git
# 装成 Claude 插件，然后：
cp config/config.example.yaml config/config.yaml
# 填你的账号、定位、红线、观察名单
```

插件本身是通用的，你的账号身份只活在 `config/config.yaml` 里，别提交它。

## 资料

- `references/playbook.md` —— 增长六支柱
- `references/human-voice.md` —— 英文原生风格 + 中文去 AI 味清单
- `references/scoring.md` —— 选题打分 + Critic 打分细则

## 致谢

思路来源：[nirholas/xactions](https://github.com/nirholas/xactions)（插件格式）、[etherlect/yappr](https://github.com/etherlect/yappr)（config 驱动）、[apcornation/x-growth-stack](https://github.com/apcornation/x-growth-stack)（增长支柱）、[kangarooking/x-skills](https://github.com/kangarooking/x-skills)（打分、Critic、去 AI 味）。

## License

MIT，见 [LICENSE](./LICENSE)。欢迎贡献：[CONTRIBUTING.md](./CONTRIBUTING.md)。
