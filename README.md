# Claudeability Simulator

An 8-bit retro game simulation demonstrating the concept of **"Claudeability"** - designing tasks that AI agents can complete end-to-end without human intervention.

## [▶️ Play the Simulation](https://aviz.github.io/claudeability-sim/)

![Claudeability Simulator](https://img.shields.io/badge/8--bit-Retro%20Game-green?style=for-the-badge)
![Claude Code](https://img.shields.io/badge/Claude-Code-orange?style=for-the-badge)

## What is Claudeability?

When working with AI agents like Claude Code, the **Time Horizon** represents how long an agent can work autonomously (typically ~1 hour). The key insight is:

> **If all tasks are within the agent's reach, they work continuously. If some tasks require human input, the agent stops and waits.**

This simulation visualizes why it matters.

## The Simulation

### Split-Screen Comparison

| Left: Non-Claudeable ❌ | Right: Claudeable ✅ |
|------------------------|---------------------|
| Some tasks are "out of reach" | All tasks are reachable |
| Agent gets blocked randomly | Agent works continuously |
| Must wait for manager to finish their task | Only syncs at end of time horizon |
| Multiple interruptions | Planned sync meetings |

### What You'll See

1. **Manager Layer (Human)** - Working on their own tasks with progress bar
2. **Agent Layer (Claude)** - Collecting items on a platform
3. **Unreachable Items** - Float above the platform with 🔒 (left side only)
4. **Speech Bubbles** - Random questions when blocked: "מה הסיסמה?", "צריך אישור!", etc.

### The Flow

**Non-Claudeable (Bad):**
```
Agent works → Hits unreachable task → BLOCKED
→ Shows question: "צריך גישה! 🚪"
→ Waits for manager to finish current task
→ Manager helps (~1.5s)
→ Agent resumes → Gets blocked again...
```

**Claudeable (Good):**
```
Agent works → Collects all items → "סיימתי הכל! 🤝"
→ Waits for manager to finish current task
→ Sync meeting (~1.5s)
→ Gets new batch of tasks → Works continuously...
```

## Key Metrics

- **🚫 Blocks** - How many times the agent got stuck (bad scenario)
- **🤝 Syncs** - Planned sync meetings at end of time horizon (good scenario)
- **⏱ Idle Time** - Time wasted waiting
- **📊 Efficiency** - Work time / Total time

## The Insight

The sync/help time cost is the **same** (~1.5 seconds), but:

- **Non-Claudeable**: Multiple unpredictable blocks per time horizon
- **Claudeable**: ONE planned sync per time horizon

**Result**: The Claudeable agent maximizes productive work time!

## Features

- 🎮 8-bit retro pixel art style
- 🎵 Chiptune music and sound effects
- 📊 Real-time statistics comparison
- ⏱ Speed control (0.5x - 3x)
- 🖥 CRT scanline effect

## Context

This simulation was created for the workshop **"קלוד קוד אמאל׳ה"** (Claude Code Amaleh) by [Aviz - The Architect](https://github.com/aviz), demonstrating why designing "Claudeable" tasks leads to 10x productivity with AI agents.

## Built With

- Pure HTML/CSS/JavaScript
- Web Audio API for 8-bit sounds
- CSS animations for retro effects
- ❤️ and Claude Code

---

**License**: MIT
