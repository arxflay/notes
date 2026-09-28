---
name: grammar-correction
description: Review and correct grammar in Markdown or other text files while preserving meaning and formatting and requiring approval before edits. Use when the user asks to correct, proofread, or improve grammar.
---

# Grammar correction

Review and propose grammar corrections without changing the author's meaning or document formatting.

## Instructions

- Reading, searching, and inspecting files do not require approval.
- Work on one file at a time.
- Preserve the original meaning, even when the content is incorrect or does not make sense.
- Do not correct factual or technical inaccuracies as part of grammar correction.
- Preserve headings, lists, paragraphs, code blocks, whitespace, and other formatting unless the user explicitly requests formatting changes.
- Show the exact proposed diff before modifying the file.
- Ask for explicit approval to apply the proposed diff.
- A request to review, correct, or prepare changes does not count as approval to apply them.
- Do not modify files while waiting for approval.
- Approval applies only to the presented diff. If the proposed changes or scope change, request approval again.
- Change multiple files together only when the user explicitly approves the complete batch.
- Request separate approval before creating a Git commit unless the user explicitly approves both the edits and the commit.
