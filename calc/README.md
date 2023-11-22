# Calc

## tl;dr

Implement a program that implements a command line calculator.

```
$ ./calc 50 x 28
1400.000000
```

## Divide and Conquer
In this problem, you will be tasked with implementing a very simple command-line based calculator program. Your program will accept inputs like this, and output the result as a float:

```
$ ./calc 4 + 5
9.000000
```

or, indeed like this (allowing the user to perform some basic floating-point arithmetic)

```
$ ./calc 8.38 - 5.12
3.260000
```
such that the user can perform all five of the basic math operations that C permits — addition, subtraction, multiplication, division, and modulo.

Notice that unlike many other programs you’ve likely written up to this point, and just like Old Friends, users are not entering any information after the program has started running. Rather, they are providing all of their input to the program at the command line, before the program has begun.

## Implementation Details

Recall that if we collect information from the user at the command line, we can use two special parameters passed into `main` (conventionally called `argc` and `argv`) which represent the number of arguments the user provided and the actual data the user provided, respectively. Given the example use case above, how many command-line arguments is the user expected to provide?

<details>
  <summary>
    <span style="font-weight: bold;">
    Hint
    </span>
  </summary>
<br>

<p>Remember the number of command-line arguments, <code>argc</code> is just the number of words (or words and numbers) entered at the command line, including the program name itself!</p>

</details>

If they fail to provide the correct number, your program should exit (possibly printing out an error message that tells them how they should have run the program) and `return 1`; so that we can automate testing of your code.

Assuming we have the right number of command-line arguments, we’re well on our way. There’s a catch, though.

Just because the user types a real number at the command line, that doesn’t mean their input will be automatically stored in a `float`. Actually, it will be stored as a `string` that just so happens to look like an `float`; after all, remember the data type of `argv`? It’s an array where each element is a `string`! And so you’ll need to convert that `string` to an actual `float`. As luck would have it, a function, `atof`, exists for exactly that purpose! Here’s how you might use it:

```c
float a = atof(argv[1]);
```

There are two values that need to be converted from a `string` to a `float` (`argv[1]` and `argv[3]`, specifically). So that just leaves dealing with the operator. Recall from the shorts on arrays and strings that a string in C is really just an array of characters. And we can access individual elements of an array by using square bracket notation to **index** into that array.

```c
string s = "Calculator";
printf("%c\n", s[0]); // prints 'C'
```

Similarly, if we have another `string` which just so happens to be called `argv[2]` can we index into its first element, which will be a single character (`char`).

```c
printf("%c\n", argv[2][0]); // prints the first character of argv[2]
```

And that also means we can compare `argv[2][0]` against a variety of possible values (such as `+`, `-`, `x`, `/` or `%`, for example) and make certain decisions in our program based on what that character is, perhaps by making use of some Boolean expressions and conditional statements. (Of course, since there are only a small number of characters that we care about in `argv[2][0]`, you might also find this a good opportunity to use a `switch` statement for perhaps the first time.)

<details>
  <summary>
    <span style="font-weight: bold;">
    More on switch?
    </span>
  </summary>
<br>
<p>Note that this is an old (but good!) video which uses an older version of the coding environment, and an older version of `get_int`. The input funtion you see in the video (`GetInt`) has been discontinued.</p>
  
<iframe width="560" height="315" src="https://www.youtube.com/embed/ch4I--dGpOM?si=nfL8CdPEDTB4H2BB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

</details>


Note above that we suggest using a lowercase `x` instead of the typical asterisk used to represent multiplication. The reason for that is that the asterisk means something special at the command line, and so ordinarily it will not be processed correctly. So just be sure when you encounter an `x` at the command line that you actually perform a multiplication!

Once you’ve performed the arithmetic, just print out the result to the user on its own line, so we can automate testing of your code. By default, C will print out floating point values to six decimal places. Might as well leave it that way, there’s plenty to do otherwise in this problem!

{% next %}


## The Mod Squad
If you’re reading this section after you’ve already tried to implement modulo (`%`) in your calculator, you’ve likely noticed an error when compiling that looks something like the following:

```
error: invalid operands to binary expression ('float' and 'float')
```

Why are you seeing this? Well as it turns out, the modulo operator is not well-defined for floating point numbers. That is to say, there’s no defined value for an expression like:

```
10.7 % 3.28
```

Rather, it turns out that modulo is only defined (in C, anyway) for **integers**. How, then, can we implement the operator while still allowing the user to input floating point values at the command line? Seems like we’re going to have to do some extra work. After all, if modulo is really just the remainder after dividing the number on the left of the operator by the number on the right, a quick long division will tell us that `10.7 % 3.28` should equal `0.86`, the remainder after calculating `10.7 / 3.28`.

That leads to a discussion of today’s Arithmetic Fun Fact™. If

```c
x % y = z
```
then that means that

```c
x / y = q rem z
```

or put differently

```c
q = (int) (x / y);
z = x - (y * q);
```

Perhaps best to illustrate this with an example, as the formulas are perhaps a bit on the intimidating side. Let’s return to our prior example of calculating `10.7 % 3.28`.

```c
q = (int) (10.7 / 3.28);
q = (int) 3.262195;
q = 3
mod = 10.7 - (3.28 * 3);
mod = 10.7 - 9.84
mod = 0.86
```

So that is one way to implement the modulo operator by using other operators that C has defined for floats. To be sure, there are others, but this one should do the trick!

{% next %}

## Subtract the Confusion
To be clear, you may make the following assumptions with respect to your calculator.

`argv[1]`, should it be present, is guaranteed to consist only of digit characters, possibly a decimal point, and possibly a negative sign. You do not need to check otherwise.

`argv[2]`, should it be present, is not guaranteed to be `+`, `-`, `x`, `/` or `%`. Your program should respond somehow if the user provides an invalid operator and return 1;.

`argv[3]`, should it be present, is guaranteed to consist only of digit characters, possibly a decimal point, and possibly a negative sign. You do not need to check otherwise.

You needn’t worry about floating-point imprecision with your calculator, and you needn’t print out the correct answer to more than six decimal places.

{% next %}

## Pseudocode

Let's break this down into small steps. Write in the file pseudocode.txt how you think you should break this program down.

{% spoiler "Spoiler" %}

Remember the program works by typing in:

```
./calc 2 + 3
```

where `2` and `3` need to be converted from `strings` into two `floats`, and the operation, here `+`, could be not only `+` but also `-`, `x` (times), `/`, or `%` (modulo).

So:

1. Start out by checking for the correct number of command line arguments
1. Save `argv[1]` as a float in a new float varialbe (i.e. `float a = atof(argv[1])`)
1. Save the second numeric arguement (the 3 in the example above) in another float variable (possibly b)
1. Save the first character in the operator (`argv[2][0]`) in a `char` for easy comparison (you can't easily compare two `strings` in C)
1. Use an if...else statement (or a switch statement!) to determine which operator this `char` represents so you can perform the appropriate operation.
1. Finally, print the output as a float. No need to control the number of decimal places.

{% endspoiler %}


{% next %}

## Usage

Your program should behave per the examples below. 

```
$ $ ./calc 4 + 5
9.000000
```
or, using floating point arithmetic

```
$ ./calc 8.38 - 5.12
3.260000
```

and don't forget about modulo

```
$ ./calc 8 % 5
3.000000
```
## Testing

### Correctness
If you’d like to check the correctness of your program with check50, you may execute the below.

```
check50 cs50/problems/2019/ap/calc
```

### Style

```
style50 calc.c
```


## How to Submit

Execute the below, logging in with your GitHub username and password when prompted. For security, you'll see asterisks (`*`) instead of the actual characters in your password.

```
submit50 cs50/problems/2019/ap/calc
```
inputting your GitHub username and GitHub password as prompted.
