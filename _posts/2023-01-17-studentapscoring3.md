---
title: Create Task Student Submission Scoring 3
layout: post
description: Scoring the student submissions for the College Board Create Task and comparing my scores with the College Board scores. (PART 3)
toc: true
hide: false
search-exclude: false
permalink: /studentctscoring2
---

## Submission 1

This is a rock-paper-scissors simulation. It's super basic and unfortunately very lame.

### Grading

| Reporting Category | Student Score | College Board Score | Comments |
| Program Purpose and Function | 1 | 1 | The student correctly identifies the program's purpose, function, inputs and outputs. |
| Data Abstraction | 0 | 0 | The list `RPS` is shown being created, but it's not shown being directly called. |
| Managing Complexity | 0 | 0 | The list `RPS` does not manage complexity, and the explanation as to how it supposedly does is unconvincing. It could have just been done with a random number generator. |
| Procedural Abstraction | 0 | 0 | The function `rpsGame` is shown being defined and called. However, the written part doesn't explain how it contributes to the functionality of the program. |
| Algorithm Implementation | 1 | 1 | Sequencing, selection, and iteration are all used in the procedure, but the description of how it works is very minimal. |
| Testing | 1 | 1 | The procedure is tested with two different arguments that show different outputs. |

## Submission 2

This is a program that plays a game of hangman with a five-letter word, giving you six possible wrong guesses.

### Grading

| Reporting Category | Student Score | College Board Score | Comments |
| Program Purpose and Function | 1 | 1 | The purpose, function, inputs and outputs are clearly defined |
| Data Abstraction | 1 | 1 | `words5` is shown being defined and called within a procedure. |
| Managing Complexity | 1 | 1 | The student clearly describes how using it in a list makes the program less complex, and provides an example of how not using one would be more complex (instead, the five letters of the word would have to be five separate variables). |
| Procedural Abstraction | 1 | 1 | The `guessWords` function is shown being defined and called. Its functionality to the program is made clear. |
| Algorithm Implementation | 1 | 1 | Sequencing, selection, and iteration are all used in the procedure above, and how it works is made very clear. |
| Testing | 1 | 1 | Two calls are shown with clearly different code being executed and different results. |

## Submission 3

This is a program that provides various information about every U.S. state.

### Grading

| Reporting Category | Student Score | College Board Score | Comments |
| Program Purpose and Function | 1 | 1 | The program's purpose, function, input and output are all described. |
| Data Abstraction | 0 | 0 | The list is not shown being called. The first code segment is pretty much pointless. |
| Managing Complexity | 0 | 0 | The student explains how the list manages complexity very vaguely, and never provides an alternative to using a list that would be less efficient. |
| Procedural Abstraction | 0 | 0 | The procedure `updateScreen` is shown being defined, but never being called. It also incorrectly describes what the function of the procedure is exactly. |
| Algorithm Implementation | 0 | 0 | Iteration is not used in the `updateScreen` procedure. |
| Testing | 0 | 0 | Two calls are made *from* `updateScreen`, not *to* it. The written part describes two completely different actions from the user, not conditions tested by the parameter. |

## Submission 4

This is a game that simulates catching fish from a boat in a high-speed situation. Just a little fishing game.

### Grading

| Reporting Category | Student Score | College Board Score | Comments |
| Program Purpose and Function | 1 | 1 | The purpose, function, input and output are all identified well. |
| Data Abstraction | 1 | 1 | The list `fishtypes` is shown being created and called. Its importance is clearly described. |
| Managing Complexity | 0 | 1 | I disagree that using a list makes the program easier to deal with, since the amount of each type of fish caught is less identifiable when represented by list indexes. Having three separate variables for the three fish types doesn't seem any more complicated. College Board gives a point for this because the student does do a decent job justifying the use of a list. |
| Procedural Abstraction | 1 | 1 | The procedure `+clone+movement+...` is shown being created and called. Its importance to the program's functionality is clear. |
| Algorithm Implementation | 1 | 1 | Sequencing, selection, and iteration are all used in the procedure above. |
| Testing | 0 | 0 | The tests do not show multiple arguments being used to alter the output/behavior of the given procedure; they instead just show two completely different code segments that can be called. |

## Reflection

Here's what I can learn from the mistakes these people made:
- Make sure that the use of a list is genuinely important to the complexity of the program. I probably won't have to worry about this, but don't just use one because you feel like it when variables would work just as well.
- Make SURE that the selected procedure for Procedural Abstraction has at least one parameter.
    - Not having at least one ruins both Procedural Abstraction and Testing, as you need to call the procedure with two different arguments for the point. Speaking of which...
- For Testing, make sure that the two tests are simply the procedure in question being called with distinctly different arguments that alter the output of the procedure.