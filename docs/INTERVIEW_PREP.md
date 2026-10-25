# Interview preparation and QA review

> These are source-review notes and **suggested** test scenarios. They do not represent executed test cases, successful builds or approved production requirements.

## Project in one sentence

Small rule-based notebook built with NLTK.

## Technical interview questions and grounded answers

### 1. Is this generative AI?

No. NLTK Chat matches text against manually authored patterns and returns predefined strings; no model training or LLM inference is involved.

### 2. What is the role of the database file?

A SQLite database exists in the repository, but the inspected notebook does not use it. It should not be claimed as a persistent chatbot store.

### 3. Does adding an item really modify a shopping list?

No. The matching rule only replies with text. A data model and persistence layer would be needed for that behaviour.

### 4. What are the main weaknesses?

Unmatched inputs, brittle regular expressions, static weather output, no structured validation and independent console/file-writing loops.

### 5. How could you test it?

Extract pattern matching into pure functions, parameterise sample inputs, assert matched/unmatched responses and validate input handling and file writes.

## Suggested functional and accessibility test cases

| ID | Scenario | Expected / verification objective |
| --- | --- | --- |
| CHAT-01 | Submit known greeting variants | Response is selected from the documented predefined replies |
| CHAT-02 | Submit unseen wording | Bot fails gracefully instead of implying it understands unsupported intents |
| CHAT-03 | Ask about the weather | Response is described as a placeholder, never actual live weather |
| CHAT-04 | Request shopping list addition | No persistent modification is implied by a text-only response |
| FILE-01 | Type quit in the console input loop | Loop terminates as expected |
| PRIV-01 | Provide user details in notebook | No sensitive real user data is committed to the repository |

## Limitations to disclose

Avoid the terms trained AI, machine-learning model, real-time weather, or persistent to-do integration when discussing the current implementation.

## How to discuss the project

Explain what the code currently contains, which components you actually developed, the difference between intent and implementation, one defect or risk you identified, and how you would validate a fix. Avoid claiming tests have passed unless you can provide reproducible evidence.

## Suggested next improvements

- Verify a clean checkout/build with a documented environment.
- Record reproducible bugs or missing features as GitHub Issues.
- Add evidence-backed screenshots and a short demo only after confirming they match the actual project.
- Add focused automated tests where the architecture makes them worthwhile; keep manual exploratory and accessibility testing visible.
