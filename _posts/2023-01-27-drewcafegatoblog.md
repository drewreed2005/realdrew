---
title: Cafe Gato - Individual College Board Content Review
layout: post
description: Describing how my portion will meet College Board requirements.
toc: true
hide: false
search-exclude: false
permalink: /individualcbplan
---

## Overview

My portion of our group project, Cafe Gato (an online marketing campaign for a hypothetical cat cafe), is an events database. A user can use a frontend endpoint to create an event (provided it passes validation requirements) and view other events read from a backend endpoint. This data can be filtered by various attributes on the frontend.

Below, I go over how I will meet the College Board expectations.

### Purpose and Function

The purpose of the program is to allow the user to get involved in their community by creating events at a local cafe. From the perspective of the cafe using the program, the purpose is to optimize and automate the process of organizing events at their cafe.

The function of the program is that the user inputs various attributes in required fields on the frontend. Those attributes are sent to a backend server, validated, and if all conditions pass, they are added to the events database. On the frontend, the user can then see all validated events and filter them by date, start time, etc.

### Data Abstraction

When date-filtered events are read from the database, the JSON data is parsed procedurally and events are ordered in a list of dictionaries by date. The list would then be called when the read table is made.

What the list will be called isn't set in stone, but it would probably be something like `chronDateList`. It contains events in index based on date.

### Managing Complexity

Using the above list of ordered dates manages complexity because the only other way to store the information would be through individual variables, which would be unpredictable and difficult to iterate efficiently considering that an unlimited number of events should be able to be stored overall.

### Procedural Abstraction

A procedure likely called `chronSort(list)` or something like that. The `list` parameter determines which list of events is sorted. This helps because it lets multiple filters be on at a time. I could have events from every day listed in exact order, or I could let the user specify a certain date/month and only sort that list once it has already been specified. Doing this allows the program to parse through less data.

### Algorithm Implementation

`chronSort` has to include some sequencing so that processes occur in the correct order. Selection will be present when the next most recent date is found and appended to the list. Iteration will be used in the process of parsing through the list in question.

### Testing

Here would be my two tests:
1. Using `chronSort` to sort a list of events from March 2023.
2. Using `chronSort` to sort a list of events from April 2023.

They would result in completely different outputs, as not only would the lists of events be different, exactly which of the events in the order of their creation are earliest should be different, so the process of iteration would end up being slightly different.

## Video Plan

I plan to show looking through the set of events on the page and messing with the filters; then moving the process of creating an event that meets the validation requirements, and refreshing the table to show it appearing; and finally making an invalid event and showing it not appearing.

If there's time (I would likely speed up the video if possible), I'd love to show the process of using the pin to update or delete a user's event.