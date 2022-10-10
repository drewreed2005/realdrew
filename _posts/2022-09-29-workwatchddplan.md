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

## Work Watch Overview

To recap the program purpose and what we have so far, the Work Watch is a program that times your work session and tells you when to take breaks. More precisely, the program lets you input a set of tasks you intend to complete and the expected duration for each so that the timer can tell you how on-track you are. You can also customize how frequently you want to take breaks based on the amount of time you have to work. You can input custom suggestions for what to do during breaks, though certain particularly ideal break activities will be recommended. You can also choose whether or not you want to see the timer counting up.

The reason we want to create this is that many studies have shown that taking frequent breaks during long work sessions greatly increases the quality of your work output. During these breaks, students who feel that they don't have time to do activities like reading and exercising that supplement their learning will have the time to.

## Work Watch UML Diagram

<img src="{{site.baseurl}}/images/workwatchUMLdiagram.png" alt="Program Purpose question" width="800"/>

This diagram shows what variables will be needed/used/modified during all stages of the Work Watch program. Let's go a little more in depth.

### Work Watch Startups, Default Values and Constant Variable Checks

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

### User Inputs (Pre- and Post-Start)

A series of functions listed in "User Input (functions)" will register user inputs in place of default settings. Once the timer is initiated, they will overwrite the defaults and dictate the behavior of the timer.

Once the timer has started running, the "Pause/Play Timer," (not in UML chart but will exist) "Break Time," "Task Complete," and "End Timer" buttons will complete the corresponding functions described in the top-right box of the diagram.

### Watch End and Reflection

Keeping in mind the discrepancies between anticipated task completion times and actual completion times, anticipated break times and actual break times, and unexpected pauses and breaks, the quality and consistency of the user's work session is determined mathematically.

The more unplanned break time the user spent and the longer the duration of certain task completion sessions than anticipated, the more unproductive the session is considered. However, the opposite is also true: if the user completes a task faster than the anticipated time, takes shorter breaks or takes breaks at more distant intervals, the work session will be considered more productive. However, if too few breaks are taken, the work session may be considered relatively unhealthy.

## Frontend Wire Frame Diagram

<img src="{{site.baseurl}}/images/workwatchwireframe.png" alt="Program Purpose question" width="800"/>

Our Frontend Designer Jagger Klein created this diagram to show the UI of the Work Watch. The text of the menu options can be a bit uncertain, but the plan is to make them buttons which reveal a submenu when hovered over/clicked to edit certain settings.

The "Timer Length" block will more accurately contain a customizeable list of assignments and anticipated assignment durations. The "Customize Timer Look" will contain setting such as selecting the visibility of the timer, the color or font of notifications, break alarm tones, and the timer itself may have other looks (digital segmented numbers, clean Serif numbers, etc.). The "Time Break" menu encompasses settings regarding the intervals between breaks, the duration of breaks, and the intervals between time notifications. The "Time Points" menu encompasses the theoretical idea of creating an incentive system along with the timer where you can use points to unlock new looks or something. At the moment, this is an extra feature to be added if possible.

The "STOP" and "Start" buttons represent the "END TIMER" and "PLAY/PAUSE TIMER" buttons respectively, and the "BREAK TIME" button would normally go in the middle. The latter wasn't included because the idea for a break-specific button came about in the UML Diagramming phase, and this vision was not communicated as both assignments were created simultaneously. With these resources combined, we'll be able to create a more cohesive idea of what the UI of the program will be like.

## This Week's SCRUM Board Sub-Entry and Assignments

A link to it can be found [here](https://github.com/drewreed2005/realdrew/issues/10). Considering this the first week of work on the Work Watch, current progress has been marked and taken into account.

An overarching SCRUM Board has been created to organize these various weeks of progress into a single entity to document our work thoroughly.

The assignments for each role this week (specifically in reference to the Work Watch, not including the "Deployment" individual tasks) are also listed on this week's board. As you can see, all role-specific tasks have been completed.

>Below is a new entry to the Program Design assignment one week later.

## Create Task Requirements

For this week, we were asked to address how our program meets the College Board create task requirements.

### Project Purpose

See the [top of this page]({{site.baseurl}}/workwatchddplan/#work-watch-overview) for project purpose. In short, it's to regulate a work session by advising when to take breaks and what to do during those breaks.

### Data Abstraction and Managing Complexity

Much of the idea for this program is algebra based. When breaks will be advised is a mathematical formula (explained briefly in sections above). The timer itself runs on a while loop, turned on and off by a `True`/`False` state check.

Lists are used to organize the names and durations of a user's tasks. By `append`ing them when input, an unlimited number of entries can be created without any clutter.

### Procedural Abstraction

Procedural abstraction and data abstraction kind of go hand in hand for this program, but one more easily-defined example is the current idea for the code that makes breaks occur. The duration of a break is directly based on the either preset or custom duration of the user's break, defined as the variable `breakdur`. The break function `breaktime(duration)` includes the placeholder `duration` to be replaced with `breakdur` when run for each break.

### Algorithm Implementation

The timer itself iterates constantly, checking if it should give a special response after each iteration (break, notification, etc.).

### Testing

Since much of the program is based on user input, invalid user inputs (for example, if they input a string rather than an integer) are fully accounted for. The best way to see this is with the task creation process. If the task duration is not provided or is input as a string/decimal, it cannot be `append`ed to the list of tasks until it is an integer. If no task name is provdied, it is automatically named "Untitled Task" on the timer. Things like this show understanding of possible unintentional actions taken by the user.