# claude-skills

A collection of Claude Code skills. Install the whole repo and get all of them, or browse individual skills below.

## Install

Add this URL in Claude Code under Settings > Skills/Plugins > Add from GitHub:

```
https://github.com/SouthCarpet/handoff
```

## Skills

### [handoff](./handoff/)

Session continuity between Claude Code sessions. `/handoff save` at the end of a session writes everything important to a JSON file — what you did, what's left, architecture decisions, bugs hit. `/handoff load` at the start of the next session reads it back and picks up where you left off. No re-exploration, no "what were we doing again?"

### [uacsaf](./uacsaf/)

Structured debugging and code analysis. Auto-detects your stack (Python, React, C++, PHP, Go, Rust, Java, Ruby, etc.) and runs a disciplined root-cause analysis. Every finding is ranked by confidence with evidence, reproduction steps, and fix proposals. Doesn't hallucinate certainty it hasn't earned.

## Adding more skills

Each skill lives in its own folder with a `SKILL.md` and `README.md`. Drop a new folder in, push, and it's available to anyone who installed the repo.

```
claude-skills/
├── README.md          ← you're here
├── handoff/
│   ├── SKILL.md
│   └── README.md
├── uacsaf/
│   ├── SKILL.md
│   └── README.md
└── your-new-skill/
    ├── SKILL.md
    └── README.md
```
