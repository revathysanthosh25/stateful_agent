# Stateful Agent — Week 4

A LangGraph agent demonstrating stateful, human-in-the-loop workflows.

## Flow
Plan → Human Approval (HITL) → Execute Tool → Stream Results → Persist (SQLite)

## Features
- Custom StateGraph with planner, human-approval, and executor nodes
- Human-in-the-loop approval via `interrupt()` / `Command(resume=...)` before any tool runs
- SQLite-backed persistence (`checkpoints.db`) — conversation state survives across runs
- Streaming output via `.stream()`
- Traced in LangSmith (project: `stateful-agent-week4`)

## Tools
- `calculator` — safe arithmetic evaluation

## Setup

uv sync:
Requires `GROQ_API_KEY` and `LANGSMITH_API_KEY` in a `.env` file.