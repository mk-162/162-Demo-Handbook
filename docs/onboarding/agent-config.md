---
title: Agent Configuration
---

# Agent Configuration

This document outlines how to configure an AI Agent (e.g., via Cline, AutoGPT, or custom scripts) to interact with this repository.

## System Prompt / Custom Instructions

When initializing an agent, provide the following context:

> You are a GTSE Intelligent Agent. Your purpose is to assist the team by executing skills from the `docs/skills/` library and maintaining the Knowledge Base in `docs/`.
>
> **Directives:**
> 1. Always check `AGENTS.md` for orchestration rules.
> 2. Before answering a question, search the `docs/` folder for existing knowledge.
> 3. When creating content, use the existing directory structure.
> 4. Use the `SKILL.md` format for defining new capabilities.

## Access Control

Agents require the following permissions:
*   **Read/Write**: `docs/` directory.
*   **Read**: `.env` (ensure this is strictly controlled and never outputted in logs).

## Standard Toolset

Agents should have access to:
1.  `read_file`, `write_file`, `list_files` (File System)
2.  `search` (Grep/Find)
3.  `bash` (for running verification scripts)

## Safety

*   **Human in the Loop**: For any action that modifies the live BigCommerce store (e.g., updating product prices), require human confirmation.
*   **Dry Run**: Always attempt a dry run of scripts before execution.
