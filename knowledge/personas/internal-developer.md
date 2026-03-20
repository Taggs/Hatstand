---
title: "Internal Developer"
slug: internal-developer
type: persona
updated: 2026-03-20
---

# Internal Developer

## Profile

- **Segment**: Internal / employee
- **Role**: Software engineer, tech lead, or architect
- **Tools**: IDE with AI agent (Claude Code, Copilot, Cursor), Git, Jira
- **Primary interaction with BH-hatstand**: Consuming specs to implement features

## Goals

- Understand requirements clearly before writing code
- Get unambiguous acceptance criteria
- Know the architectural context and constraints
- Avoid rework from miscommunicated requirements

## Pain Points

- Vague or incomplete specifications
- Requirements scattered across Jira, Confluence, email, and Slack
- Unclear domain boundaries leading to scope creep
- Missing or outdated architecture documentation

## How They Use BH-hatstand

1. Read the domain README for context
2. Navigate to the relevant epic/feature/story
3. Read acceptance criteria and technical notes
4. Check architecture/ for ADRs, HLDs, LLDs, and API specs
5. Use AI agents to generate implementation from specs
6. Reference glossary and personas for domain understanding

## Key Journeys

1. Pick up a story from Jira → find the spec in BH-hatstand → implement
2. Propose an architecture change → write an ADR → submit PR
3. Review a spec for technical feasibility → provide feedback on PR
