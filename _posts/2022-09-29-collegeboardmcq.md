---
title: College Board Multiple Choice Quizzes
description: Showing my work and discussing confusion.
toc: true
layout: post
comments: true
hide: false
search_exlude: false
permalink: /collegeboardmcq/
---

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