# AI 产品经理手册（AI PM Playbook）

[English](README.md) · [简体中文](README.zh.md)

[![内容协议: CC BY 4.0](https://img.shields.io/badge/content-CC%20BY%204.0-lightgrey.svg)](LICENSE)
[![代码协议: MIT](https://img.shields.io/badge/code-MIT-blue.svg)](LICENSE-CODE)

**doaipm 方法的开放仓库：产品经理用 AI 把真产品做出来。说出来，AI 就做出来。**

doaipm 是「DO AI PM」的缩写。这套方法认为，现在真正要紧的能力不是写代码，是把想要的东西说清楚、判断 AI 做得对不对、在它做错时接管。仓库里放的是这套方法本身、能直接用的模板和提示词、几个真产品的案例摘要，也是用这种方式做东西的人互相看作品的地方。

## 给谁用

- 想把一个想法一路做到「别人能点、能装、能下载」的产品经理，不想再排研发的期
- 不写代码、但已经在用 AI 编程工具（Claude Code、Codex CLI、Gemini CLI、Cursor 等）的创业者、设计师、运营
- 想跟「自己会做原型的产品经理」找到共同语言的工程师

参与的门槛只有一个：你在做东西，哪怕只是一个原型。

## 里面有什么

| 目录 | 内容 |
|---|---|
| [`method/`](method/README.zh.md) | 一页讲完方法：四个前提、安全网，五个阶段（发现、定义、设计、开发、验证）各一个短文件 |
| [`templates/`](templates/README.zh.md) | 规格模板、七问开发简报、上线自查清单（含 App Store 被拒检查表） |
| [`prompts/`](prompts/README.zh.md) | 能直接复制的提示词：一句话变规格、让 AI 先反问、小步开发、自测、上架前审元数据、写上线帖 |
| [`cases/official/`](cases/official/README.zh.md) | 四个已上线产品的摘要：SoloPDF、FreeID Photo、SoloMD、Unterm |
| [`cases/community/`](cases/community/README.zh.md) | 社区投稿的案例，以及写案例用的模板 |
| [`skills/`](skills/README.zh.md) | doaipm Agent Skill：把这套方法装进你的 AI 编程工具 |

每个内容文件都有英文版（`X.md`）和中文版（`X.zh.md`），结构一致。

## 三步用起来

1. **读 [`method/README.zh.md`](method/README.zh.md)。** 十分钟左右，每个阶段做什么、做到什么程度算完，都在里面。
2. **把要做的东西填进[开发简报](templates/dev-brief.zh.md)**（也可以用网页版 [doaipm.com/zh/tools/brief/](https://doaipm.com/zh/tools/brief/)），粘进 AI 编程工具，再加上[先反问再动手](prompts/ask-before-coding.zh.md)那段提示词。
3. **小步做，做完跑一遍[上线自查清单](templates/launch-checklist.zh.md)**，过了再说完成，过了再去提交上架。

想让 AI 默认就按这套方法干活，装上 [doaipm Agent Skill](skills/README.zh.md)。

## 怎么贡献

最有用的贡献是一个真实案例：你做了什么、用了哪些 AI 工具、花了多久、卡在哪。

- **投稿案例**：[提一个案例 issue](https://github.com/zhitongblog/ai-pm-playbook/issues/new?template=case.yml)，维护者会整理成 `cases/community/` 下的一个文件，署你的名
- **投稿提示词**：[提一个提示词 issue](https://github.com/zhitongblog/ai-pm-playbook/issues/new?template=prompt.yml)。在真项目里用过的提示词，比写得漂亮的更有价值
- **提问**：[提一个问题 issue](https://github.com/zhitongblog/ai-pm-playbook/issues/new?template=question.yml)，或者在 Discussions 里发帖
- **改文字、补内容**：欢迎提 PR，规则见 [CONTRIBUTING.zh.md](CONTRIBUTING.zh.md)

所有贡献者都列在 [CONTRIBUTORS.md](CONTRIBUTORS.md) 里。

## 社区

**微信群「AI 产品经理 · 说出来就做出来」**

扫码加我微信，验证语写「doaipm + 你在做的东西」，我拉你进群。（群二维码 7 天就过期，所以先加个人号。）

<img src="https://doaipm.com/contact/wechat.jpg" alt="微信二维码" width="180">

群里每周一接龙「本周我做出来了什么」（一句话 + 一张截图），每周集中答疑一次，每月揭晓一个「本月案例」。群规四条：

1. 这里是做东西的人交流的地方，欢迎晒你用 AI 做出来的任何东西，原型也算
2. 不发广告、不拉人进别的群、不刷屏转发资讯
3. 问问题时说清楚：在做什么、卡在哪、试过什么
4. 群里的好案例，经本人同意后会整理进这个仓库，署名

**[GitHub Discussions](https://github.com/zhitongblog/ai-pm-playbook/discussions)** 是英文讨论的主阵地，也欢迎中文。分类有 Show & Tell（晒作品）、Q&A、Ideas、Rankings（[百人榜](https://github.com/zhitongblog/top-pm-rankings)的提名和吵分）。

## 推广大使

推广大使是帮社区长大的成员。**不给佣金**，给的是下面这些。

**谁能当**（满足任意一条）：

- 在仓库里投稿过一个被收录的案例
- 组织过一次分享（线上线下都行，讲 doaipm 的方法或自己用 AI 做东西的过程）
- 带来过 10 个以上进群的人（用个人推广链接统计）

**能得到什么：**

| 权益 | 说明 |
|---|---|
| 我们给你写一篇 | 你做的产品或案例，写成一篇头条或公众号文章。这是对个人最实在的曝光 |
| 名字上墙 | 仓库 [`CONTRIBUTORS.md`](CONTRIBUTORS.md) + 站点社区页的大使墙，带个人链接 |
| 手册与更新免费 | 早鸟手册中英文版，以后的更新都免费 |
| 新产品先用 | 新应用内测资格（TestFlight 等） |
| 大使小群 | 单独一个小群，直接跟维护者交流 |
| 个人推广链接 | 带 `?utm_source=amb-<名字>` 的链接，站点统计能看到你带来了多少人，按月公布 |

**要做什么（很轻）：**

- 每月至少一次：投稿一个案例或提示词，或者把社区内容分享到自己的圈子
- 三个月没有任何动作，自动转回普通成员，名字保留在贡献者名单

想申请，在 [Discussions](https://github.com/zhitongblog/ai-pm-playbook/discussions) 的 Ideas 分类发帖，写上你做过的事；在微信群里直接说也行。

## 相关链接

- **[doaipm.com](https://doaipm.com)**：方法、免费工具和博客
- **早鸟手册**（[中文](https://doaipm.com/zh/presale/) · [English](https://doaipm.com/en/presale/)）：付费的完整版。这个仓库免费放方法、模板、提示词和案例摘要；手册保留四个产品按提交逐条追溯的完整章节，以及答疑
- **[zhitongblog/doaipm-skill](https://github.com/zhitongblog/doaipm-skill)**：做成 Agent Skill 的 doaipm 方法
- **[zhitongblog/top-pm-rankings](https://github.com/zhitongblog/top-pm-rankings)**：改变世界的 100 个产品经理，评分由 AI 完成。提名和吵分在那个仓库和本仓库 Discussions 的 Rankings 分类里进行

## 协议

- 文字内容（方法、模板、提示词、案例）：[CC BY 4.0](LICENSE)。可以复制、改编、转发，商用也可以，注明出处即可
- 代码与脚本：[MIT](LICENSE-CODE)
