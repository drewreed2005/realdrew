---
title: Story Demo
layout: none
description: test story layout on local
toc: true
hide: true
search-exclude: true
permalink: /cstory
---

<style>
    .big_daddy {
    max-width: 100%;
    max-height: 100vh;
    height: auto;
    justify-content: center;
    }

    .game_border {
    display: flex;
    height: 1080px;
    width: 1920px;
    background-color: black;
    }

    .left_bar {
    display:flex;
    flex-direction:column;
    height: 1080px;
    width: 420px;
    background-color: gray;
    }

    .image_border {
    display:flex;
    justify-content:center;
    text-align:center;
    flex-direction:column;
    height: 1080px;
    width: 1080px;
    background-color: brown;
    }

    .game_image {
    display: flex;
    position: absolute;
    height: 930px;
    width: 930px;
    margin: 0px 0px 0px 75px;
    justify-content: center;
    background-image: url('https://i0.wp.com/voiceofsandiego.org/wp-content/uploads/2021/05/1FEE4EE4-D1EC-4C38-A8FB-A19800E2C787-72404-000022779096391B-800x533-1.jpg?fit=800%2C533&ssl=1');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    background-color: black;
    }

    .right_bar {
    display:flex;
    flex-direction:column;
    height: 1080px;
    width: 420px;
    background-color: gray;
    }

    .top_creature {
    display: flex;
    height: 33%;
    margin: 20px;
    background-image: url('');
    justify-content: center;
    background-color: red;
    }
    .mid_creature {
    display: flex;
    height: 33%;
    margin: 20px;
    background-image: url('');
    justify-content: center;
    background-color: orange;
    }
    .btm_creature {
    display: flex;
    height: 33%;
    margin: 20px;
    background-image: url('');
    justify-content: center;
    background-color: yellow;
    }

    .scene_tbox {
    display: flex;
    position: absolute;
    height: 150px;
    width: 700px;
    justify-content: center;
    justify-items: center;
    background-image: url('https://static.vecteezy.com/system/resources/previews/009/302/650/original/white-cloud-clipart-design-illustration-free-png.png');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    }

    .scene_tbox_text {
    position: relative;
    padding: 6% 3% 0% 3%;
    font-family: 'Verdana';
    text-align: left;
    justify-content: center;
    font-size: 20px;
    width: 500px;
    height: 100px;
    }

    .left_portrait {
        position: relative;
        display: flex;
        height: 50%;
        background-image: url('');
        justify-content: center;
        background-color: green;
    }

    .right_portrait {
        position: relative;
        display: flex;
        height: 50%;
        background-image: url('');
        justify-content: center;
        background-color: blue;
    }

    .left_text {
        position: relative;
        display: flex;
        height: 50%;
        background-image: url('');
        justify-content: center;
        background-color: orange;
    }

    .right_text {
        position: relative;
        display: flex;
        height: 50%;
        background-image: url('');
        justify-content: center;
        background-color: purple;
    }
</style>

<div class="big_daddy">
  <div class="game_border">
    <div class="left_bar" id="left_bar">
      <div class="left_text">
        left text
      </div>
      <div class="left_portrait">
        left portrait
      </div>
    </div>
    <div class="image_border" id="image_border">
      <div class="game_image" id="game_image">
        game image
        <div class="scene_tbox" id="scene_tbox" style="opacity:0;top:90%">
          <div class="scene_tbox_text" id="scene_tbox_text">
            This is a test to see how far the text in this box goes. I just want to see how much I can fit before I have to make a new line. (CUTOFF)
          </div>
        </div>
      </div>
    </div>
    <div class="right_bar" id="right_bar">
      <div class="right_text">
        right text
      </div>
      <div class="right_portrait">
        right portrait
      </div>
    </div>
  </div>
  <button onclick="scene_box_in()">scene_box_in</button><button onclick="scene_box_out()">scene_box_out</button>
</div>

<script>
    let scene_tbox = document.getElementById("scene_tbox");

    function scene_box_in() {
    console.log("box in");
    scene_tbox.style["opacity"] = "0";
    scene_tbox.style["top"] = "85%";
    var opval = 0;
    var posval = 85;
    let i = 0;
    var anim_scene_tbox_up = setInterval(function() {
        opval = opval + i;
        if (scene_tbox.style["top"] != "80%") {
        posval = posval - 0.25;
        };
        scene_tbox.style["opacity"] = String(opval);
        scene_tbox.style["top"] = String(posval) + "%";
        i = i + 0.01
        if (posval <= 80) {
            scene_tbox.style["opacity"] = "1";
            scene_tbox.style["top"] = "80%";
            clearInterval(anim_scene_tbox_up);
            console.log('stop');
            };
        }, 15);
    }

    function scene_box_out() {
    console.log("box out");
    scene_tbox.style["opacity"] = "1";
    scene_tbox.style["top"] = "80%";
    var opval = 1;
    let i = 0;
    var anim_scene_tbox_down = setInterval(function() {
        opval = opval - i;
        scene_tbox.style["opacity"] = String(opval);
        i = i + 0.01;
        if (opval <= 0) {
            scene_tbox.style["opacity"] = "0%";
            scene_tbox.style["top"] = "85%";
            clearInterval(anim_scene_tbox_down);
            console.log('stop')
            };
        }, 15);
    }
</script>