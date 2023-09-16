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

Log into [cs50.dev](https://cs50.dev) using your GitHub account. Once your “codespace” loads, you should see that it is divided into three regions. Toward the top is your “text editor”, where you’ll write all of your programs. Toward the bottom of is a “terminal window”, a command-line interface (CLI) that allows you to explore your codespace’s files and directories (aka folders), compile code, and run programs. And on the left is your file “explorer,” a graphical user interface (GUI) via which you can also explore your codespace’s files and directories.

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
  <iframe src="https://www.youtube.com/embed/wSk1KSDUEYA?modestbranding=1&amp;rel=0&amp;showinfo=0&amp" frameborder="0" allow="accelerometer; autoplay; showinfo=0; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""> </iframe>
</div>

<details>
  <summary>
    <span style="font-weight: bold;">
    More Hints
    </span>
  </summary>
  <ul>
    <li>Don’t recall how to prompt the user for their name?<br>
Recall that you can use <code>get_string</code> as follows, storing its return value in a variable called name of type <code>string</code>.<br>
    <code>string name = get_string("What's your name? ");</code></li>
    <li>Recall that you can print a <code>string</code> with <code>printf</code>, which is declared in <code>stdio.h</code>.</li>
    <li>Recall that you can format a <code>string</code> with <code>printf</code> with <code>%s</code>.</li>
  </ul>
</details>

Hints
Don’t recall how to prompt the user for their name?
Recall that you can use get_string as follows, storing its return value in a variable called name of type string.

string name = get_string("What's your name? ");

Don’t recall how to format a string?
Don’t recall how to join (i.e., concatenate) the user’s name with a greeting? Recall that you can use printf not only to print but to format a string (hence, the f in printf), a la the below, wherein name is a string.

printf("hello, %s\n", name);
Use of undeclared identifier?
Seeing the below, perhaps atop other errors?

error: use of undeclared identifier 'string'; did you mean 'stdin'?
Recall that, to use get_string, you need to include cs50.h (in which get_string is declared) atop a file, as with:

#include <cs50.h>


## How to Test Your Code
Execute the below to evaluate the correctness of your code using check50, a command-line program that will output happy faces whenever your code passes CS50’s automated tests and sad faces whenever it doesn’t! But be sure to compile and test it yourself as well!

```
check50 cs50/problems/2023/x/hello
```

Execute the below to evaluate the style of your code using `style50`, a command-line program that will output additions (in green) and deletions (in red) that you should make to your program in order to improve its style. If you have trouble seeing those colors, `style50` supports other modes too!

```
style50 hello.c
```

## How to Submit
In your terminal, execute the below to submit your work.

```
submit50 cs50/problems/2023/x/hello
```

You can then go to `submit.cs50.io` to see that your program submitted properly, as well as check your correctness and style scores. You may resubmit as many times as you like before the deadline.
