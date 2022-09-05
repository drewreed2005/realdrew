---
title: Week 1 Review Ticket
description: A collection of tasks I've completed over Week 1 (August 22, 2022 through August 28, 2022).
toc: true
layout: post
comments: true
hide: false
search_exlude: false
---

# Summary of This Week's Goals

This week primarily covered content regarding HTML Fragments (which was largely a lesson about what goes on behind the code we make), Lists and Dictionaries, and Data Abstraction overall. There was also a bit more emphasis on collaboration after many students the week before did not indicate the ideal amount of teamwork.

# This Week's Progress

This week, the hacks tended to be less plentiful but more singularly time-consuming and difficult to understand. I went into this week with a partially-complete project that I had worked on over the weekend. It just so happens that the project has some pertenance to the "Lists and Dictionaries" part of the week's content. Let's go into that first.

## The "Survey"

After making the Python quiz, one thing that I found distinctly unsatisfying about the quiz-taking process itself was its predictability. I didn't like that I could just know the answers to the five questions and put them in immediately. I didn't like that I had to tell the quiz-taker how to format their inputs, capitalized versus lowercase or string versus integer versus float versus symbol, etc. If someone put in the wrong kind of input, it was just nonsense that didn't contribute the quiz. It felt thoroughly uninteractive and clunky.

So I got to work to fix those problems.

The "Survey" (which, spoiler, is really an eligibility test to see if you are worthy of working for or being wed to 'THE MASTER,' an unspecified being or great power) was programmed to fix these problems. It contains 15  questions to answer, ten multiple choice and five free response, each time you take it. However, a bank of 15 multiple choice questions and nine free response questions exists, meaning that which questions you get to answer each time depends somewhat on RNG. The order of these questions is also completely random. No matter when the question is asked, each response gives the same results.

Though the Python quiz was largely intended to be a lesson on `if`, `else`, math and the like, the "Survey" taught me a whole lot more abouts lists, indexes and patience. Using the `random` module and its `range` and `shuffle` commands allowed me to create a list of all possible index values of the list of MC/FR questions (without repeating numbers), shuffle them randomly, and call upon only the first ten/five list integers. This is a fool-proof strategy to randomize questions...but then I need a way to check the question response.

In order to give unique feedback based on what question was being asked, a variable known as `checkval` is globalized and set equal to the list index corresponding to each numbered question, and this `checkval` would tell the defined `mc_check()` or `fr_check()` commands how to react to the response to a given question. I was very, very proud of having come up with this.

The `retry()` function has been set to let you repeat any question if you provide an invalid response to it (detecting which question you're on with `quesval`, similar to `checkval`). If you mess up questions too many times, you will anger the survey robot until he eventually forces you to restart from the beginning upon finally finishing the survey.

There are also various Easter eggs which are hard to find without looking into the code. Doing exceptionally poor in the first five questions results in the survey-taker being repromanded. A bit more obviously, the survey robot actually messes up your name after the tenth question (which you provide to it along with your gender at the beginning), calling you by a bizarre name starting with the same letter. When correcting his mistake, if you say you have a different name than initially, the robot will question your response. Different names (including my own, give it a try) give different results after or during the survey.

(Don't feel like dealing with the 1/10 luck FR question? Just name yourself "Drew" and give some good responses!)

Again, I am very proud of this project. Writing unique responses for each input took a lot of time and effort, but it feels very worth it.

## Look Around You, Pal!

The site is a different color! Ain't that wacky.

Yeah, I followed the instructions to use "dark mode" on my site. I think altered the color hex values to suit my own preferences, since dark mode gets boring to use on every site.

I also changed the image on the home page. Why not?

## Lists and Dictionaries Notes

I found the content surrounding loops confusing and decided to mess around with them in a notes Jupyter file under the name above. Using this, I was able to create the objective Notebooks page found below.

I used a mix of Markdown and Python (like with most pages on this site) to explain what I was doing (for my own future reference). I also showed use of my own InfoDb data and various types of loops, though a much better instance of this is found in...

## Lists and Dictionaries Pair Programming

I have made a Jupyter Notebooks page along with my partner Devon to show understanding of loops and dictionaries with InfoDb. Devon used a game to show his understanding (see his Review Ticket) with a "while loop", and I used a "recursive loop" along with a system which allows the user to input their own information.

We did a portion of this during the 20 minute segments on Friday.

## Make a Table?

Here's a table using Markdown:

| Goals | Complete? | Proof |
| ----------- | ----------- |
| Lists and Dictionaries | Yes | Notes, Pair Programming, Survey |
| HTML Fragments | Yes | This Table |
| Live Review | Underway | You're looking at this table |

And here's a table using HTML:

<style type="text/css">
.myTable { width:400px;background-color:#f47;border-collapse:collapse; }
.myTable th { background-color:#a38;color:white;width:50%; }
.myTable td, .myTable th { padding:5px;border:1px solid #000; }
</style>
<table class="myTable">
<tr>
<th>Header Color</th><th>Cell Color</th>
</tr>
<tr>
<td>Purple</td><td>Pink</td>
</tr>
<tr>
<td>#a38</td><td>#f47</td>
</tr>
</table>

I used `<style>` to establish some colors I'd like to be in my table. I tried changing the border color as well but it ended up looking ugly. I think this looks nice with my mostly purple website.

# List of Objectives Met

- Changed website "theme" or colors with `_sass`
- Home screen customization
- Survey making use of lists, indexes, and past content like `if` and `def`
- Lists and Dictionaries notes with all types of loops used
- Pair programming: at least 2 `InfoDb` entries between me and Devon
- All Jupyter Notebooks pages with use a mix of Markdown and Python cells
- Use of `#` in cells to add commentary
- Customized table(s)
- Verify tools with Bash
- This Review Ticket and live presentation

And, of course, our table has submitted all Review Tickets in one comment.