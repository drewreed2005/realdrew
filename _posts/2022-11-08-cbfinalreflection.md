---
title: College Board Final Reflection
layout: post
description: How I got 100%.
toc: true
hide: false
search-exclude: false
permalink: /cbfinalreflection
---

## Overview and My Score

In this post, I will discuss all of the questions in this quiz that gave me any amount of trouble, sectioned off by either question number of subject matter.

<figure>
  <img src="{{site.baseurl}}/images/cbfinal5050.png" alt="I scored 50/50 (Source: Trust me bro)" width="900"/>
  <figcaption>I scored 50/50</figcaption>
</figure>

I ended up scoring 50/50 on the final. It was pretty easy for the most part. Below, I go over where it was and wasn't.

### Questions 1-18

These questions were all reviews from the quizzes we already took. Questions 1 through 15 were all from Big Idea 1 concepts, which were all very simple and familiar due to prior studying. Some (such as <mark>Questions 2 and 8</mark>) were ones I had previously gotten wrong, so I was pretty clear on which answers were correct and why.

(Question 8 is still a bad question, though, because it isn't stated that list indexes start at 1 in this imaginary code language.)

### Binary

Binary isn't really something we've covered in this class so far, and yet it showed up somewhat prominently in this final. <mark>Question 19</mark>, the first of multiple binary-based questions, forced me to take a quick minute to go learn how to count in binary.

<figure>
  <img src="{{site.baseurl}}/images/q19cbfinal.png" alt="CB Question 19" width="600"/>
  <figcaption>I felt like I should probably learn how to count in binary</figcaption>
</figure>

To clarify, going in, I understood the concept of bits and how different numbers of bits limit you to a certain number of variations. For example, I knew that 4 bits of binary had a maximum of 16 possible variations (0 through 15), because that's just simple math: 2<sup>4</sup> = 8. That let me figure out the answer to this question pretty easily. However, I didn't know exactly how one would count in binary.

After looking it up, I quickly figured out the pattern:

>0000 = 0, 0001 = 1, 0010 = 2, 0011 = 3, 0100 = 4, 0101 = 5, 0110 = 6, 0111 = 7, 1000 = 8, 1001 = 9, 1010 = 10, 1011 = 11, 1100 = 12, 1101 = 13, 1110 = 14, 1111 = 15. And you could continue this pattern with binary that has more than 4 bits if you wanted.Put one all the way to the right, move it to the left, add a new one on the right, and now that the ones are crowded up,put a 1 to the left of the leftmost 1 and make everything to the right of it 0.

I'm glad I figured this out for the questions that came after. Though Q20 used essentially the same knowledge as Q19 and Q21 was just part of knowing  what binary is used for (everything), <mark>Question 22</mark> would put that knowledge to the test.

<figure>
  <img src="{{site.baseurl}}/images/q22cbfinal.png" alt="CB Question 22" width="600"/>
  <figcaption>...and learning to count in binary was a fine use of time</figcaption>
</figure>

I was pretty quickly able to rule out A (3 is 0011) and D (15 is 1111). I thought about what 6 was in binary (since it was closest to 3) and came upon 0110, option B. The only one missing was option C, 9.

After a quick run through Q23 (which tested common sense), knowledge of binary once again showed its use.

<figure>
  <img src="{{site.baseurl}}/images/q24cbfinal.png" alt="CB Question 24" width="600"/>
  <figcaption>Some more binary application</figcaption>
</figure>

In this case, I had to figure out precisely what the binary represented, unlike the previous where I only had to use process of elimination. I was able to figure it out pretty easily.

### Questions 25-27

These questions asked for the proper variable type for various specific things. It was very easy to tell what the correct response is: you wouldn't make `age` a string or `isOpen` a list (assuming they mean exactly what they sound like they mean).

### Smorgasbord (and Data Abstraction)

After Q28, which was pretty much a basic algebra problem, I had a bit of confusion.

<figure>
  <img src="{{site.baseurl}}/images/q29cbfinal.png" alt="CB Question 29" width="600"/>
  <figcaption>It couldn't be D...right?</figcaption>
</figure>

<mark>Question 29</mark> was the first question that really made me second-guess myself. I don't see a world where I picked anything but A, but I did have to look for a second at D. Even though it's true that lists do allow you to hold as much data as necessary (and keep it all in one place for organization), you technically could store user input in one list for the exact same reason. Answer A was obviously better, but still.

Q30 talked about procedurally applying a function to each value of a list,Q31 talked about indexes, and Q32 brought in a new type of common question...

### Mind-Numbing "This is This Now" Questions

There are problems that define a few variables, then decide "this variable is equal to this variables" and so on. About every other question until the end of the test is one of these, and, though I'd be happy to explain my answer when prompted, there is no way I'm going over them; they're incredibly self-explanatory.

### The Remaining Questions

Many of the questions that weren't "this is this now" questions asked to provide a function to do a certain task. Q35 actually included multiple functions that would result in the same outcome in different ways through different means.

Q39 was a random index question and Q40 & Q45 was an output question, all very easy and self-explanatory. Q43 and Q44 were both math questions. The last two, Q49 and Q50, were both asking you to make something happen given two procedures, and these questions were both simple.

## Takeaways

I learned about binary. I learned that College Board's goofy language usually ues 1-based indexes. Not a lot else.