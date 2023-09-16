# Hello It's Me

<style type="text/css">
.iframe_container {
	position: relative;
	padding-bottom: 56.25%; 
	padding-top: 25px;
	height: 0;
	margin-bottom: 30px;
}

.iframe_container iframe {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
</style>

<div class="iframe_container">
  <iframe allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" class="border" data-video="" src="https://www.youtube.com/embed/YQHsXMglC9A?modestbranding=0&amp;rel=0&amp;showinfo=0&amp;start=74" scrolling="no" id="iFrameResizer0" style="overflow: hidden;"></iframe>
</div>

## Problem to Solve

In a file called `hello.c`, in a folder called `me`, implement a program in C that prompts the user for their name and then says hello to that user. For instance, if the user’s name is Adele, your program should print `hello, Adele\n`!

<details>
  <summary>
    <span style="font-weight: bold;">
    Hints
    </span>
  </summary>
  <ul>
    <li>Recall that you can get a <code>string</code> from a user with <code>get_string</code>, which is declared in <code>cs50.h</code>.</li>
    <li>Recall that you can print a <code>string</code> with <code>printf</code>, which is declared in <code>stdio.h</code>.</li>
    <li>Recall that you can format a <code>string</code> with <code>printf</code> with <code>%s</code>.</li>
  </ul>
</details>

## Demo

<iframe src="https://asciinema.org/a/Jn4egWrG0Rvuzo9d2Rs0qpkcL/iframe?autoplay=1&amp;loop=1&amp;cols=80&amp;rows=12" id="asciicast-iframe-Jn4egWrG0Rvuzo9d2Rs0qpkcL" name="asciicast-iframe-Jn4egWrG0Rvuzo9d2Rs0qpkcL" scrolling="no" allowfullscreen="true" style="overflow: hidden; margin: 0px; border: 0px; display: inline-block; width: 100%; float: none; visibility: visible; height: 305px;"></iframe>

## How to Begin
Execute `cd` by itself in your terminal window. You should find that your terminal window’s prompt resembles the below:

```
$
```

Next execute

```
mkdir me
```

to make a folder called `me` in your codespace.

Then execute

```
cd me
```

to change directories into that folder. You should now see your terminal prompt as `me/ $`. You can now execute

```
code hello.c
```

to create a file called `hello.c` in which you can write your code.

## Walkthrough
Here’s a “walkthrough” (i.e., tour) of this problem, if you’d like a verbal overview of what to do too!

<div class="iframe_container">
  <iframe src="https://www.youtube.com/embed/wSk1KSDUEYA?modestbranding=1&amp;rel=0&amp;showinfo=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""> </iframe>
</div>
