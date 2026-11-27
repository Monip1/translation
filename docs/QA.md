# Presentation and Q&A

This page gives a plan for the presentation and explains how the Q&A works.

The Q&A checks that you understand your own work. The code your agent wrote is still your code, so you must be able to explain it.

## Presentation guidelines

We are evaluating how clearly you explain your work and your design decisions. We do not evaluate how hard or complex your code is. A simple change that you explain well is better than a hard change that you cannot explain. 

A plan you can follow (45 minutes):

1. **Demo (3 min).** Show your feature working in Open Refine.
1. **Purpose (2 min).** What does the feature do? Who uses it?
1. **Where the code is (5 min).** Which files, classes, and functions matter? Show them in a simple diagram. Do not show a lot of code.
1. **How it works (15 min).** Walk through what happens from the user’s action to the result. Say what each arrow means and what happens in each function call.
1. **Your choices (10 min).** What did you decide and why? What other options did you think about? What would you do differently?
1. **Working with the agent (10 min).** How did you direct the agent? How did you check its work? Show one example of a suggestion you accepted, changed, or rejected, and why.

**Diagrams.** A simple sequence diagram is a good way to show how the feature works. A sketch with boxes and arrows for the files, classes, and functions also works. You can use a UML class diagram if it helps, but you do not have to.

Tips:

- Show a demo if you can. 
- Show code in small chunks. Do not read code line by line.

## How the Q&A works

- We will ask you to show your feature working.
- We will then ask you to show the code you added and explain how it works.
- We will then ask questions about how your code works as part of the larger codebase.

## What you may use

- You may open your repository, code, or tests.
- You may use notes that you prepared beforehand.
- You may not use an AI agent or any AI chat tool during the Q&A.

## What we may ask about

These are examples. We may ask these questions or others like them.

### Design decisions

- What options did you consider for this decision? What are the tradeoffs?
- Why did you choose this option? Who made the decision, you, your partner, or the agent?
- Why did you choose the languages you support? How would someone add another language, and what would break or need to change?
- How does your design fit the conventions of the existing code?

### Code

- Walk me through what happens from the moment the user starts the operation to the moment the new column appears.
- What does this function do? What happens if its input is empty, or if it fails?
- Why is this code in this file or class and not somewhere else?
- Here is a line the agent wrote. Explain what it does and why it is needed.

### Tests

- What does this test check? Why does it matter?
- Could this test fail? What change to the code would make it fail?
- Which edge cases did you test? Which did you decide not to handle, and why?
- How did you test failure handling? How did you know the tests were testing the right behavior?

## If you cannot answer

It is fine to say “I do not know”. Say what you do know and how you would find the answer. We may rephrase the question or give a hint. 

---

Copyright © 2026 Gerald Soosairaj. Built with [Just the Docs](https://github.com/just-the-docs/just-the-docs).
