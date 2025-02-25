# Regex Tutorial

Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects. These patterns are used with the exec() and test() methods of RegExp, and with the match(), matchAll(), replace(), replaceAll(), search(), and split() methods of String. This chapter describes JavaScript regular expressions.

## Summary

In this tutorial we will be describing how the following Regex is used to match an email address:

```const rexEmail = /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/;```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

- ```^The        matches any string that starts with The```
- ```end$        matches a string that ends with end```
- ```^The end$   exact string match (starts and ends with The end)```
- ```roar        matches any string that has the text roar in it```

### Quantifiers

- ```abc*        matches a string that has ab followed by zero or more c```
- ```abc+        matches a string that has ab followed by one or more c```
- ```abc?        matches a string that has ab followed by zero or one c```
- ```abc{2}      matches a string that has ab followed by 2 c```
- ```abc{2,}     matches a string that has ab followed by 2 or more c```
- ```abc{2,5}    matches a string that has ab followed by 2 up to 5 c```
- ```a(bc)*      matches a string that has a followed by zero or more copies of the sequence bc```
- ```a(bc){2,5}  matches a string that has a followed by 2 up to 5 copies of the sequence bc```

### OR Operator

- ```a(b|c)     matches a string that has a followed by b or c (and captures b or c)```
- ```a[bc]      same as previous, but without capturing b or c```

### Character Classes

- ```\d         matches a single character that is a digit```
- ```\w         matches a word character (alphanumeric character plus underscore)```
- ```\s         matches a whitespace character (includes tabs and line breaks)```
- ````.          matches any character```

### Flags

<p>Regular expressions may have flags that affect the search.</p>

<p>There are only 6 of them in JavaScript:</p

- ```i  With this flag the search is case-insensitive: no difference between A and a.```
- ```g  With this flag the search looks for all matches, without it – only the first match is returned.```
- ```m  Multiline mode.```
- ```s  Enables “dotall” mode, that allows a dot . to match newline character \n.```
- ```u  Enables full Unicode support. The flag enables correct processing of surrogate pairs.```
- ```y  “Sticky” mode: searching at the exact position in the text.```

### Grouping and Capturing

<p>Capturing groups are a way to treat multiple characters as a single unit. They are created by placing the characters to be grouped inside a set of parentheses. For example, the regular expression (dog) creates a single group containing the letters "d" "o" and "g". The portion of the input string that matches the capturing group will be saved in memory for later recall via backreferences</p>

### Bracket Expressions

- ```[ ] Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set```
- ```You can use the ^ metacharacter to negate what is between the brackets.```
- ```{ } Curly braces are used to specify an exact amount of things to match.```
- ```( ) Parentheses represent remembered matches. This is especially useful for find-and-replace operations or any time you need to do something with part of the match.```
- ```Parentheses are also used in regex to group parts of the expression together into subgroups, like in /(\$|¥)([0-9]+)\.([0-9]{2})/.```

### Greedy and Lazy Match

## Greedy
<p>By default the regular expression engine tries to repeat the quantified character as many times as possible. For instance, \d+ consumes all possible digits. When it becomes impossible to consume more (no more digits or string end), then it continues to match the rest of the pattern. If there’s no match then it decreases the number of repetitions (backtracks) and tries again.</p>

## Lazy
<p>Enabled by the question mark ? after the quantifier. The regexp engine tries to match the rest of the pattern before each repetition of the quantified character.</p>

### Boundaries

<p>The (\b) is an anchor like the caret (^) and the dollar sign ($). It matches a position that is called a “word boundary”. The word boundary match is zero-length.</p>

<p>The following three positions are qualified as word boundaries:

- <p>Before the first character in a string if the first character is a word character.</p>
- <p>After the last character in a string if the last character is a word character.</p>
- <p>Between two characters in a string if one is a word character and the other is not.</p>

<p>Simply put, the word boundary \b allows you to carry the match the whole word using a regular expression in the following form:</p>

```\bword\b```

### Back-references

<p>Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag. Here’s how: <([A-Z][A-Z0-9]*)\b[^>]*>.*?</\1>. This regex contains only one pair of parentheses, which capture the string matched by [A-Z][A-Z0-9]*. This is the opening HTML tag. (Since HTML tags are case insensitive, this regex requires case insensitive matching.) The backreference \1 (backslash one) references the first capturing group. \1 matches the exact same text that was matched by the first capturing group. The / before it is a literal character. It is simply the forward slash in the closing HTML tag that we are trying to match.</p>

### Look-ahead and Look-behind

## Lookahead
The syntax is:
- ```X(?=Y)```, it means "look for ```X```, but match only if followed by ```Y"```. There may be any pattern instead of X and Y.
## Lookbehind
Lookahead allows to add a condition for “what follows”.
Lookbehind is similar, but it looks behind. That is, it allows to match a pattern only if there’s something before it.
The syntax is:
- Positive lookbehind: ```(?<=Y)X```, matches X, but only if there’s Y before it.
- Negative lookbehind: ```(?<!Y)X```, matches X, but only if there’s no Y before it.


## Author
(https://hickups789.github.io/Regex-Tutorial/)
(https://github.com/Hickups789/Regex-Tutorial.git)


