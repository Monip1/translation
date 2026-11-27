---
title: Home
layout: home
permalink: /
nav_order: 0
---

# CSE 190 Study
{: .no_toc}

Open Refine Translation Task
{: .fs-6 .fw-300 }

# Overview

| Hour | Task |
|---|------------|
| 1st | Implement the Following Translation Task in Open Refine |
| 2nd | Familiarize yourself further with the codebase and how your new feature ties into the it. Prepare for walkthrough and Q&A |
| 3rd | Code Walkthrough Presentation (Q&A) |

## Using Claude for the Task


> **Agentic Development:** Use the provided Claude Code to help explore the codebase, plan changes, implement the feature, and develop tests. You must work with the agent to discover edge cases and make design decisions, rather than letting the agent make all the decisions.
>
> **You own everything your agent produces.** Anything the agent writes for you is your work. Taking ownership means you:
>
> - **Design decisions:** Understand every decision in your design, whether you or the agent proposed it. Be able to explain the options and why you chose this one.
> - **Code:** Read and understand every line you commit. If will need to be able to explain it. 
> - **Tests:** Check that the tests the agent writes test the right behavior, cover the edge cases, and can fail. A passing test is not enough.
> - **Mistakes:** If the agent gets something wrong, the mistake is yours.

## Step 1: The OpenRefine Development Environment

#### Creating Your OpenRefine Repository

Clone the [Open Refine Repository](https://github.com/openrefine/openrefine).

Name the repository `openRefine-[your_githubusername]`, using your own GitHub username. For example, if your username is `muthuvel` name it `openRefine-muthuvel`.


## Step 2: Translate Column in OpenRefine

### Motivation

This assignment is inspired by Yelp-style restaurant reviews. Imagine analyzing a dataset of reviews written by diners in different languages. You want to compare their experiences and understand feedback about the restaurants, but the language differences make it difficult to work with the reviews together. Translating them into a common language can make the dataset easier to explore and analyze while preserving the original text for reference.

In this assignment, you will extend OpenRefine so users can translate an existing text column into a new column. You will practice working across an unfamiliar codebase, integrating an external service, handling failures, and testing a complete user-facing feature.

You will use Claude Code as part of your development process. You are responsible for understanding, evaluating, and verifying the changes you submit. In practice, this means three things:

- **Understanding:** You can explain what each change does, why it is needed, and how it fits into the rest of OpenRefine, without asking the agent.
- **Evaluating:** You judge the agent’s suggestions instead of accepting them by default. Ask whether the approach follows the codebase’s conventions, whether a simpler option exists, and whether it handles failures and edge cases.
- **Verifying:** You check that the work is correct by running it. Run the tests, try the feature in OpenRefine yourself, and test the cases you expect to break. Do not trust the agent’s claim that something works.

### Task

Add a feature that lets a user select an existing text column, choose a target language, and create a new column containing the translated text.

For example, a project containing Yelp-style reviews may include reviewer names or IDs, restaurant names, and multilingual review text. A user should be able to translate the reviews into a chosen language and see the translations alongside the original data.

**You choose which languages to support and how many.** Every pair must support at least these three languages, each as both a source and a target: **English, Spanish, and Mandarin Chinese**. Beyond that, the sky is the limit. Add as many languages as you like, for example Telugu, Tamil, Hindi, or French.

For reference, our own solution supports five: Spanish, Mandarin Chinese, English, Telugu, and Tamil. Treat that as one example, not a target. Document your supported languages in `design.md` and explain how someone would add another one.

The images below show the result we expect: the original column stays as it is, and a new column with the translated text appears next to it. They do **not** show a required design. You do not need to match their layout, buttons, or wording.

You decide how the feature works in the interface and how it fits into OpenRefine. For example, you decide:

- Where the user starts the operation.
- How the user chooses the column and the target language.
- What the user sees while translation is running, and when something goes wrong.
- How the new column is named and where it is placed.

Look at how existing OpenRefine features handle these questions, and follow the codebase’s conventions. Explain your choices and the alternatives you considered in `design.md`.

**Before operation**

![Before operation](https://cse190largecodebasesfall2026.github.io/assets/assignments/BeforeTranslation.png)

**After operation**

![After operation](https://cse190largecodebasesfall2026.github.io/assets/assignments/AddedTranslationColumn.png)

### Required features

- **Translation:** You decide how the translation is done. You can call a hosted translation API, or you can run a translation server or model locally. Either way, it must support at least the three required languages (English, Spanish, and Mandarin Chinese) as both source and target languages, plus any extra languages you choose to support. Compare the options and choose one. Think about cost, usage limits, setup effort, speed, translation quality, and how easily someone else can run your code.

- **New column and data preservation:** Place each translation in the row corresponding to its original text. Preserve the source column, other existing data, and row order. Do not overwrite an existing column without warning.

- **OpenRefine integration:** Integrate the feature with the frontend and backend using the codebase’s existing conventions.

- **Dataset:** Find a Yelp reviews dataset online, or generate your own Yelp-style reviews, for testing purposes. You may choose any dataset as long as it contains a column for text reviews. Commit a small sample of about 20 rows to the `Assignment3/` folder so anyone running your feature (for example, tutors while grading your final PR) can try it. The sample should include reviews in every language you support, so a grader can test each one.

- **Edge cases and design decisions:** Identify edge cases and document your chosen behavior (e.g., failure handling, translated text in the same language, etc). Explain decisions that affect the user experience in `design.md`.

- **Testing:** Run the relevant existing tests, and add new tests that cover your feature’s normal behavior, the edge cases you chose to support, and failure handling. If your changes break an existing test, work out why. Change the test only if the expected behavior has intentionally changed. Do not delete or disable failing tests. All relevant existing tests and your new tests should pass in your final submission.

Use the [presentation page](./QA.md) for the plan, tips, and details on how the Q&A works, with example questions.


### Exporting your chat history

Save your full conversation with the agent in the `transcripts/` folder. If you used more than one session, add one file per session and name them so the order is clear (for example `chat-1.md`, `chat-2.md`).

**Claude Code:** In the session, run `/export session.md`. This saves the conversation as plain text to that file. If you run `/export` with no filename, a dialog lets you copy to the clipboard or save to a file. See the [Claude Code commands reference](https://code.claude.com/docs/en/commands).

Export before you close each session, and move or save the file into `transcripts/`.

<style>
  .meme {
    max-width: 300px;
  }

  @media screen and (min-width: 1024px) {
    .meme {
      float: right;
      margin-left: 16px;
    }
  }
</style>
