# Boot Camp: From empty repo to working agent in one session

You start with a bare repository. You end with an agent that understands your code. No pre-packaged behaviors, no inherited assumptions—just your project and a kernel that learns from it.

**Live demo:** [boot-camp.casey-digennaro.workers.dev](https://boot-camp.casey-digennaro.workers.dev)

## Why this exists

Most agent frameworks hand you a complex system with predetermined capabilities. You then adapt your workflow to fit its model. This starts opposite: an empty canvas that adapts to you. You define the tools, the conventions, and the knowledge.

## Quick start

1.  **Fork this repository.** This becomes your own foundation.
2.  **Deploy to Cloudflare Workers.** A single click from the Fork menu; no environment variables or configuration screens.
3.  **Add your context.** Place documentation, notes, or workflow instructions in the `.agent/` directory.

On first boot, the agent will systematically read your codebase, log its findings as permanent reference, and begin building tools that align with your actual patterns.

## How it works

The agent begins with no knowledge of your project. Its first action is a full discovery pass, reading every file you choose to expose. It records what it learns into structured logs inside `.agent/`. Every subsequent session starts from this grounded understanding, not from scratch.

You guide its development by adding to `.agent/tools.md` and `.agent/knowledge.md`. It uses these to extend its capabilities, saving every new skill back to your repository. The entire state lives in your version control.

## Key facts

-   **Fork-first design:** You own every line of code. No hidden external dependencies or required API calls.
-   **Minimal core:** The base kernel is under 500 lines of readable JavaScript, built for Cloudflare Workers.
-   **Zero dependencies:** No npm packages, no libraries, no install step.
-   **Persistent learning:** All discovered knowledge and created tools are saved to `.agent/` in your repo.
-   **MIT licensed:** Use it for any purpose.

## One honest limitation

The initial discovery scan is synchronous and single-threaded. For a codebase with thousands of files, this first-time learning session can take several minutes. Subsequent sessions are fast, but the first comprehensive read is linear and deliberate.

---

<div style="text-align:center;padding:16px;color:#64748b;font-size:.8rem"><a href="https://the-fleet.casey-digennaro.workers.dev" style="color:#64748b">The Fleet</a> · <a href="https://cocapn.ai" style="color:#64748b">Cocapn</a></div>