# Old Friends: Hello

Improve upon older programs. This lab is the first of three that will convert three older programs to use command-line arguments.

```
$ ./hello Milo
Hello, Milo!
```

## Well Distributed

Here’s some good news for you right off the bat: you’ve seen almost everything we’re going to talk about in this problem once before. We’re going to revisit three old programs and rewrite them so that instead of taking input from the user while the program is running, they will instead accept input from the user at the command-line, before the program is even run.

Even better, to ensure everyone is on a level playing field while solving this problem, you’ll be using some "distribution code" (otherwise known as a "distro"), written by us, and make modifications to it. You’re welcome of course to use the code you wrote for a prior problem (if it worked!) and re-work it for this problem, but if you struggled with the problems we’ll be reimplementing this time around, know that we will otherwise be supplying you with fully-functional code. All you have to do is change the way that the user inputs data.

When you click on your folder icon, you should indeed see your first old friend!

```
hello.c
```

How nice to see you again!

Lastly, have a look at Doug’s short video on command-line arguments. Since we’ll be converting all three of the programs listed above to accept command-line arguments (none of them currently do!), this video should come in handy.

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
  <iframe src="https://youtu.be/AI6Ccfno6Pk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

If you happen to see (and are confused by!) char * in this and other shorts, know for now that char * simply means string. But more on that soon!


## Hello, again!

In Hello you were asked to write a program that very simply printed the message hello, world\n to the screen when run. It’s not too much of a leap to extend this program to say hello to a specific person by asking for the user to type a name at the prompt instead, so the program behaves like this.

```
$ ./hello
Your name: Zamyla
hello, Zamyla
```

In fact, the distro contains a file, hello.c, with exactly this behavior. What we want, though, is a program that has this behavior instead:

```
$ ./hello Zamyla
hello, Zamyla
```

See the slight difference? Instead of prompting the user for information after the program has started running, we collect the desired information from the user before they run the program, and then use that information once the program has started. How do we do so?

Recall that our programs are capable of knowing information about what the user typed at the command line by modifying the way we write the start of our main function. Instead of

```c
int main(void)
```

if we start main off by typing

```c
int main(int argc, string argv[])
```

we then have access to two special variables that we can use inside of main. First is argc, which is an integer variable that tells us how many things the user typed in at the command line, and second is argv, which is an array of strings representing exactly what the user typed.

Knowing this, and from the information in Christopher’s short, can you now modify hello.c so that it prints out the name provided at the command line, instead of collecting a string from the user after the program has started?

One more wrinkle. How do you make sure the user in fact did provide you with one (and only one) additional argument, so that you can print it out? Well remember that’s what our new friend argc can manage for us. If the user doesn’t supply a command-line argument, best to terminate the program and have them try again. One way to accomplish this might be to have this near the top of our code:

```c
if (argc != 2)
{
    printf("Usage: ./hello <name>\n");
    return 1;
}
```

Note what this accomplishes? We check to make sure that the user has supplied the proper number of command-line arguments. If not, we tell the user how they should run the program, and then we return 1;, which is our way of indicating that our program finished running, but not successfully. We use nonzero return values from main, also known as exit codes, to report back to the system that something went awry.


## How to Check

If you’d like to check the correctness of your program with check50, you may execute the below.

```
check50 cs50/problems/2019/ap/friends/hello
```

## How to Submit

Even though this is a practice problem please do submit to show you've completed it.

```
submit50 cs50/problems/2019/ap/friends/hello
```

