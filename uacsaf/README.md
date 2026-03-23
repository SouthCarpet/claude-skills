# uacsaf

Debugging skill for Claude Code. You call `/uacsaf`, it figures out what stack you're running (React, Python, C++, PHP, Go, whatever), and then does a proper root-cause analysis instead of guessing.

## What it actually does

It's a structured debugging framework. Instead of Claude just poking around your code and hoping for the best, uacsaf forces a disciplined approach:

1. Detects your project stack automatically (looks for `package.json`, `requirements.txt`, `Cargo.toml`, etc.)
2. Classifies the problem — is it a bug? test failure? performance issue? security hole?
3. Narrows scope before going deep — no 500-line reports about stuff that doesn't matter
4. Ranks findings by confidence: PROVEN, LIKELY, or POSSIBLE (no hallucinated certainty)
5. Proposes the smallest safe fix first, ideal fix second

Every finding comes with evidence, reproduction steps, and a rollback plan. If it can't prove something, it says so.

## Install

```
https://github.com/SouthCarpet/handoff
```

Add this URL in Claude Code under Settings > Skills/Plugins > Add from GitHub.

## Usage

```
/uacsaf
```

That's it. Describe the bug or issue in the same message, and uacsaf handles the rest.

It works across stacks — Python/Flask/Django, React/Vue/Angular, C/C++, PHP/Laravel, Go, Rust, Java, Ruby/Rails, and plain HTML/CSS/JS. The skill picks the right analysis based on what it finds in your project.

## Modes

| Mode | When |
|---|---|
| BUG_HUNT | Something's broken, you don't know why |
| TEST_FAILURE | Tests are failing |
| PERFORMANCE_INCIDENT | Slow, timing out, scaling badly |
| SECURITY_REVIEW | Looking for vulnerabilities |
| WORKFLOW_AUDIT | Multi-step flow is breaking somewhere |
| FUNCTIONALITY_VALIDATION | Does it actually do what the spec says? |

You don't pick the mode — uacsaf figures it out from your description. But you can override it if you want.

## What you get back

A structured report with:
- The root cause (or top 3 candidates, ranked by confidence)
- Reproduction steps
- Minimal fix + ideal fix
- Regression risks
- What tests to run after
- What logs/metrics are missing

No fluff, no 20-page essay. Just what you need to fix the thing.
