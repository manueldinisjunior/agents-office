# DEVAF Agents Office

This repository is my personal adaptation of the Agents Office project. I use it as a software engineering sandbox for building systems around autonomous agents, knowledge work, and the broader idea of super intelligence: not as a marketing product, but as an environment for experimentation, thinking, and execution.

I am Manuel Dinis Júnior, a software engineer with a strong interest in super intelligence, agentic software, and AI-first workflows. This project reflects that interest: a personal office of AI agents that can read my notes, reason with context, act through the tools I already trust, and help me move from ideas to structured work.

![Agents Office — six department pods around the Brain, with the Task Status panel](assets/readme-hero.jpg)

A 3D isometric office where AI agents do real work on your own Claude login.

Six departments, thirty-five agents at their desks, a task bar that routes what you type to the right agent, and a Brain at the centre that is your own folder of notes. Type a task, the office gives it to the right person, they read your notes, use the connectors you have already set up in Claude Code, do the work, and file the result back into your notes. Everything runs on your machine.

This is my personal version of that idea: a workspace where I can shape the office around my own work style, knowledge system, and research interests.

## Why this exists

I want an AI operating environment that behaves less like a chatbot and more like a digital team: structured, contextual, accountable, and useful across real work.

This project gives me:

- a personal knowledge brain powered by notes and links
- role-based agent routing by department and expertise
- real tool access through the Claude Code ecosystem
- a way to teach agents how I work through briefs, skills, and corrections
- routines and scheduling for work that should happen without me typing every step
- a system for experimentation in the direction of super-intelligence-aligned workflows

## Core concepts

### The Brain

The Brain is the center of the office: a local folder of notes, ideas, documents, and links. It acts as the long-term memory of the system. The agents read from it before acting, and their deliverables are saved back into it as dated notes.

This makes the project more than a prompt interface. It becomes an operational memory layer for my own thinking and work.

### Departments and agents

The office is structured around six departments:

- Marketing
- Emails
- Sales
- Operations
- Finance
- Delivery

Each department has a lead and multiple specialized desks. The system routes work to the most suitable agent based on the task and context.

### Task flow

A task can be typed directly into the office, assigned to a department, and then routed to the most relevant agent. The agent reads the notes, uses the tools it is allowed to call, completes the task, and records the output in the Brain.

### Connectors and tools

The office can integrate with the MCP servers and connectors already connected to Claude Code on this machine. That means the agents can use the same external systems I already use, such as Gmail, Google Drive, Slack, Notion, Canva, browser-based tools, and more, depending on configuration and authorization.

The principle is simple:

- read freely
- act only when the task explicitly asks for it
- keep the work grounded in my notes and instructions

## What you need

- macOS or Linux (Windows: works with `npm` commands directly; `./setup` is Bash only)
- Node.js 20+
- git
- Claude Code, logged in with your Claude account, or an `ANTHROPIC_API_KEY`

## Install and run

```bash
git clone https://github.com/ajsahni/agents-office.git
cd agents-office
./setup          # checks Node, git and Claude; installs; builds; boots once
npm start        # -> http://localhost:4520
```

Without `./setup`:

```bash
npm install && node build.mjs && npm start
```

## First minutes in the office

1. Open http://localhost:4520.
2. Pick a department and type a task in plain language.
3. The office routes it to the most suitable agent.
4. The agent reads the relevant notes and works through the task.
5. The result lands in the agent chat and in the Brain as a note.
6. If needed, use `revise: ...` to improve the output.

## Making the office mine

The original project is structured for customization. I use it as my own personal operating system for AI work. The office can be adapted by changing the roster, the agent briefs, the skills, the connectors, the routine schedules, and the Brain folder.

The agents are not just generic assistants; they can be tailored to how I think and work.

Examples from the original project still apply here:

- rewrite each agent's role and purpose
- adjust tools and department responsibilities
- teach agents via a brief or a skill
- store useful notes in the Brain
- automate recurring workflows with routines
- use the calendar to schedule tasks
- activate team mode for split jobs

## Teaching the agents how I work

I can personalize the office in two practical ways:

- a brief: a few standing instructions about tone, constraints, or escalation
- a skill: a folder with a `SKILL.md`, a template, and an example for how a task should be done

This is how the office becomes truly personal instead of generic.

## Routines and scheduled work

The office can run recurring work on its own clock:

- daily checks
- weekly tasks
- recurring reports
- routine triage
- scheduled outbound work with approval gating

A routine may simply read and report, or it may prepare drafts and wait for my approval before sending, paying, or changing anything.

## Calendar and task planning

The office includes a calendar view for:

- scheduled tasks
- routine projections
- day-based planning
- department and routine filtering
- task history and next actions

This helps keep work visible and time-aware instead of purely conversational.

## Agent teams

Some jobs should be split across multiple agents. The office supports team-based execution where a lead decomposes the work, the individual desks execute independently, and the final result is assembled by the lead.

This is especially useful for:

- parallel analysis
- multi-perspective reviews
- content production with independent pieces
- larger research or planning tasks

## Which model and effort level

The office supports model selection by task, routine, agent, or office default. The project keeps model control flexible:

- Sonnet
- Opus
- Fable

And effort settings such as low, medium, high, extra high, and max can be applied at the appropriate level.

## Connectors and security

The office reads the real MCP server list from Claude Code and exposes only the relevant tools to the agents. Depending on configuration, it can allow or deny tools, limit them by department, and keep the browser and web access controlled.

The default rule is very important:

- read freely
- act only when the task explicitly asks for the exact action
- keep all sensitive work grounded in my own authorization and judgement

## Build and validation

The project includes a build and validation loop:

```bash
npm run check
npm run check:live
```

These checks validate the build, the office logic, and the project state before relying on it for real work.

## Project layout

| Path | What it does |
|---|---|
| `src/` | Main office logic, tasks, Brain, connectors, and UI |
| `serve.mjs` | Local server and routing |
| `mcp.mjs` | Connector and tool management |
| `roster.mjs` and `office.agents.json` | The 35 agents and their configuration |
| `skills.mjs` and `skills/` | Skills and task-specific workflows |
| `learn.mjs` | Feedback and corrections from `revise: ...` |
| `onboard.mjs` | Set-up interview for department leads |
| `routines.mjs` and `src/when.js` | Timetables and recurring work |
| `brain/` | Sample knowledge base and note system |
| `CLAUDE.md` | Guidance for Claude Code in this project |
| `SKILLS.md` | Guide to briefs and skills |
| `dist/command-centre-v2.html` | Built office view |

## Personal note

This project is not only a tool for getting tasks done. It is also a research environment for my interest in super intelligence: how AI systems can organize memory, collaborate, reason with context, and operate as a coherent digital workforce.

I want the office to become more aligned with my ideas, my constraints, and my working style over time. That is why the project is shaped around personal notes, personal routines, and my own reasoning process.

## Privacy

Your notes are read from disk and supplied to Claude only as context when needed. Agents call connectors through your own Claude Code login, just as you would. Deliverables are saved locally, and nothing is sent outside your machine unless explicitly requested by the task itself.

## License

This project remains based on the original Agents Office codebase and retains the project’s licensing terms. The original license is included in [LICENSE](LICENSE).

---

My goal is simple: turn a powerful agent workspace into a personal system for thinking, building, and exploring the future of intelligent software.
