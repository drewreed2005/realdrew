---
title: College Board Create Task Student Submission Scoring
layout: post
description: Scoring the student submissions for the College Board Create Task and comparing my scores with the College Board scores.
toc: true
hide: false
search-exclude: false
permalink: /studentctscoring
---

## Submission 1

This submission, taking place completely within the console, allows the user to input the side lengths of a triangle and then outputs the trigonometric ratios created by each side length in a table.

### Grading

| Reporting Category | Student Score | College Board Score | Comments |
| Program Purpose and Function | 0 | 0 | The purpose is not described, but instead the function of the program. The purpose is unclear. The video shows the program working as intended. |
| Data Abstraction | 1 | 1 | The data stored in `sideIndex` is abstracted under a clear name. It is called later under the correct conditions for the elements' purposes. |
| Managing Complexity | 0 | 0 | In the written response, the `sideIndex` list is shown, but the way that it manages complexity is unconvincing. It would be just as efficient to put the elements within the list in the conditionals that it is called within. |
| Procedural Abstraction | 1 | 1 | The `ratioCalculate` funciton is shown, which calculates the ratio of the side lengths. |
| Algorithm Implementation | 1 | 1 | Sequencing, selection, and iteration are all used in the procedure, though only a little bit for the latter. |
| Testing | 1 | 1 | The procedure is tested with two different plausible sets of variables with different results. |

## Submission 2

This submission allows the user to create a customizable simulation based on the rules of John Conway's *Game of Life*, in which the user can place and remove tiles to be modified in the simulation. It is supposed to entertain the user.

### Grading

| Reporting Category | Student Score | College Board Score | Comments |
| Program Purpose and Function | 1 | (TBD) | The purpose is stated to be entertainment, and the function is to create a simulation which follows the rules of John Conway's *Game of Life*. There is clear incorporation of input and output with the tiles. |
| Data Abstraction | 1 | 1 | The data stored in `startGrid`, `currentGrid`, and `nextGrid` is clearly called and relevant throughout the function to depict the state of the thousands of tiles. |
| Managing Complexity | 1 | 1 | The grid lists very clearly show how complexity is managed, as 10,800 tiles is unreasonable to try to manage with individual variables or unstructured means of data storage. |
| Procedural Abstraction | 1 | 1 | The intermixing of the `replaceList` and `resetall` functions thorughout the program show their relevance and functionality. Their names clearly describe their functions. The written portion meets all criteria. |
| Algorithm Implementation | 1 | 1 | Sequencing, selection, and iteration are all used in the procedure above. |
| Testing | 1 | 1 | Two calls are shown with clearly different results. |

## Reflection

I ended up scoring exactly the same as the College Board criteria. There was one case (Submission 1's "Algorithm Implementation") that I graded it a 0 initially, but then realized that there was a for loop at the bottom of the function in question. I thought there wasn't iteration, which was the reason I had given it a 0 in the first place, so I changed it to a 1.

While I ended up grading things the same, being forced to scrutinize the Create Task rubric makes me a lot more confident that I'll be able to meet the requirements easily. How will I do it? I wrote a bit about that below.

### How I Can Meet the Requirements?

- Very clearly distinguish between purpose and function. The function is what the program literally does and the purpose is why that function matters/what its effect is on the user.
- Store and call information in a list, specifically information that is made more easily accessible by it being in a list.
- Include a aptly-named method that incorporates sequencing (correctly ordering events chronologically in the function), selection (can be an if statement or other conditional), and iteration (loops, baby).
- The written portion should contain two distinct, realistic tests that show the functionality of the program.
- The written portion should include very distinct screenshots of the list, where it is called, the procedure, where it is called, and any other described evidence that is necessary for the grade.