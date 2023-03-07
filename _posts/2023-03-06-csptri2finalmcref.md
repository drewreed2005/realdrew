---
title: Trimester 2 Final College Board MC Reflection
layout: post
description: A reflection on the final trimester 2 College Board MCQ test.
toc: true
hide: false
search-exclude: false
permalink: /mcqfinaltri2reflection
---

## Results

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-03-06 at 12.50.59 PM.png" alt="Results: 48/50" width="900"/>
  <figcaption>I got 48/50.</figcaption>
</figure>

This is the first time I've gotten questions wrong on these College Board tests, and also the one I struggled with the most.

## Problems I Got Wrong

Here are the two problems that I got wrong, both for different reasons.

### Question 28

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-03-06 at 1.06.38 PM.png" alt="Problem 28" width="650"/>
  <figcaption>JavaScript's "substring" procedure messed me up.</figcaption>
</figure>

As with many problems that I have faced in this class, I am blaming the fact that I got the answer wrong on JavaScript. I'm kind of kidding, but only kind of.

Though I did read the `substring` procedure call in the table, when I was looking at it, I was still considering the last parameter the index-based endpoint of the substring rather than the length of the segment taken. That's how it works with the innate JavaScript `substring`/`substr` function. As a result, I thought that any code with `len(oldString) - 4` as a parameter would then be incorrect since the endpoint should be two substring characters away from the end, not four.

### Question 49

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-03-06 at 1.15.34 PM.png" alt="Problem 49" width="650"/>
  <figcaption>This feels like a trick question.</figcaption>
</figure>

I picked option D mainly because it felt most in line with the wording of "limitation." It's a bit of a trick that observations need to be made before "running" the simulation; obviously that's not true, but I understood that option to mean something closer to "Many observations must be made in order to create and use a useful simulation." Since the question set up the urban conditions and the complicated nature of the situation, I had assumed the observations would be a limitation.

At the same time, I knew that B was also technically a correct answer, and I've answered that exact option on multiple simulation questions before this. It just felt too general for the given situation and made me not want to click it.

## Problems I Struggled With

Here are some problems that I had trouble with, many of which I ended up looking up to be sure of my answer. I still haven't had to look up a question before selecting an answer yet, but I got closer this time than ever before.

### Question 8

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-03-06 at 1.27.12 PM.png" alt="Problem 8" width="650"/>
  <figcaption>My knowledge of Unit 5 falters here.</figcaption>
</figure>

My answer to this question was driven by the smallest shreds of remaining information in my brain about this unit. This is one that I definitely had to look up before I was willing to submit it, and I'm surprised my initial answer was correct.

A digital certificate is also called a public key certificate. This knowledge alone will prevent me from making this same mistake again.

### Question 29

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-03-07 at 2.37.48 PM.png" alt="Problem 29" width="650"/>
  <figcaption>Struggling to read the long set of Boolean.</figcaption>
</figure>

I've never seen a set of nested Boolean expressions that contain `AND`, `OR`, AND `NOT`, so I was having trouble telling what would take precedent. I eventually figured out that `a OR b` would be `true` because `b` is true, and since `c` is true, `b AND c` becomes `true`, and the `NOT` makes it `false`. Just an overall strange piece of code, but I think I can understand it better now.

## Overall Reflection

Here are some things to remember from what I struggled with on this MCQ:

- All the stuff about privacy and security from Big Idea 5 (cookies and keys especially)