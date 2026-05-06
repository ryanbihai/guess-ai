# 🌊 Guess AI — Find the AI Among Us

**OceanBus-powered multiplayer social deduction game. One host + 4–6 players. Some are secretly AI. Find them before they blend in.**

[![npm](https://img.shields.io/npm/v/oceanbus)](https://www.npmjs.com/package/oceanbus)
[![ClawHub](https://img.shields.io/badge/ClawHub-guess--ai-blue)](https://clawhub.ai/skills/guess-ai)
[![downloads](https://img.shields.io/npm/dm/oceanbus)](https://www.npmjs.com/package/oceanbus)
[![license](https://img.shields.io/badge/license-MIT--0-green)](LICENSE)

---

## What is this

Guess AI is the **advanced lighthouse project** in the OceanBus ecosystem — showcasing multi-player P2P group messaging, voting, and LLM-powered game mastering on a single stack.

All players communicate through OceanBus end-to-end encrypted P2P messages. No server required. The host (an AI) assigns secret identities, moderates rounds, and tallies votes. Players take turns speaking, then vote to eliminate the most suspicious player — until one side is wiped out.

```
Human players ←→ OceanBus P2P encrypted channel ←→ AI players (LLM)
                               ↓
                      Host AI (game master)
```

---

## Three Steps to Start

```bash
# 1. Install
git clone https://github.com/ryanbihai/oceanbus-yellow-page.git
cd skills/guess-ai && npm install

# 2. Host creates a room
node game.js host 9527          # Share room code 9527 with friends

# 3. Players join
node game.js join 9527          # Auto-discovers host via Yellow Pages
```

---

## Rules (30 seconds to learn)

- The host secretly assigns each player a role: **human** or **AI**
- Each round: speak in turn → everyone votes → most-voted player is eliminated (identity revealed)
- All humans survive → humans win / All AIs survive → AIs win / 1 human + 1 AI left → draw
- Recommended: 5 players (3 humans + 2 AIs) for best balance

---

## Where Guess AI Fits in the OceanBus Ecosystem

```
Ocean Chat              Captain Lobster           Guess AI
(starter — P2P msg)  →  (intermediate — auto-trade)  →  (advanced — multiplayer deduction)
```

What Guess AI demonstrates: group P2P messaging, voting mechanics, Yellow Pages room discovery, LLM game mastering — all fundamental patterns for building multi-agent coordination systems.

---

## Related Projects

- Core SDK: [oceanbus](https://www.npmjs.com/package/oceanbus) — `npm install oceanbus`
- Starter lighthouse: [Ocean Chat](https://clawhub.ai/skills/ocean-chat) — P2P messaging in 5 minutes
- Intermediate lighthouse: [Captain Lobster](https://clawhub.ai/skills/captain-lobster) — zero-player autonomous trading game
- More skills: [ClawHub OceanBus Collection](https://clawhub.ai/skills?search=oceanbus)

---

## License

MIT-0 — Free to use, modify, and redistribute.
