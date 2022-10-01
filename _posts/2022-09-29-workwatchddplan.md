---
title: Work Watch Program Planning
description: Applying concepts from Program Design and Development to our Work Watch project.
toc: true
layout: post
comments: true
hide: false
search_exclude: false
categories: [work-watch]
permalink: /workwatchddplan/
---

# Work Watch Overview

To recap the program purpose and what we have so far, the Work Watch is a program that times your work session and tells you when to take breaks. More precisely, the program lets you input a set of tasks you intend to complete and the expected duration for each so that the timer can tell you how on-track you are. You can also customize how frequently you want to take breaks based on the amount of time you have to work. You can input custom suggestions for what to do during breaks, though certain particularly ideal break activities will be recommended. You can also choose whether or not you want to see the timer counting up.

The reason we want to create this is that many studies have shown that taking frequent breaks during long work sessions greatly increases the quality of your work output. During these breaks, students who feel that they don't have time to do activities like reading and exercising that supplement their learning will have the time to.

# Work Watch UML Diagram

<img src="{{site.baseurl}}/images/workwatchUMLdiagram.png" alt="Program Purpose question" width="800"/>

This diagram shows what variables will be needed/used/modified during all stages of the Work Watch program. Let's go a little more in depth.

## Work Watch Startups, Default Values and Constant Variable Checks

When the Work Watch program is first opened, the file `deltavar.py` is opened and default values completely overwrite whatever settings exist from previous uses to ensure that, once the timer has been used and stopped, it can be reset and used again.

These default values reflect the default settings provided in the diagram.

```
watchon = False
totaltime = False
secs = 0
mins = 0
showtimer = False
anames = ["Work"]
adurs = [30]
breakintv = 25
breakdur = 15
notifintv = 20
alarmtone = alarms[1] #Sound effects TBD; alarms is a list of .mp3 files
discr = [placeholder] #List of discrepancies in anticipated times, used later
```

So break time can continue to occur over continuous intervals, a variable called `ptimerstart` will take into account when the timer was last played after a periodic break. The difference between this time and the break interval will determine when breaks occur.

If the user does not change these values through means explained below, they will dictate the behavior of the timer. When the timer starts, a `while` loop will ensure that the timer is constantly going up until breaks occur (mentioned later).

The code below shows what will be done to constantly check variables throughout the timer process. The `inctotaltime()` function and its associated variables will be used to determine discrepancies in the future.

```
def inctotaltime():
    global totalsecs
    global totalmins
    totalsecs += 1
    totalmins = totalsecs / 60
    time.sleep(1)
    inctotaltime()

while totaltime == True:
    inctotaltime()

def inctime():
    global secs
    global mins
    secs += 1
    mins = secs / 60
    notifcheck() #Calculates if a notification should be provided
    breakcheck() #Calculates if it's break time
    time.sleep(1)
    inctime()

while watchon == True:
    inctime()
```

## User Inputs (Pre- and Post-Start)

A series of functions listed in "User Input (functions)" will register user inputs in place of default settings. Once the timer is initiated, they will overwrite the defaults and dictate the behavior of the timer.

Once the timer has started running, the "Pause/Play Timer," (not in UML chart but will exist) "Break Time," "Task Complete," and "End Timer" buttons will complete the corresponding functions described in the top-right box of the diagram.

## Watch End and Reflection

Keeping in mind the discrepancies between anticipated task completion times and actual completion times, anticipated break times and actual break times, and unexpected pauses and breaks, the quality and consistency of the user's work session is determined mathematically.

The more unplanned break time the user spent and the longer the duration of certain task completion sessions than anticipated, the more unproductive the session is considered. However, the opposite is also true: if the user completes a task faster than the anticipated time, takes shorter breaks or takes breaks at more distant intervals, the work session will be considered more productive. However, if too few breaks are taken, the work session may be considered relatively unhealthy.

# Frontend Wire Frame Diagram

TBD