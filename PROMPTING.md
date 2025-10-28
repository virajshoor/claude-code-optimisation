
# Prompting Guide

This guide explains how to write clear, effective prompts so an AI can produce high‑quality results. Be explicit, give context, and tell the model to use its full capabilities. Ask the model to plan steps thoroughly and show its reasoning when useful.

## Purpose
Provide a concise, repeatable process for turning a request into a high‑quality prompt that yields reliable, actionable output.

## Core principles
- Be specific: state the objective, the expected format, and acceptance criteria.
- Provide context: supply background, examples, constraints, and relevant files or data.
- Ask the model to plan: require a stepwise plan before the final answer.
- Ask for reasoning selectively: request chain‑of‑thought style decompositions for complex tasks (or ask for summaries of reasoning).
- Iterate: evaluate outputs, give focused feedback, and request refinements.

## Prompt structure (recommended)
1. Role & goal — assign a role and state the exact goal.
2. Context — include supporting info: files, examples, data, constraints, environment.
3. Requirements — list must‑haves, prohibited actions, output format, and quality criteria.
4. Plan request — ask the model to produce a step‑by‑step plan before executing.
5. Deliverables — specify concrete outputs (code, tests, explanations, CLI commands).
6. Acceptance tests — provide sample inputs/outputs or checks the result must pass.

## Quick checklist
- Is the objective one clear sentence? ✅  
- Is required format specified (JSON, markdown, code file)? ✅  
- Are constraints (time, memory, package restrictions) included? ✅  
- Did you ask for a plan and verification steps? ✅

## Example prompt templates

Basic:
"I want you to act as a senior developer. Goal: implement X feature in Y language. Context: [repo path or description]. Constraints: [libraries allowed/forbidden]. Output: code files and unit tests. First, show a step‑by‑step plan. Then implement."

Bugfix:
"Role: debugging assistant. Bug: [short description]. Reproduction steps: [commands]. Files: [file paths]. Requirements: minimal change, add unit test that fails before fix and passes after. Show plan, then patch."

Exploratory / design:
"Role: architect. Goal: propose designs for [feature]. Constraints: [scalability, tech stack]. Produce: pros/cons table, sequence of implementation steps, and recommended first PR."

## Examples of explicit constraints
- "Must use <= node 18 and no native modules."
- "Return only valid JSON with keys: status, summary, diff."
- "Limit output length to 300 tokens; include a one‑line summary."

## Best practices & tips
- Give the model permission to use "its max power": e.g., "Use your full reasoning and provide a detailed plan."
- When ambiguous, ask clarifying questions before proceeding.
- Prefer stepwise verification: ask for tests or checks the model can run mentally or in CI.
- Use small reproducible examples for debugging or spec design.
- For code tasks, require unit tests and a short explanation of the change.

## Iteration workflow
1. Prompt with context + plan request.
2. Review the stepwise plan; correct or refine it.
3. Ask for the implementation.
4. Run tests, provide failing output if any.
5. Ask for targeted fixes and re‑run tests until acceptance.

## Short do/don't
Do: be explicit about format, acceptance criteria, and constraints.  
Don't: leave goals vague or omit how results will be validated.

## Closing
Clear context + explicit requirements + a requested plan = higher quality, predictable AI output. Use the templates above as starting points and adapt them to the task and environment.