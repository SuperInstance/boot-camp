# Cocapn Boot Camp
> Turn an empty repository into a functioning agent in one session.

Most agent setups require days of manual configuration and context injection. Boot Camp starts with a bare kernel and builds a captain that understands your specific project by exploring it directly.

---

## Why this exists
Agent onboarding often involves extensive manual setup—pasting prompts, copying context, and configuring tools. Boot Camp takes a different approach: it drops a minimal kernel into an empty repository and lets the agent explore and adapt to the environment autonomously.

---

## From empty repository to working agent

### Boot Camp vs. Dojo
These are separate components of the Cocapn Fleet with distinct purposes.

**Dojo** is a training laboratory. It runs experiments to compare different training methodologies and techniques.

**Boot Camp** is a deployment forge. It takes a repository without an agent and produces a functional captain tailored to that project.

```
DOJO                              BOOT CAMP
────                              ─────────
Tests training methods            Trains captains
Compares methodologies            Converts bare repo → working agent
Laboratory                        Forge
Outputs research data             Outputs trained agent + skill files
```

---

## How it works
1. **No pre-trained behavior.** The agent builds its capabilities after arrival, avoiding inherited assumptions from other projects.
2. **Persistent discovery.** The agent logs its environment findings as ground truth, avoiding redundant probing each session.
3. **Ergonomics-driven.** It observes your workflow and builds tools that match your actual usage patterns.
4. **Fork-first.** You own every line of code. The agent operates locally without external calls unless you configure them.

Boot Camp runs on Cloudflare Workers with an MIT license. No paid tiers or mandatory API keys beyond those you provide.

---

## The Boot Camp process

### Phase 0: Initialization
The Cocapn kernel (~500 lines, zero dependencies) lands in your repository. It boots and performs an initial probe of the environment.

```
┌─────────────────────────────────────┐
│  Repository (initially empty)       │
│                                     │
│  ├── cocapn kernel                  │
│  ├── .agent/ (created on boot)      │
│  └── No prior configuration         │
│                                     │
│  Kernel boots → Captain wakes       │
│  Initial probe: "What is here?"     │
│                                     │
└─────────────────────────────────────┘
```

The kernel runs identically across environments: local hardware, isolated containers, Cloudflare Workers, or remote terminals.

### Phase 1: Exploration and grounding
The agent explores the repository structure, documentation, and existing code. It logs its findings as immutable ground truth, building a contextual understanding of the project.

### Phase 2: Tool building and adaptation
Based on the exploration and your interactions, the agent develops practical tools tailored to the project's needs and your workflow.

### Phase 3: Captain emergence
The agent synthesizes its knowledge into operational competence, capable of handling tasks, answering questions, and managing the repository autonomously.

---

## Quick start
1. Fork the Boot Camp repository.
2. Deploy to Cloudflare Workers (or run locally via `wrangler dev`).
3. Add your repository as a target.
4. Start a session. The agent will explore and adapt over one continuous run.

Detailed deployment instructions are in the `DEPLOY.md` file.

---

## Limitations
Boot Camp requires a project with some structure or documentation to analyze. Completely empty repositories without any context (like a blank `README`) will result in a generic agent that lacks project-specific knowledge.

---

## Attribution
Boot Camp is part of the Cocapn Fleet, developed by Superinstance & Lucineer (DiGennaro et al.).

<div>
  <a href="https://the-fleet.casey-digennaro.workers.dev">The Fleet</a> |
  <a href="https://cocapn.ai">Cocapn</a>
</div>