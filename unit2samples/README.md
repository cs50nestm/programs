# Palindrome

```c
#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string s = get_string("Text: ");

    bool palindrome = true;

    // Check chars from start and end
    for (int i = 0, len = strlen(s); i < len / 2; i++)
    {
        if (s[i] != s[len - 1 - i])
        {
            palindrome = false;
            break;
        }
    }

    // Print output
    if (palindrome)
    {
        printf("PALINDROME\n");
    }
    else
    {
        printf("NOT PALINDROME\n");
    }
}
```

# Anagram

```c
#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <string.h>
#include <strings.h>

#define ALPHASIZE 26

int main(void)
{
    string s1 = get_string("Word 1: ");
    string s2 = get_string("Word 2: ");

    // If an exact match, catch it here
    if (strcasecmp(s1, s2) == 0)
    {
        printf("EXACT MATCH\n");
        return 0;
    }

    // Declare an array which will associate each letter with the index
    int characters[ALPHASIZE] = {0};

    // Add 1 to corresponding place in array for each letter
    for (int i = 0, len = strlen(s1); i < len; i++)
    {
        if (isalpha(s1[i]))
        {
            characters[tolower(s1[i]) - 'a']++;
        }
        else
        {
            printf("Alpha chars only!\n");
            return 1;
        }
    }

    // Subtract 1 from corresponding place in array for each letter
    for (int i = 0, len = strlen(s2); i < len; i++)
    {
        if (isalpha(s2[i]))
        {
            characters[tolower(s2[i]) - 'a']--;
        }
        else
        {
            printf("Alpha chars only!\n");
            return 1;
        }
    }

    // If all elements in array are zero, it's an Anagram
    for (int i = 0; i < ALPHASIZE; i++)
    {
        if (characters[i] != 0)
        {
            printf("NOT ANAGRAM\n");
            return 0;
        }
    }

    printf("ANAGRAM\n");
}
```
