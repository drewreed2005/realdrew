---
title: Binary Math
layout: base
description: A Binary Math illustrative application using HTML, Liquid, and JavaScript.
permalink: /frontend/binary
categories: [3.B, 3.C, C4.4]
---

<!-- Hack 1: add a character display to text when 8 bits, determine if printable or not printable -->
<!-- Hack 2: change to 24 bits and add a color code and display color when 24 bits, think about display on this one -->
<!-- Hack 3: do your own thing -->

{% assign BITS = 24 %}

<div class="container bg-primary">
    <header class="pb-3 mb-4 border-bottom border-primary text-dark">
        <span class="fs-4">Binary Math with Conversions</span>
    </header>
    <div class="row justify-content-md-center">
        <div class="col-8">
            <table class="table">
            <tr id="table">
                <th>Plus</th>
                <th>Binary</th>
                <th>Octal</th>
                <th>Hexadecimal</th>
                <th>Decimal</th>
                <th>Color</th>
                <th>Minus</th>
            </tr>
            <tr>
                <td><button type="button" id="add1" onclick="add(1)">+1</button></td>
                <td id="binary">00000000</td>
                <td id="octal">0</td>
                <td id="hexadecimal">0</td>
                <td id="decimal">0</td>
                <td id="color" style="font-size:100px;padding:0px">▣</td> 
                <td><button type="button" id="sub1" onclick="add(-1)">-1</button></td>
            </tr>
            </table>
        </div>
        <div class="col-12">
            {% comment %}Liquid for loop includes last number, thus the Minus{% endcomment %}
            {% assign bits = BITS | minus: 1 %} 
            <table class="table">
            <tr>
                {% comment %}Build many bits{% endcomment %}
                {% for i in (0..bits) %}
                <td><img class="img-responsive py-3" id="bulb{{ i }}" src="{{site.baseurl}}/images/bulb_off.png" alt="" width="40" height="Auto">
                    <button type="button" id="butt{{ i }}" onclick="javascript:toggleBit({{ i }})">Turn on</button>
                </td>
                {% endfor %}
            </tr>
            <tr>
                {% comment %}Value of bit{% endcomment %}
                {% for i in (0..bits) %}
                <td><input type='text' id="digit{{ i }}" Value="0" size="1" readonly></td>
                {% endfor %}
            </tr>
            <tr id="newfunction">
                <td>8388608</td><td>4194304</td><td>2097152</td><td>1048576</td><td>524288</td><td>262144</td><td>131072</td><td>65536</td><td>32768</td><td>16384</td><td>8192</td><td>4096</td><td>2048</td><td>1024</td><td>512</td><td>256</td><td>128</td><td>64</td><td>32</td><td>16</td><td>8</td><td>4</td><td>2</td><td>1</td>
            </tr>
            </table>
        </div>
    </div>
</div>

<script>
    const BITS = {{ BITS }};
    const MAX = 2 ** BITS - 1;
    const MSG_ON = "Turn on";
    const IMAGE_ON = "{{site.baseurl}}/images/bulb_on.gif";
    const MSG_OFF = "Turn off";
    const IMAGE_OFF = "{{site.baseurl}}/images/bulb_off.png"

    // script below used to create the rows below
    // var rowmax = 8388608;
    // var colhtml = "<td>" + String(rowmax) + "</td>";
    // function createCol() {
        // if(rowmax > 1) {
            // console.log(rowmax);
            // rowmax = (rowmax / 2);
            // colhtml = colhtml + "<td>" + String(rowmax) + "</td>";
            // createCol();
        // } else {
            // console.log(colhtml);
            // document.getElementById('newfunction').innerhtml = colhtml;
        // };
    // };
    // createCol();

    // return string with current value of each bit
    function getBits() {
        let bits = "";
        for(let i = 0; i < BITS; i++) {
        bits = bits + document.getElementById('digit' + i).value;
        }
        return bits;
    }
    // setter for DOM values
    function setConversions(binary) {
        document.getElementById('binary').innerHTML = binary;
        // Octal conversion
        document.getElementById('octal').innerHTML = parseInt(binary, 2).toString(8);
        // Hexadecimal conversion
        hexval = parseInt(binary, 2).toString(16);
        document.getElementById('hexadecimal').innerHTML = hexval;
        // Decimal conversion
        document.getElementById('decimal').innerHTML = parseInt(binary, 2).toString();
        // Color conversion
        document.getElementById('color').style.color = "#" + String(hexval);
    }
    //
    function decimal_2_base(decimal, base) {
        let conversion = "";
        // loop to convert to base
        do {
        let digit = decimal % base;
        conversion = "" + digit + conversion; // what does this do?
        decimal = ~~(decimal / base);         // what does this do?
        } while (decimal > 0);                  // why while at the end? what is ~~?
        // loop to pad with zeros
        if (base === 2) {                        // only pad for binary conversions
        for (let i = 0; conversion.length < BITS; i++) {
            conversion = "0" + conversion;
        }
        }
        return conversion;
    }

    // toggle selected bit and recalculate
    function toggleBit(i) {
        //alert("Digit action: " + i );
        const dig = document.getElementById('digit' + i);
        const image = document.getElementById('bulb' + i);
        const butt = document.getElementById('butt' + i);
        // Change digit and visual
        if (image.src.match(IMAGE_ON)) {
        dig.value = 0;
        image.src = IMAGE_OFF;
        butt.innerHTML = MSG_ON;
        } else {
        dig.value = 1;
        image.src = IMAGE_ON;
        butt.innerHTML = MSG_OFF;
        }
        // Binary numbers
        const binary = getBits();
        setConversions(binary);
    }
    // add is positive integer, subtract is negative integer
    function add(n) {
        let binary = getBits();
        // convert to decimal and do math
        let decimal = parseInt(binary, 2);
        if (n > 0) {  // PLUS
        decimal = MAX === decimal ? 0 : decimal += n; // OVERFLOW or PLUS
        } else  {     // MINUS
        decimal = 0 === decimal ? MAX : decimal += n; // OVERFLOW or MINUS
        }
        // convert the result back to binary
        binary = decimal_2_base(decimal, 2);
        // update conversions
        setConversions(binary);
        // update bits
        for (let i = 0; i < binary.length; i++) {
        let digit = binary.substr(i, 1);
        document.getElementById('digit' + i).value = digit;
        if (digit === "1") {
            document.getElementById('bulb' + i).src = IMAGE_ON;
            document.getElementById('butt' + i).innerHTML = MSG_OFF;
        } else {
            document.getElementById('bulb' + i).src = IMAGE_OFF;
            document.getElementById('butt' + i).innerHTML = MSG_ON;
        }
        }
    }
</script>
