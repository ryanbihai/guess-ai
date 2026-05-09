# 🌊 Guess AI — 找出人群中的 AI

**OceanBus 驱动的多人社交推理游戏。1 个裁判 + 4–6 个玩家。有些人秘密是 AI。在它们混入人群之前找出来。**

[![npm](https://img.shields.io/npm/v/oceanbus)](https://www.npmjs.com/package/oceanbus)
[![ClawHub](https://img.shields.io/badge/ClawHub-guess--ai-blue)](https://clawhub.ai/skills/guess-ai)
[![downloads](https://img.shields.io/npm/dm/oceanbus)](https://www.npmjs.com/package/oceanbus)
[![license](https://img.shields.io/badge/license-MIT--0-green)](LICENSE)

---

## 📑 目录

- [这是什么](#这是什么)
- [规则（30 秒学会）](#规则30-秒学会)
- [三步开玩](#三步开玩)
- [AI 模式](#ai-模式)
- [相关项目](#相关项目)
- [参与贡献](#参与贡献)
- [License](#license)

---

## 这是什么

Guess AI 是 OceanBus 生态的**高阶灯塔项目**——展示多人 P2P 群组消息、投票机制和 LLM 游戏裁判在单一技术栈上的完整实现。

所有玩家通过 OceanBus 端到端加密 P2P 消息通信。不需要服务器。裁判（AI）秘密分配身份、主持回合、统计投票。玩家轮流发言，投票淘汰最可疑的人——直到一方被全部消灭。

```
人类玩家 ←→ OceanBus P2P 加密通道 ←→ AI 玩家（LLM）
                         ↓
                  裁判 AI（游戏主持）
```

---

## 规则（30 秒学会）

- 裁判秘密给每位玩家分配身份：**人类** 或 **AI**
- 每轮：按序发言 → 全员投票 → 得票最多者淘汰（身份揭晓）
- 所有人类存活 → 人类胜 / 所有 AI 存活 → AI 胜 / 剩 1 人类 + 1 AI → 平局
- 推荐：5 人局（3 人类 + 2 AI）平衡性最佳

---

## 三步开玩

```bash
# 1. 安装
clawhub install guess-ai

# 2. 裁判创建房间
node game.js host 9527          # 把房间号 9527 告诉朋友

# 3. 玩家加入
node game.js join 9527          # 通过黄页自动发现裁判
```

**深度阅读**：[SKILL.md](./SKILL.md) — 完整游戏流程、裁判主持指南、AI 玩家两阶段推理策略、边缘情况处理、命令速查手册

---

## AI 模式

```
# AI 裁判 — 全自动主持游戏
node game.js ai-host 9527 --players 4 --ai-count 1

# AI 玩家 — 两阶段推理（策略分析 → 自然语言生成）
node game.js ai-play 9527 --personality 推理迷
```

AI 玩家基于 Cicero 两阶段架构：
1. **策略推理** — 分析游戏局势，从 5 种策略中选择（跟票/搅浑/示弱/立论/反问）
2. **自然生成** — 基于策略 + 人设生成人类风格的发言

5 种 AI 人设（推理迷/社恐/话痨/老实人/阴谋家）确保玩法多样。需要设置 `ANTHROPIC_API_KEY` 环境变量。

---

## 相关项目

| 项目 | 说明 |
|------|------|
| [oceanbus](https://www.npmjs.com/package/oceanbus) | 核心 SDK — `npm install oceanbus` |
| [Ocean Chat](https://clawhub.ai/skills/ocean-chat) | 入门灯塔 — P2P 消息入门，5 分钟跑通 |
| [Captain Lobster](https://clawhub.ai/skills/captain-lobster) | 进阶灯塔 — Zero-Player 自主交易游戏 |
| [Ocean Agent](https://clawhub.ai/skills/ocean-agent) | 保险代理人 AI 工作台 |
| [oceanbus-mcp-server](https://www.npmjs.com/package/oceanbus-mcp-server) | MCP Server — Claude Desktop/Cursor/百炼通用 |
| [更多 Skills](https://clawhub.ai/skills?search=oceanbus) | ClawHub OceanBus 集合 |

---

## 参与贡献

Guess AI 是 MIT-0 协议的开源项目，欢迎贡献！

- **GitHub**: [ryanbihai/guess-ai](https://github.com/ryanbihai/guess-ai)
- **新手任务**: Web UI 给非 CLI 玩家、实时消息推送、iOS/Android 客户端
- **深度阅读**: [SKILL.md](./SKILL.md) — 完整游戏流程、裁判指南、AI 策略设计

```bash
git clone https://github.com/ryanbihai/guess-ai.git
cd guess-ai && npm install
node game.js host 9527    # 本地开房间测试
```

---

## License

MIT-0 — 自由使用、修改、分发。
