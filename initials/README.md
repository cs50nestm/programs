# Initials

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
  <iframe src="https://www.youtube.com/watch?v=UItYCp0Ivqg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


## What to do?

Implement a program that, given a person’s name, prints a person’s initials, per the below.

```
$ ./initials
Name: Regulus Arcturus Black
Initials: RAB
```

## Getting Ready

First, take a look at the section of the Unit 2 Lecture Video where we learn more about how to use strings.

<div class="iframe_container">
  <iframe src="https://video.cs50.io/XmYnsO7iSI8?screen=5YGV1hcM_MY&start=5618" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


## Implementation Details

Design and implement a program, initials, that, given a person’s name, prints a person’s initials.

Implement your program in a file called initials.c.

Your program should prompt a user for their name using get_string to obtain their name as a string.

You may assume that the user’s input will contain only letters (uppercase and/or lowercase) plus single spaces between words. You don’t need to worry about names like Joseph Gordon-Levitt, Conan O’Brien, or David J. Malan!

Your program should print the user’s initials (i.e., the first letter of each word in their name) with no spaces or periods, followed by a newline (\n).

You may assume that the only spaces in the user’s input will be single spaces between words.

## Pseudocode

First, write in pseudocode.txt at right some pseudocode that implements this program, even if not (yet!) sure how to write it in code. Remember a computer cannot see the entire name at one time like a human. Your program will have to analyze the name one character at a time.

<details>
  <summary>
    <span style="font-weight: bold;">
    Write some code that you know will compile
    </span>
  </summary>
<br>

1. Start out by using <code>get_string("Name: ")</code> to promts a user for a name.
1. Using printf, print out "Initials: ". 
1. Print out the first character of the name as an upper case char. You might find the function <code>toupper</code> in <code>ctype.h</code> helpful.
1. Then iterate through the remaining characters of the string.
    1. Does the char you are looking at tell you then next char is an initial? If so, print out the next char using upper case.

</details>


## Usage

Your program should behave per the examples below. 

```
$ ./initials
Name: Zamyla Chan
Initials: ZC
```

```
$ ./initials
Name: robert thomas bowden
Initials: RTB
```


details>
  <summary>
    <span style="font-weight: bold;">
    Write some code that you know will compile
    </span>
  </summary>
<br>

To iterate through a string, use a for loop like this:

<code>for (int i = 0; i < strlen(s); i++)</code>

</details>







## How to Check

```
check50 cs50nestm/checks/2022/initials
```

To check style:

```
style50 initials.c
```

## How to Submit

```
submit50 cs50nestm/checks/2022/initials
```
