# PAB Bot — rule-based chatbot experiment

**Python · NLTK · Jupyter Notebook**

> **Status:** Small exploratory notebook, not a production assistant or a large-language-model application.

## Overview

PAB (Personal Assistant Bot) is a basic conversational experiment using NLTK's rule-based chat utilities. The notebook maps text patterns to predefined responses and includes a separate console exercise for writing customer details to a local text file.

Despite this repository's name, it **does not train or serve an AI model**.

## What the notebook contains

- Regular-expression-style pattern/response pairs using NLTK Chat.
- Simple greeting and name-related replies.
- A few predefined shopping and to-do responses.
- A console conversation loop using chat.converse().
- A separate input loop that writes customer name, age and gender to data.txt.

**Important distinction:** the shopping/to-do responses are text only; there is no implemented persistent shopping or task list. The database file tracked in the repository is not used by the notebook's displayed logic.

## Repository contents

- **PAB Bot.ipynb** — exploratory notebook.
- **data.txt** — empty sample output file, rewritten when the file-writing cell runs.
- **listofitems.db** — SQLite file in the repository; no active database integration was found in the inspected notebook.
- **.gitignore** — excludes local Python environments, generated notebook checkpoints and local data from new commits.

## Run the experiment

1. Install Python 3 and JupyterLab or Notebook.
2. Install NLTK:

   ~~~bash
   python -m pip install nltk jupyterlab
   ~~~

3. Start JupyterLab, then open **PAB Bot.ipynb**.
4. Run cells selectively. The conversation cell waits for user input; stop or interrupt the kernel to exit.
5. The separate data-entry cell writes to data.txt and loops until quit is entered; avoid entering real personal data.

No external model credentials are necessary, and no automated runtime verification was performed for this documentation update.

## Known limitations

- Replies are entirely pattern-based and can be inconsistent or fail for different phrasing.
- A weather response is hard-coded, not fetched from live weather data.
- The notebook mixes two independent experiments: chat matching and data collection.
- The text-file loop has no structured validation, data minimisation or privacy safeguards.
- No meaningful automated tests, package lockfile or deployment interface is provided.
- The tracked SQLite database and empty sample data file deserve a separate review before being retained or removed. Previously tracked files remain in history even when ignored.

## QA learning opportunities

Test unmatched phrases, whitespace/case variants, pattern priority, exit behaviour, unsupported intents, unexpected input and personally identifiable data handling. Consider extracting pure functions from the notebook so they can be unit tested.

## Portfolio context

An early Python/NLTK learning exercise. The main value is understanding the limits of hard-coded conversational logic and describing concrete improvements, rather than claiming advanced AI engineering.