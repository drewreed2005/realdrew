---
title: Test CSS for Cafe Gato
layout: none
description: Try it out!
permalink: /sampcss
hide: true
search-exclude: true
---

<style>
    .topheader {
        width: 100%;
        height: 100px;
        font-family: Verdana, sans-serif;
        font-size: 20px;
        background: #FFB430;
        border-color: black;
        border-width: 10px;
    }
    .headlink {
        color: white;
        text-decoration-color: white;
    }
    .headlink:hover {
        text-decoration-color: #D9D9D9;
    }
    .eventbox {
        font-size: 20px;
        margin: 10px;
        background: #444444;
        border: solid 6px black;
        border-radius: 50px;
        padding: 0px 30px 16px;
        color: white;
    }
</style>

<p class="topheader">
    <table class="topheader" style="width:100%;font-size:30px">
        <tr>
            <td><a href="/cafegato/"><img src="{{site.baseurl}}/images/Studio_Project.png" width="200px"></a></td><!--ABOUT US IN HERE-->
            <td><a href="/cafegato/cats" class="headlink">Cats</a></td>
            <td><a href="/cafegato/menu" class="headlink">Menu</a></td>
            <td><a href="/cafegato/hours" class="headlink">Hours</a></td>
            <td><a href="/cafegato/events" class="headlink">Events</a></td>
            <td><a href="/cafegato/shop" class="headlink">Shop</a></td>
        </tr>
    </table>
</p>
<br>
<div class="eventbox" style="border:solid 6px #805900;background:#EDA500">
    <img src="{{site.baseurl}}/images/Studio_Project.png" width="300px" style="float:right;padding: 5px 5px 5px 5px">   
    <h1 style="color:white">9AM: Kitty Breakfast</h1>
    The cats may need to take a short break from playing with toys or sitting on high-up hammocks to eat their own breakfast. (Don't worry: we make sure they're all fed plenty!)<br><br>If you come on the weekend, the kitties will already have been fed.
</div>

