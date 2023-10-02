# Fahrenheit

## tl;dr

Implement a program that converts degrees in Celsius to Fahrenheit, per the below.

```
$ ./fahrenheit
C: 0
F: 32.0
```

## Turning Up The Heat

In the past, if you wanted to know what the outdoor temperature was, you had to look around for one of these, which might have been mounted outside at your house.

![Thermometer](https://raw.githubusercontent.com/cs50nestm/labs/2020/fahrenheit/thermometer.png)

Prior to that, you just stood outside, but we digress. Nowadays, it’s a fairly trivial exercise to pull open a weather app on your phone or visit a weather-reporting website to get the current temperature and the five-day forecast. No need to mess around with one of the above circular dials or its tube-of-mercury cousin.

Depending on where you live in the world, your country uses one of two major temperature scales. If you live in the United States (and don’t spend most of your day working in a science lab), it’s likely that you’re familiar with the Fahrenheit scale, and so if you hear that it’s 30° outside you’re probably putting on a heavy coat and warm pants and bracing yourself for the possibility of snow, because that means it’s quite cold, given that the freezing point of water is 32°. On the other hand, it’s not until the temperature hits 212° that water boils.

In practically every other country of the world (or if you live in the United States and do in fact spend most of your day working in a science lab), you’re probably most familiar with the Celsius or centigrade scale. In that case, if you hear that it’s 30° outside you’re probably going to rummage through your closet for a swimsuit and put on some sunblock, because it’s a beautiful beach day. On the Celsius scale, 0° is the freezing point of water, and 100° is the boiling point.

We acknowledge that with most apps that tell you the weather, it’s fairly simple to press that switch that switches the temperature display from Fahrenheit to Celsius (or vice versa), but before that process was automated for us, one either had to memorize some of the more common conversion points or had to use a mathematical formula to convert from one scale to another, which is important if you plan on traveling internationally.

For this problem, we’re going to focus on converting in just one direction: from Celsius to Fahrenheit. As it happens, the formula for this conversion isn’t terribly complex. (Phew!) One simply takes the current temperature in degrees Celsius (°C), multiplies it by 9, divides by 5, and then adds 32. The result is the equivalent temperature in degrees Fahrenheit (°F). Not bad, right? For the more visually inclined, this translates to this formula:

```
F = ((C * 9) / 5) + 32
```

Let’s do a quick test to make sure things work as expected. Worldwide, the commonly accepted value for normal human body temperature is 37°C. If we plug "37" into that formula where °C goes and do the math (37 multiplied by 9 is 333, 333 divided by 5 is 66.6, 66.6 + 32 is 98.6) we get 98.6°F which is what folks in the United States know as normal human body temperature. So that checks out. Similarly if we plug in 0°C (the freezing point of water) into that formula does it convert to 32°F, and 100°C (the boiling point of water) is apparently equivalent to 212°F. Seems like things are going well.

So your job is to write a program that converts a temperature in Celsius to Fahrenheit, as per the sample output below, wherein the "100" represents some user’s input.

```
$ ./fahrenheit
C: 100
F: 212.0
```

## Pseudocode

First, write in `pseudocode.txt` at right some pseudocode that implements this program, even if not (yet!) sure how to write it in code. 

Odds are your pseudocode will use (or imply using!) one or more functions, operators, and variables.

<details>
  <summary>
    <span style="font-weight: bold;">
    Hints
    </span>
  </summary>
  <p>
  There's more than one way to do this, so here's just one!
</p>

<ol>
  <li>Prompt for degrees Celsius and save this in a variable</li>
  <li>Use this value to calculate degrees Fahrenheit and save in another variable</li>
  <li>Print out the result</li>
</ol>

<p>
  It's okay to edit your own after seeing this pseudocode here, but don't simply copy/paste ours into your own!
</p>

</details>


## Prompting for Input

Whatever your pseudocode, let's first write only the C code that prompts (and re-prompts, as needed) the user for input. 

First, declare a new floating point variable to hold degrees Celsius.

Do recall that if you include `<cs50.h>` atop your fahrenheit.c file, you will have access to a function called get_float, which will allow the user to input a floating-point value (a number with a decimal point in it, also known as a real number).The parameters of the get functions will display a prompt for users.

Now make sure to assign the value of this input function to your new Celsius variable.

Declare another float to hold degrees Fahrenheit, and assign the result of the temperature conversion formula (given above). 

Finally, print out the result with exactly one decimal place.

{% spoiler "hint" %}

Printf can be used to specify how many places after the decimal point you wish to display to the user. For example to print a float with 2 decimal places you would type:

```c
printf("%.2f\n", number);
```

Can you see why this prints with 2 decimal places? Now adapt this to print degrees Fahrenheit (don't forget to start the output with "F: ") to exactly one decimal place.

{% endspoiler %}

## Testing
### Correctness
Before turning in your solution, be sure to test the correctness of your program with check50, by executing the below.

```
check50 cs50/problems/2019/ap/fahrenheit
```

### Style

If you pass all the check50 test cases, and get a green smiley face when you run things through style50, as with:

```
style50 fahrenheit.c
```

If not, don’t worry: it’s just time for a little bit of debugging and/or cleaning up your code.

## How to Submit

Execute the below, logging in with your GitHub username and password when prompted. For security, you'll see asterisks (`*`) instead of the actual characters in your password.

```
submit50 cs50/problems/2019/ap/fahrenheit
```

You may resubmit any problem as many times as you’d like before the deadline.

Your submission should be graded for correctness within 2 minutes, at which point your score will appear at submit.cs50.io!

This was Fahrenheit.
