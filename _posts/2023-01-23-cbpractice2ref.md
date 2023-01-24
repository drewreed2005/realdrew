---
title: College Board MCQ Test 2 Reflection
layout: post
description: A reflection on the second College Board MCQ test.
toc: true
hide: false
search-exclude: false
permalink: /mcqtest2reflection
---

## Results

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 8.29.39 PM.png" alt="Results: 50/50" width="900"/>
  <figcaption>I got 50/50.</figcaption>
</figure>

I feel that I have very noticeably improved since the last MCQ Test. I didn't need to look up any of the problems at all, aside from one or two double-checks if there was another answer that I felt may have been partially correct.

## Problems I Struggled With

Here are some problems that didn't necessarily stump me or challenge me all that much critically, but made me stop and think throughout the quiz.

### Question 1

It may have been because it was just the first problem, but Q1 had me stumped for a minute.

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 8.37.20 PM.png" alt="CB Q1" width="600"/>
  <figcaption>I understand it now, but it took me a second.</figcaption>
</figure>

My brain kind of auto-corrected the sequence in the code to `IF` -> `ELIF` -> `ELSE` rather than the erroneous `IF` -> <mark>`IF`</mark> -> `ELSE` structure. After a certain point, I figured that the error must come from that strange structural choice, and I was able to figure it out from there.

### Question 13

This was another one that I didn't have trouble understanding, but still almost tricked me because I wasn't paying attention.
 
<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 10.11.05 PM.png" alt="CB Q13" width="600"/>
  <figcaption>I almost missed the third option.</figcaption>
</figure>

I hadn't considered formatting the statements the way the III. option does, so it almost slipped my mind.

### Robot Questions

I felt the same way about pretty much all of the problems involving robot simulations: they weren't hard, but they took a while for me to figure out and answer.

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 10.19.21 PM.png" alt="CB Q13" width="600"/>
  <figcaption>This one is a good example of an easier one.</figcaption>
</figure>

From this, I was able to tell that the problem would arise at a fork where the robot would have to turn left but would instead turn right due to sequencing.

Many of the other problems, however, weren't as easy to solve because they essentially required you to analyze every answer. This wasn't necessary incredibly difficult, but it could be time-consuming and tedious

### Question 22

It took a lot of reading to understand this one.

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 10.19.21 PM.png" alt="CB Q22" width="600"/>
  <figcaption>This one was just confusing.</figcaption>
</figure>

I was talking to my friend about it for a while during class and we disagreed until I managed to prove that Algorithm B worked. Eventually, we figured it out.

### Question 30

This one was a mix of being a bit complex with a graph to look at, and a bit tedious because I had to verify through all of the possible answers for *two* correct ones.

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 10.29.57 PM.png" alt="CB Q30" width="600"/>
  <figcaption>For some reason, the graph made it seem more complicated.</figcaption>
</figure>

I kept forgetting that the coordinate represented the midpoint.

### Question 34

I really didn't know what to put for this one when I first read it.

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 10.33.39 PM.png" alt="CB Q34" width="600"/>
  <figcaption>We didn't really learn a specific number/fraction.</figcaption>
</figure>

I picked my answer mainly because a number 50 or higher felt like too much searching. This is one I ended up double-checking with Google just to be sure, but I'm glad I managed to figure it out on my own first.

### Question 45

I really don't have justification as to why I struggled with it. It was just a lot of similar words mixed with my kind of rusty knowledge of what "heuristic" meant.

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 10.39.40 PM.png" alt="CB Q45" width="600"/>
  <figcaption>My brain just struggled to put this one together.</figcaption>
</figure>

### Question 50

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-01-23 at 10.43.04 PM.png" alt="CB Q50" width="600"/>
  <figcaption>My brain just struggled to put this one together.</figcaption>
</figure>

I might have been a bit burned out after doing the whole MCQ, but it took a second for how counting with hexidecimal would work.

I eventually realized each of the leftmost digits could be multiplied by 16 instead of 10 to account for 16-base counting, and the 6 could stay the same. 5 times 16 is a nice, even 80, and plus six is 86, translating to "V". Just to be sure, I quickly Googled this one at the end to double-check. I didn't want to be let down at the end by my own burnout.

## Overall Reflection

Here are some things to remember from what I struggled with on this MCQ:

- If a problem makes it clear that one of the answer choices creates an error of some sort, take a look at the procedure's formatting. If the formatting seems super alient in certain parts, chances are it's where the error is.
- On problems with a set of possibly correct answers are provided, and you can choose as many as you want as the correct anwser make *sure* to check every single option.
- Remember "heuristic": it's an approach that sacrifices the perfection of the output for ease of programming in a situation where making a perfect procedure to solve the problem would be impossible or require too much effort.
- With hexidecimal, every single "tens" digit character is worth 16, so just multiply that number by 16 when converting two-bit into decimal.