# LLM Wiki

A pattern for building personal knowledge bases using LLMs.

This is an idea file, it is designed to be copy pasted to your own LLM Agent (e.g. OpenAI Codex, Claude Code, OpenCode / Pi, or etc.). Its goal is to communicate the high level idea, but your agent will build out the specifics in collaboration with you.

## The core idea

Most people's experience with LLMs and documents looks like RAG: you upload a collection of files, the LLM retrieves relevant chunks at query time, and generates an answer. This works, but the LLM is rediscovering knowledge from scratch on every question. There's no accumulation. Ask a subtle question that requires synthesizing five documents, and the LLM has to find and piece together the relevant fragments every time. Nothing is built up. NotebookLM, ChatGPT file uploads, and most RAG systems work this way.

The idea here is different. Instead of just retrieving from raw documents at query time, the LLM **incrementally builds and maintains a persistent wiki** — a structured, interlinked collection of markdown files that sits between you and the raw sources. When you add a new source, the LLM doesn't just index it for later retrieval. It reads it, extracts the key information, and integrates it into the existing wiki — updating entity pages, revising topic summaries, noting where new data contradicts old claims, strengthening or challenging the evolving synthesis. The knowledge is compiled once and then *kept current*, not re-derived on every query.

This is the key difference: **the wiki is a persistent, compounding artifact.**

## Architecture

- **Raw sources** — immutable curated collection of source documents.
- **The wiki** — directory of LLM-generated markdown files.
- **The schema** — configuration document (CLAUDE.md or AGENTS.md) defining structure, conventions, and workflows.

## Operations

- **Ingest**: Read raw source, discuss key takeaways, write source summary page, update index.md, update relevant concept/entity pages, append to log.md.
- **Query**: Search index.md and relevant pages, synthesize answer with citations, file valuable answers back into the wiki as new pages.
- **Lint**: Periodically health-check for contradictions, stale claims, orphan pages, missing concepts, and data gaps.
