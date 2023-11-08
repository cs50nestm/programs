# Initials

{% video https://www.youtube.com/watch?v=UItYCp0Ivqg %}

## What to do?

Implement a program that, given a person’s name, prints a person’s initials, per the below.

```
$ ./initials
Name: Regulus Arcturus Black
Initials: RAB
```

## Getting Ready

First, take a self-paced tour through a few coding examples that are likely to prove quite useful to you as you work on this and some future problems in this unit, the source code for which can be found in [this sandbox](http://bit.ly/2zPo948).

Here is the first of those videos. Note: GetString() has been replaced with get_string("prompt").

{% video https://www.youtube.com/watch?v=BYbuuUntOZ4&feature=youtu.be&list=PLhQjrBD2T380sc-fXwl1sviA-twxFduVU %}

{% spoiler "More on strings" %}

{% video https://www.youtube.com/watch?list=PLhQjrBD2T380sc-fXwl1sviA-twxFduVU&time_continue=2&v=a2n7vKdRWKE %}

{% video https://www.youtube.com/watch?v=p1e_6lkMGDg&list=PLhQjrBD2T380sc-fXwl1sviA-twxFduVU&index=17 %}

{% endspoiler %}

{% video https://www.youtube.com/watch?v=sELkIJyRHWg&index=5&list=PLhQjrBD2T380sc-fXwl1sviA-twxFduVU %}

{% spoiler "More on ASCII" %}

{% video https://www.youtube.com/watch?v=ifCoAx0r3es&list=PLhQjrBD2T380sc-fXwl1sviA-twxFduVU&index=6 %}

{% endspoiler %}

{% video https://www.youtube.com/watch?v=vp3TBL4WTbc&index=7&list=PLhQjrBD2T380sc-fXwl1sviA-twxFduVU %}

{% spoiler "More on Capitalize" %}

{% video https://www.youtube.com/watch?v=h0hcz5zCBhU&list=PLhQjrBD2T380sc-fXwl1sviA-twxFduVU&index=8 %}
{% video https://www.youtube.com/watch?v=wYvnyO2PbT0&index=9&list=PLhQjrBD2T380sc-fXwl1sviA-twxFduVU %}

{% endspoiler %}

## Implementation Details

Design and implement a program, initials, that, given a person’s name, prints a person’s initials.

Implement your program in a file called initials.c.

Your program should prompt a user for their name using get_string to obtain their name as a string.

You may assume that the user’s input will contain only letters (uppercase and/or lowercase) plus single spaces between words. You don’t need to worry about names like Joseph Gordon-Levitt, Conan O’Brien, or David J. Malan!

Your program should print the user’s initials (i.e., the first letter of each word in their name) with no spaces or periods, followed by a newline (\n).

You may assume that the only spaces in the user’s input will be single spaces between words.

## Pseudocode

First, write in pseudocode.txt at right some pseudocode that implements this program, even if not (yet!) sure how to write it in code. Remember a computer cannot see the entire name at one time like a human. Your program will have to analyze the name one character at a time.

{% spoiler "Spoiler" %}

1. Start out by using get_string("Name: ") to promts a user for a name.
1. Using printf, print out "Initials: ". 
1. Print out the first character of the name as an upper case char.
1. Then iterate through the remaining characters of the string.
    1. Does the char you are looking at tell you then next char is an initial? If so, print out the next char using upper case.

{% endspoiler %}


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

{% spoiler "Hints" %}

To iterate through a string, use a for loop like this:

```c
for (int i = 0; i < strlen(s); i++)
{
    // do something
}
```

{% endspoiler %}

## How to Check

```
check50 cs50nestm/checks/2022/initials
```

To check style:

```
style50 initials.c
```

## How to Submit

No need to submit! This is a practice problem. 
