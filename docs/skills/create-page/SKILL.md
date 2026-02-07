---
name: create-knowledge-base-page
title: Create Knowledge Base Page
description: Create and publish a new Markdown page in the GTSE Knowledge Base.
version: 1.0.0
authors: [Jules]
tags: [documentation, git, jekyll]
---

# Create Knowledge Base Page

## Purpose
To add new knowledge, strategies, or guides to the repository in a structured format compatible with the Jekyll theme.

## Inputs
*   `category`: The existing folder where the page belongs (e.g., `strategy`, `seo`).
*   `slug`: URL-friendly filename (e.g., `my-new-page`).
*   `title`: The human-readable title of the page.
*   `content`: The markdown content of the page.
*   `nav_order`: (Optional) Integer for ordering in the sidebar.

## Procedure

1.  **Validate Category**: Ensure the `category` folder exists in `docs/`.
2.  **Create File**:
    *   Path: `docs/<category>/<slug>.md`
    *   Content:
        ```markdown
        ---
        layout: default
        title: <title>
        parent: <Category Parent Title>
        nav_order: <nav_order>
        ---

        # <title>

        <content>
        ```
3.  **Update Index**: Append a link to the new page in `docs/<category>/index.md` if not auto-generated.
4.  **Commit**: Commit with message "docs: add <title> to <category>".

## Example
> Create a page titled "Q4 Plan" in "Strategy".
> File: `docs/strategy/q4-plan.md`
