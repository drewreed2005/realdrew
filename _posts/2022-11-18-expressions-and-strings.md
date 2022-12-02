---
keywords: fastai
description: Based on the notebooks template by Orlando, Jaden, Max and Dylan.
title: Sections 3-4 (Mathematical Epxpressions and Strings) Notes
toc: true
permalink: /sections3-4notes/
nb_path: _notebooks/2022-11-18-expressions-and-strings.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-11-18-expressions-and-strings.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="3.3-Mathematical-Expressions">3.3 Mathematical Expressions<a class="anchor-link" href="#3.3-Mathematical-Expressions"> </a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Vocabulary:-Fill-in-the-Blanks">Vocabulary: Fill in the Blanks<a class="anchor-link" href="#Vocabulary:-Fill-in-the-Blanks"> </a></h3><p>The symbol for exponent is <code>^</code></p>
<p>The symbol for addition is <code>+</code></p>
<p>The symbol for subtraction is <code>-</code></p>
<p>The symbol for multiplication is <code>*</code></p>
<p>The symbol for division is <code>/</code></p>
<p>The symbol for modulus is <code>%</code></p>
<p>An algorithm is <mark>a function with a set of rules that tells a program what to do</mark>.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Sequencing Practice: the code below does not follow the intended steps below. change the code so that it does so.</p>
<ol>
<li>Divide value1 by 10 (value1 = 5)  </li>
<li>Multiply 2 from the result of the step 1  </li>
<li>Subtract 4 from the result of the step 2</li>
<li>Print the result of step 3</li>
</ol>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="n">value1</span> <span class="o">=</span> <span class="mi">5</span>
<span class="n">value2</span> <span class="o">=</span> <span class="n">value1</span> <span class="o">/</span> <span class="mi">10</span> <span class="c1">#step 1</span>
<span class="n">value3</span> <span class="o">=</span> <span class="n">value2</span> <span class="o">*</span> <span class="mi">2</span> <span class="c1">#step 2</span>
<span class="n">value4</span> <span class="o">=</span> <span class="n">value3</span> <span class="o">-</span> <span class="mi">4</span> <span class="c1">#step 3</span>
<span class="nb">print</span><span class="p">(</span><span class="n">value4</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>-3.0
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Selection/Iteration Practice: Create a function to print ONLY the numbers of numlist that are divisble by 3.</p>
<p>Hint: use the MOD operator (a % b) to find the remainder when a is divided by b.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="n">numlist</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;3&quot;</span><span class="p">,</span><span class="s2">&quot;4&quot;</span><span class="p">,</span><span class="s2">&quot;9&quot;</span><span class="p">,</span><span class="s2">&quot;76&quot;</span><span class="p">,</span><span class="s2">&quot;891&quot;</span><span class="p">]</span>
<span class="k">for</span> <span class="n">number</span> <span class="ow">in</span> <span class="n">numlist</span><span class="p">:</span>
    <span class="k">if</span> <span class="p">(</span><span class="nb">int</span><span class="p">(</span><span class="n">number</span><span class="p">)</span> <span class="o">%</span> <span class="mi">3</span><span class="p">)</span> <span class="o">==</span> <span class="mi">0</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">number</span> <span class="o">+</span> <span class="s2">&quot; is divisible by 3&quot;</span><span class="p">)</span>
        <span class="k">continue</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="k">continue</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>3 is divisible by 3
9 is divisible by 3
891 is divisible by 3
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Homework/Binary Adaptation: Create a Python function that will convert a decimal number 1-255 to binary using mathematical operations and powers of 2. Challenge: add frontend with javascript or html.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="k">def</span> <span class="nf">convert</span><span class="p">(</span><span class="nb">input</span><span class="p">):</span>
    <span class="k">if</span> <span class="mi">0</span> <span class="o">&lt;=</span> <span class="nb">input</span> <span class="o">&lt;=</span> <span class="mi">255</span><span class="p">:</span>
        <span class="k">pass</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Invalid input.&quot;</span><span class="p">)</span>
        <span class="k">return</span>
    <span class="n">i</span> <span class="o">=</span> <span class="mi">7</span>
    <span class="n">binary</span> <span class="o">=</span> <span class="s2">&quot;&quot;</span>
    <span class="k">while</span> <span class="n">i</span> <span class="o">&gt;=</span> <span class="mi">0</span><span class="p">:</span>
        <span class="k">if</span> <span class="nb">input</span> <span class="o">%</span> <span class="p">(</span><span class="mi">2</span><span class="o">**</span><span class="n">i</span><span class="p">)</span> <span class="o">==</span> <span class="nb">input</span><span class="p">:</span>
            <span class="n">binary</span> <span class="o">+=</span> <span class="s2">&quot;0&quot;</span>
            <span class="n">i</span> <span class="o">-=</span> <span class="mi">1</span>
        <span class="k">else</span><span class="p">:</span>
            <span class="n">binary</span> <span class="o">+=</span> <span class="s2">&quot;1&quot;</span>
            <span class="nb">input</span> <span class="o">-=</span> <span class="mi">2</span><span class="o">**</span><span class="n">i</span>
            <span class="n">i</span> <span class="o">-=</span> <span class="mi">1</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">binary</span><span class="p">)</span>

<span class="n">convert</span><span class="p">(</span><span class="o">-</span><span class="mi">3</span><span class="p">)</span>
<span class="n">convert</span><span class="p">(</span><span class="mi">284</span><span class="p">)</span>
<span class="n">convert</span><span class="p">(</span><span class="mi">189</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Invalid input.
Invalid input.
10111101
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="3.4-Strings(Show-video-1)">3.4 Strings(Show video 1)<a class="anchor-link" href="#3.4-Strings(Show-video-1)"> </a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Vocab:-fill-in-the-blanks-using-the-video">Vocab: fill in the blanks using the video<a class="anchor-link" href="#Vocab:-fill-in-the-blanks-using-the-video"> </a></h3><p>Index is a number representing a position, like a character's position in a string or a string's position in a list.</p>
<p>Concatenation is <mark>combining strings</mark>.</p>
<p>Length is <mark>the amount of characters in a string</mark>.</p>
<p>A substring is <mark>individual characters of a string</mark>.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="What-is-psuedocode?">What is psuedocode?<a class="anchor-link" href="#What-is-psuedocode?"> </a></h3><p>Pseudocode is writing out a program in plain language with keywords that are used to refer to common coding concepts.</p>
<p>Can you think of some benefits of using pseudocode prior to writing out the actual code?</p>
<ol>
<li>Choose an everyday activity</li>
<li>Imagine that you are providing instructions for this activity to a person who has never done it before</li>
<li>Challenge someone to do the steps you wrote out</li>
</ol>
<p>Ex. Brushing Teeth</p>
<ol>
<li>Pick up your toothbrush</li>
<li>Rinse toothbrush</li>
<li>Pick up toothpaste</li>
<li>Place toothpaste on the toothbrush</li>
<li>Rinse toothbrush again</li>
<li>Brush teeth in a circular motion</li>
<li>Spit</li>
<li>Wash mouth </li>
<li>Rinse toothbrush</li>
<li>You have brushed your teeth!</li>
</ol>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Substring/Length-Practice">Substring/Length Practice<a class="anchor-link" href="#Substring/Length-Practice"> </a></h3><p>Change the print functions to print "hello", "bye", and the string length.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#the substring will have the characters including the index &quot;start&quot; to the character BEFORE the index &quot;end&quot;</span>
<span class="c1">#len(string) will print the length of string</span>

<span class="n">string</span> <span class="o">=</span> <span class="s2">&quot;hellobye&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="n">string</span><span class="p">[</span><span class="mi">0</span><span class="p">:</span><span class="mi">5</span><span class="p">])</span>
<span class="nb">print</span><span class="p">(</span><span class="n">string</span><span class="p">[</span><span class="mi">5</span><span class="p">:</span><span class="mi">8</span><span class="p">])</span>
<span class="nb">print</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">string</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>hello
bye
8
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Concatenation Practice: combine string1 and string2 to make string3, then print string3.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="n">string1</span> <span class="o">=</span> <span class="s2">&quot;computer&quot;</span>
<span class="n">string2</span> <span class="o">=</span> <span class="s2">&quot;science&quot;</span>
<span class="n">string3</span> <span class="o">=</span> <span class="n">string1</span> <span class="o">+</span> <span class="n">string2</span>
<span class="nb">print</span><span class="p">(</span><span class="n">string3</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>computerscience
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Homework/List Adaptation: create a function that prints the name of each string in the list and the string's length. Challenge: add frontend with javascript or html.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="n">names</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;jaden&quot;</span><span class="p">,</span><span class="s2">&quot;max&quot;</span><span class="p">,</span><span class="s2">&quot;dylan&quot;</span><span class="p">,</span><span class="s2">&quot;orlando&quot;</span><span class="p">]</span>

<span class="k">def</span> <span class="nf">length</span><span class="p">(</span><span class="nb">list</span><span class="p">):</span>
    <span class="k">for</span> <span class="n">name</span> <span class="ow">in</span> <span class="n">names</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">name</span><span class="o">.</span><span class="n">capitalize</span><span class="p">()</span> <span class="o">+</span> <span class="s2">&quot; is&quot;</span><span class="p">,</span> <span class="nb">str</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">name</span><span class="p">)),</span> <span class="s2">&quot;letters long.&quot;</span><span class="p">)</span>

<span class="n">length</span><span class="p">(</span><span class="n">names</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Jaden is 5 letters long.
Max is 3 letters long.
Dylan is 5 letters long.
Orlando is 7 letters long.
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><mark>My take on the frontend challenge</mark></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<table id="nametable">
  <!--SCRIPT DATA GOES HERE-->
</table><script>
    table = document.getElementById("nametable");
    newhtml = "";
    defaulthtml = "<tr><th>Name</th><th>Length</th></tr>";
    var namelist = ["Jaden", "Max", "Dylan", "Orlando"];
    arrayLength = namelist.length;
    for (var i = 0; i < arrayLength; i++) {
        console.log(namelist[i], namelist[i].length);
        newhtml = newhtml + "<tr><td>" + namelist[i] + "</td><td>" + String(namelist[i].length) + "</td></tr";
        table.innerHTML = defaulthtml + newhtml
    };
</script>
</div>
</div>
</div>
</div>
 
