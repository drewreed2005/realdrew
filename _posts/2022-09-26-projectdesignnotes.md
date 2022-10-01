---
title: Big Idea 1 - Program Design and Development Notes
description: Notes taken based on the corresponding CollegeBoard post.
toc: true
layout: post
comments: true
hide: false
search_exlude: false
permalink: /programdesignnotes/
---

# What is Program Design?

Program design entails frontend (UI) and backend (code), but also all of the individual parts and how they contribute to the program purpose(s). Designing a program means combining all of these aspects of a program.

## What is the process? (Daily Video 1)

Every program starts with an idea. Programmers sometimes go step-by-step, though other times it can be a more exploratory process. Programmers note the purpose of their program, its requirements, its constraints, and its user's concerns and interests. The latter may be understood best with surveys and forms of user testing.

After reflecting and investigating, programmers...
<ul style="list-style-type:circle;">
    <li>Brainstorm their idea</li>
    <li>Storyboard the program</li>
    <li>Plan the user experience</li>
    <li>Lay out the user interface</li>
    <li>Organize into modules</li>
    <li>Develop a testing strategy</li>
</ul>

Programmers then decide on program requirements that...
<ul style="list-style-type:square;">
    <li>Describe program behavior</li>
    <li>List user interactions</li>
    <li>Plan the user experience</li>
    <li>Lay out the user interface</li>
    <li>Organize into modules</li>
    <li>Develop a testing strategy</li>
</ul>
Program specifications must outline all requirements. A prototype is then created, frequently in an incremental process so that developers can define individual *modules* of the program.

The program is then tested, both in a micro and a macro level. Tests provide feedback to developers, upon which they reflect and react accordingly.

## Who is involved in the process? (Daily Video 2)

Programs are developed in teams. Parts of or individuals in these teams work on certain functional components. It is important to credit these individuals and what they complete so that they can receive the credit they deserve. This can be done with comments within the program.

These developers very often borrow code from other developers who aren't directly a part of the team. These people still need to be credited, as the code is the intellectual property of the original author. The program documentation should include that person's name, as well as the source from which it was found. This is like a code bibliography.

## How is documentation used when designing a program? (Daily Video 3)

Program documentation describes the overall program and lists specifications and requirements. This documentation often includes functions/procedures/methods to be used in the program, events and their corresponding outputs, details about program development, how other programs react with this program, and may even include segments of the actual code. It is important to list contributors to the program in documentation.

The documentation process occurs over time.
<dl>
    <dt>At the beginning</dt>
    <dd>List specifications</dd>
    <dt>During development</dt>
    <dd>Keep track of progress</dd>
    <dt>After completion</dt>
    <dd>To document the process</dd>
</dl>

Documenting throughout can improve programming efficiency, the refinement of the program, and the programmers' ability to respond to bugs.

Typically, documentation comes in the form of comments within the code which do not affect the code itself. In Python, comments are made using `#` before a string of text. Java (matched similarly by Javascript, C++, and Swift) uses `//` for single line comments, but `/*[text]*/` can be used for multiple-line comments and `/**[documentation text]*/` can be used for specifically multiple-line documentation text. HTML comments are a bit more involved, following this format: `<!--[text]-->`.

Documentation is an important step not only for keeping track of your own progress, but also for collaborating with other programmers who do not have the specific knowledge of what you have completed or what you intend to do with a certain segment of code.

# College Board Quizzes

As a requirement for this week ("Deployment"), we have been asked to show evidence that we have completed the multiple-choice College Board quizzes assigned to us.

## Screenshot of Completed Quizzes

<img src="{{site.baseurl}}/images/cbmcproof.png" alt="Program Purpose question" width="600"/>

As you can see, I got an unfortunate total of two questions wrong on these quizzes. I go into why I got them wrong below. In short, one is a matter I'm still confused about and the other was an oversight that I am completely at fault for.

## Confusion

For the most part, the quizzes have been fairly straight-forward. The only sort of confusion I've met have been regarding the answer choices and the given program examples.

<img src="{{site.baseurl}}/images/cbmcqwrong2.png" alt="Program Purpose question" width="600"/>

For example, in this case, answers "C" and "D" cannot be correct because they do not recognize that a copy of `numList` is being returned while `numList` itself isn't being edited. Both "A" and "B" appear to be wrong too, however: "A" is correct that `j` must be a number greater than or equal to zero, but it doesn't necessarily have to be a value less than `k` for the list swap to occur correctly (though it cannot be *equal* to k); and "B" is correct that both `j` and `k` must be less than `LENGTH(numList)` because its length is one greater than the greatest index of the list, but the values do not have to be greater than or equal to *one* (instead, it should be *zero* because of zero-based index numbering).

I ended up deciding on "A" because the question was talking about code documentation rather than how exactly the code works. Maybe the programmer wants to express that `j` should be less than `k` simply because of how the rest of the program is intended to work. This makes the comment not necessarily an incorrect statement. However, the statement made about `j` and `k` in "B" is just imprecise, as their values can be equal to zero and, if `j` and `k` were equal to each other, no swap would occur, so this range of possible index values is faulty. However, it is important to recognize that this comment specified that the two values must be less than `LENGTH(numList)`, a detail that isn't included in "A".

The answer ended up being "B" for the exact reason I explained it could have been. I likely should have recognized that "B" was arguably *more* correct with its recognition of `LENGTH(numList)`. I'm curious whether or not the coding language used in this question is zero-based, as I'm not exactly sure what it's supposed to be. Regardless, the documentation in both cases is incomplete for different reasons. It is important for the documentation in "B" to recognize as well that `j` and `k` should not be equal to each other, or else no swap will occur.

<img src="{{site.baseurl}}/images/cbmcqwrong1.png" alt="Program Purpose question" width="600"/>

This question is an honest mistake on my part. I seem to have disregarded that `DISPLAY y` would only be recognized if `y` was `True`. I'll be more careful when selecting answers next time.

# Applying Program Design and Development

This can be seen in another Notebooks post in which I plan the Work Watch project from the SCRUM Master point of view. [Link here](https://drewreed2005.github.io/realdrew/wwplanning/).