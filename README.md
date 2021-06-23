# Regex-Tutorial

As a web development student, I want develope a tutorial explaining a specifics of regex so that we can understand the search pattern of  the regex defines. To create a tutorial that explains how a specific regular expression, or regex, functions by breaking down each part of the expression and describing what it does. I'll use the template provided in the starter code to create my walkthrough.

## Summary

A Regex or regular expression is a sequence of characters that define a search pattern. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings. It also looks for input validations. It is a technique commonly developed in theoretical computer science. I will Take the following example of a regular expression, which we’ll call `Matching an Email`:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This series of characters are a search pattern that checks to see if a string fullfillss the requirements for a basic email.
* Considered a literal, so the pattern must be wrapped in slash characters (/).
*  matches one or more letters, digits, dots, and/or hyphens.
* The string can contain any lowercase letter between a–z.
* The string can contain any number between 0–9.
* The string can contain an underscore and hyphen.
* There must be a period (‘.’) `\.` at period with backslash.
* Finally, the email address must end with two to six alphabets or dots`([a-z\.]{2,6})`.
The below content will explain what each section of this code does and more in detail.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

“Matching an Email” regex is example selected
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Anchors

The characters `^` and `$` are both considered to be anchors.The `^` anchor signifies a string that begins with the characters that follow it. This could be in one of two formats:
* An exact string match or
* A range of possible aches, displayed using bracket expressions.
The `$` anchor signifies a string that ends with the characters that precede it. As with the `^` character, it can be preceded by an exact string or a range of possible matches. 

### Quantifiers

Set the limits of the string that your regex matches. They frequently include the minimum and maximum number
of characters that your regex is looking for. Quantifiers are inherently greedy, meaning they match as many occurrences of particular patterns as possible. 
They include the following:

`*`—Matches the pattern zero or more times

`+`—Matches the pattern one or more times

`?`—Matches the pattern zero or one time

`{}`—Curly brackets can provide three different ways to set limits for a match:

`{ n }`—Matches the pattern exactly n number of times

`{ n, }`—Matches the pattern at least n number of times

`{ n, x }`—Matches the pattern from a minimum of n number of times to a maximum of x number of times
In our case the “Matching an Email” have the quantifier `{2,6}`. This means that we want to find the 
preceding string pattern a minimum of 2 times and a maximum of 6 times.

### Grouping Constructs

The “Matching an Email” regex is fairly straightforward and open-ended about what it accepts. As regular 
expressions grow more complicated, you may check multiple parts of a string to determine that different 
sections fulfill different requirements. To break these sections up, you'll need to use grouping constructs.
The primary way you group a section of a regex is by using parentheses `()`. Each section within parentheses is known as a subexpression. Our exaple:`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` have 
three group: `([a-z0-9_\.-]+)`, `([\da-z\.-]+)`, and `([a-z\.]{2,6})$/`

### Bracket Expressions

Anything inside a set of square brackets `[]` represents a range of characters that we want to match. These 
patterns are known as bracket expressions, but they are also known as a positive character group, because they 
outline the characters we want to include. We can write these expressions to include all of the characters we want to match.
In our “Matching an Email” regex example:
*  `[a-z0-9_\.-]`—The string can contain any lowercase letter between `a–z`, any numbers b/n 0-9, underlines `_`, dots `.`, and hyphens `-`. 
*  `[\da-z\.-]`—The string can contain any number between `0–9`, any lowercase `a-z`, dots`.`, and hyphens`(-)`.
*  `[a-z\.]`-Has any lowercase `a-z` and dots `.`.

### Character Classes

A character class will match one out of several characters. The order of the characters within the character class does not matter.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

A character set [ABC] will match any single character in the set. In our example [a-z0-9_\.-] will match any character within the square brackets. A range [A-Z] will match a character included between the two characters separated by the hyphen. In our example a-z will match any character between a and z. 0-9 will match any character between zero and nine.

The following are additional examples of character classes that are not found in our example:

A negated set contains a caret first thing within the square brackets [^ABC] and matches any character that is not in the set.
A `.` will match any character except line breaks. The `.` in our example actually refer to actually periods, and are not a character class.
Word `/w` will match any word.
Not word `/W` will match any character that is not a word.
Digit `/d` matches any number.
Not digit `/D` will match any character that is not a number.
Whitespace `\s` will match any character that leaves whitespace (spaces, tabs, line breaks, etc.).
Not whitespace `\S` will match any character that is not a whitespace character.

### The OR Operator

The pipe `|` is considered an alternation. It matches the expression before or after it. This quantifier can affect specific characters, 
or a whole expression. There are none in our example.

### Flags

Flags will always follow the closing forward slash charactors of an expression, and change how it is interpreted.
There are no flags in our example; however, the following are some examples with `g`, `i`, & `m` are the three you're most 
likely to encounter:
* Ignore case i will make the entire expression case-sensitive.
* Global search g will store the index of the last match.
* Multiline m will cause the beginning and end anchors to match the start and end of a line instead of the     whole string.
* Unicode u allows extended unicode escapes in the form \x{FFFFF}.
* Sticky y will only match from its last index position and ignores the global search flag.
* Dot all s causes dot (.) to match any character.

### Character Escapes

The backslash (\) in a regex escapes a character that otherwise would be interpreted literally. For example, the open curly brace ({) is used to begin a quantifier, but adding a backslash before the open curly brace(\{) means that the regex should look for the open curly brace character instead of beginning to define a quantifier. This is common when looking for strings with special characters that are the same as a particular component of a regex. It's important to note that all special characters, including the backslash (\), lose their special significance inside bracket expressions.

## Author

Dereje Ayele: University of Richmond Coding Bootcamp Student                                                 
GitHub: https://github.com/dereatom

### Referances

https://www.youtube.com/watch?v=7DG3kCDx53c
https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp