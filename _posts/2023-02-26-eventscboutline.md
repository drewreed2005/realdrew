---
title: Cafe Gato Events - College Board Outline
layout: post
description: Describing how my projects meets College Board requirements.
toc: true
hide: false
search-exclude: false
permalink: /eventscboutline
---

## Overview

My portion of our group project, Cafe Gato (an online marketing campaign for a hypothetical cat cafe), is an events database. A user can use a frontend endpoint to create an event (provided it passes validation requirements) and view other events read from a backend endpoint. This data can be filtered by various attributes on the frontend.

### Purpose and Function

The purpose of the program is to promote community interaction and cat cafe business consistency through user-created events hosted by the cat cafe. Another purpose of the program is to aid a given cat cafe business in validating and organizing the events that will be hosted at their location.

The function of the program is to add user-created events to a cat cafe-hosted database, with validation requirements built into the input to ensure all events in the system are valid. Other functions include allowing users or administrators to delete events for any reason and allowing interested customers to look at and sort future events so that they can possibly attend one.

#### Input and Output

The input of the program is various written event attributes in the form of text inputs on the frontend. The output is the alert which either points out an error in the attributes or expresses that the event has been added to the database. The event's presence itself within the database is also an output.

### Data Abstraction

<figure>
  <img src="{{site.baseurl}}/images/sortedlistcreated1.png" alt="Code segment shows list being formed" width="600"/>
</figure>

The list `sorted_List` is shown being formed based on the values of the sort input windows. In order either soonest to latest or latest to soonest (based on the frontend input windows), events are pushed to `sorted_List`.

<figure>
  <img src="{{site.baseurl}}/images/sortedlistcreated2.png" alt="Code segment shows list being finished and used" width="600"/>
</figure>

The list `sorted_List` is shown being finished here and, at the end, the list is used as a reference for the formation of the `final_List` variable, which is formed with only entries from the given month.

The `sorted_List` variable represents a list of events organized either soonest to latest or latest to soonest, depending on the input values.

#### Importance

The data within this list, including its index order, is important because its organization is then translated to the `final_List` variable which selectively carries over values from it. Without this specific list, the data would be very difficult to order correctly.

In terms of purpose, this list allows users to see events in date order, meaning that users in the community can more easily see which events they may go to.

### Managing Complexity

This list helps the programs because it allows the program to take advantage of the way that indexes can represent a chronological organization of data. That chronological organization means that, with just a basic for loop which increments the index value of `i` by one, adding to the `final_List` list variable with the `push` function allows it to remain in in chronological order despite removing specific entries.

### Procedural Abstraction

```
    function table_Make(list) {
        table.innerHTML = "";
        list.forEach(user => {
                // build a row for each user
                const tr = document.createElement("tr");

                // td's to build out each column of data
                const name = document.createElement("td");
                const email = document.createElement("td");
                const event_name = document.createElement("td");
                const event_details = document.createElement("td");
                const date = document.createElement("td");
                const start_time = document.createElement("td");
                const end_time = document.createElement("td");
                    
                // filter times
                var temp_stime = user.start_time;
                var temp_etime = user.end_time;
                if (Number(temp_stime.substring(0, 2)) > 12) {
                    var temp_shr = Number(temp_stime.substring(0, 2)) - 12;
                    var new_stime = String(temp_shr) + temp_stime.substring(2, 5) + " PM";
                } else {
                    var new_stime = temp_stime + " AM"
                }
                if (Number(temp_etime.substring(0, 2)) > 12) {
                    var temp_ehr = Number(temp_etime.substring(0, 2)) - 12;
                    var new_etime = String(temp_ehr) + temp_etime.substring(2, 5) + " PM";
                } else {
                    var new_etime = temp_etime + " AM"
                }

                // add content from user data          
                name.innerHTML = user.name; 
                email.innerHTML = user.email; 
                event_name.innerHTML = user.event_name; 
                event_details.innerHTML = user.event_details;
                date.innerHTML = user.date; 
                start_time.innerHTML = new_stime; 
                end_time.innerHTML = new_etime;

                // add data to row
                tr.appendChild(name);
                tr.appendChild(email);
                tr.appendChild(event_name);
                tr.appendChild(event_details);
                tr.appendChild(date);
                tr.appendChild(start_time);
                tr.appendChild(end_time);

                // add row to table
                table.appendChild(tr);
        });
    };
```

This code shows the algorithm behind the function `table_Make`.

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-02-26 at 6.22.43 PM.png" alt="table_Make function being called" width="600"/>
</figure>

This code shows the `table_Make` function being called by the `create_Table` function.

This function contributes to the program by allowing it to express the database data in a table that is easy for a user to understand. It converts the traditional military time format that the database uses to standard AM/PM time. Its use of the parameter `list` allows the function to be used to display both the default data set of the database and a sorted version of it.

### Algorithm Implementation

This function starts by emptying the table to make sure that new data is not added on top of the old data. A `forEach` function is then used to iterate through every event dictionary provided in the list (which is the parameter). All of the rows are first created under descriptive variables. Then, the start time and end time are selected if the hour is expressed as a number greater than 12 and converted to a PM time. If not, `" AM"` is simply concatenated to the back of a replacement variable for both the start time and the end time. These replacement variables, which are created regardless of whether or not the time is selected, are then defined as the `innerHTML` of the start and end time rows respectively. The other rows have their `innerHTML` defined as the corresponding variables shown in the dictionaries. These columns of information are appended into a row, and that row is then appended to a table that collects all of it.

Iteration is used when iterating through the events in the event parameter using the `forEach` function.

Selection is used with an `if` statement that defines a replacement "PM" time for military times with hours expressed as numbers greater than 13.

Sequencing is used to ensure that all used variables are defined before being called. The columns are also filled in in order before being appended to the rows, and the rows are fully filled in before being appended to the table.

### Testing

In this section, I test this table creation function function.

#### Test Conditions

The first call of `table_Make` has the parameter `list` expressed as the following:

```
[
    {
        "date": "03/01/2023",
        "email": "lucky@magic.com",
        "end_time": "15:00",
        "event_details": "This is the month that St. Patrick's Day takes place, so we're celebrating.",
        "event_name": "Beginning of March Celebration",
        "name": "Lucky Leprechaun",
        "start_time": "13:00"
    },
    {
        "date": "03/07/2023",
        "email": "downer@icloud.com",
        "end_time": "13:45",
        "event_details": "We're gonna break it down!",
        "event_name": "The Down Breaker Clowns",
        "name": "Breaker Downer",
        "start_time": "12:37"
    },
    {
        "date": "03/13/2023",
        "email": "fixer@icloud.com",
        "end_time": "13:00",
        "event_details": "We're gonna fix it!",
        "event_name": "The Fix Mix Flicks",
        "name": "Fixer Upper",
        "start_time": "11:50"
    }
]
```

As you can see, the events are listed in chronological order from soonest to latest.

The second test defines the parameter as the following:

```
[
    {
        "date": "03/13/2023",
        "email": "fixer@icloud.com",
        "end_time": "13:00",
        "event_details": "We're gonna fix it!",
        "event_name": "The Fix Mix Flicks",
        "name": "Fixer Upper",
        "start_time": "11:50"
    },
    {
        "date": "03/01/2023",
        "email": "lucky@magic.com",
        "end_time": "15:00",
        "event_details": "This is the month that St. Patrick's Day takes place, so we're celebrating.",
        "event_name": "Beginning of March Celebration",
        "name": "Lucky Leprechaun",
        "start_time": "13:00"
    },
    {
        "date": "03/07/2023",
        "email": "downer@icloud.com",
        "end_time": "13:45",
        "event_details": "We're gonna break it down!",
        "event_name": "The Down Breaker Clowns",
        "name": "Breaker Downer",
        "start_time": "12:37"
    }
]
```

#### Test Outputs

The outputs of the tests produce different tables.

##### Test 1

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-02-26 at 7.44.38 PM.png" alt="table_Make function being called" width="600"/>
</figure>

##### Test 2

<figure>
  <img src="{{site.baseurl}}/images/Screen Shot 2023-02-26 at 7.43.11 PM.png" alt="table_Make function being called" width="600"/>
</figure>