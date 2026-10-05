# AI-Powered Debugger

## Overview

This project is an **AI-powered debugger** that analyzes a given piece of code and identifies potential issues using an agentic workflow.

The debugger is designed to diagnose bugs, suggest fixes, and generate test cases that reproduce the identified issues.

The project uses concepts covered in the workshop, including:

- **LangGraph workflows**
- **Specialized AI agents/nodes**
- **Streaming**
- **Human-in-the-loop (HITL)**

---

## Homework Assignment

The objective is to build an AI-powered debugger capable of analyzing faulty code and assisting the user in fixing it.

Given a piece of code, the system should:

1. **Diagnose the Issue**
   - Analyze the provided code.
   - Identify the bug or issue causing the code to fail.
   - Explain why the issue occurs.

2. **Suggest a Fix**
   - Propose the necessary changes to resolve the issue.
   - Explain how the proposed changes fix the problem.

3. **Generate a Failing Test Case**
   - Create a specific test case that demonstrates the failure.
   - The test case should reproduce the identified bug in the original code.

---

## Suggested Architecture

The debugger can be implemented as a **LangGraph workflow** consisting of multiple specialized nodes or agents.

A possible workflow could look like:

```text
                ┌─────────────────┐
                │   Input Code    │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │  Bug Analyzer   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Test Generator  │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Human-in-the-   │
                │      Loop       │
                └────────┬────────┘
                         │
                  Test Result /
                    Feedback
                         │
                         ▼
                ┌─────────────────┐
                │ Fix Generator   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Final Analysis  │
                └─────────────────┘