---
title: "Regular Expressions in JavaScipt"
date: "2021-09-21"
draft: false
path: "/blog/regular-expressions"
---
# Regular Expressions

Regular expression are very powerful tool used for searching or matching patters. We can create a unique combination of the patterns and search for the patterns in string. RE gives us 
command over how to create a pattern, repetitions, charachters to be found, etc. 

## Definig RE
To create a Regular expression we can do either by putting the pattern in **/<your_RE_goes_here>/** 2 forward slashes or create using 
```
let re = new RegExp("your_RE")
```
All the normal constructor rules apply to the RegExp() function as well. We use the backward slashes to incdicate any special charecters like \+, \n, etc. Now \ without any
character after it is considered as \ only.

In /re /i/g we can use i - case insensitive, g- global all occurences.

## functions for testing
1. /abc/.**test("string")** is one function that will return Boolean value if the pattern is present in the string or not.
2. /RE/.**exec()** An object returned from exec has an index property that tells us where in the string the successful match begins and printing the object gives 
us the matching partn of the string.

3. "string".**replace([RE_Exp],"string to be replaced")** is used to find the pattern in string and replace it with the given string.

## Set of charecters
1. [0123456789] - return true if any of the characters present in the square brackets is found in the string.
2. *-* is used to indicate the range eg: [0-9]
```
\d	Any digit character
\w	An alphanumeric character (“word character”)
\s	Any whitespace character (space, tab, newline, and similar)
\D	A character that is not a digit
\W	A nonalphanumeric character
\S	A nonwhitespace character
.	Any character except for newline
```
3. When we put a **+** sign it indicates that it can be repeated more than once. eg: /\d+/ - many digits.
4. Wehn we put a * indicates that there are zero or more repetetion. eg: /\d*/ - >= 0 digits.
5. ? - indicates that the charecter preeceding the ? is optional 0 or 1 times.
6. To indicate number of times put {n} (n - number of repetetions) or {n, m} from n-m times.
7.  Use () - paranthesis to indicate the sub-expressions and use *,+,? to combine the sub expressions.
8.  To indicate the start and end of the string.
    - use ^\ to indicate from start nad
    - use $ sign to indicate the end of the string
    - eg: ^\d+$/ matches a string consisting entirely of one or more digits, 
    - eg: /^!/ matches any string that starts with an exclamation mark,

9. To test for multiple put a **|** symbol (pipe) like /(pig|cow|dog)?/