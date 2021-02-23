# Regex Tutorial

A regular expression (shortened as regex or regexp; also referred to as rational expression) are literal strings or a sequence of characters that define a search pattern. It is a pattern used to match texts.

## Summary

This tutorial will explain the features of Regex and how we can take advantage of it.  Regular Expressions are expressions that made to match a specific pattern.

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
- [Author](#author)

## Regex Components
A regex is a string of text that allows you to create patterns that help match, locate, and manage text. 

### Anchors
In regex, anchors are not used to match characters, they match a position before, after, or between characters. To match start and end of line, we use following anchors:

Caret (^) matches the position before the first character in the string.
Dollar ($) matches the position right after the last character in the string.

### Quantifiers

 Quantifiers are used to quantify how many times a part of your regular expression should be repeated.  Every time you want to repeat something in a regex, you can write a quantifier after it to specify how many times it should be repeated.

##### The following list shows some examples of the most common quantifiers:

?
*
+
{N}
{,N}
{N,}
{N,M}

### OR Operator
You can use the | operator (logical OR) to match characters or expression of either the left or right of the operator.  In a regular expression it is denoted with a vertical line character |.

### Character Classes

Character classes match a character from a specific set. There are a number of predefined character classes but you can also define your own sets.

\d         matches a single character that is a digit.
\w         matches a word character that is alphanumeric character plus underscore
\s         matches a whitespace character that includes tabs and line breaks
.          matches any character 

### Flags
Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression. There are only 6 of them in JavaScript:

 `i`  
This flag ignore case so there is no difference between A or a.
	
 `g` 
The (global) flag search retains the index of the last match, allowing subsequent searches to start from the end of           
the previous match. Without the global flag, subsequent searches will return the same match.

  `m`
When the multiline flag is enabled, the beginning and end anchors (^ and $) will match the start and end of a line instead of the start and end of the whole string.

 `u`
The Unicode flag enables correct handling of surrogate pairs.

`s`
The `s` enables the dotall `.` mode which will match any character, including newline.

### Grouping and Capturing
Parentheses group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex.
##### Example:
(abc){3} matches abcabcabc. First group matches abc.

Escaped parentheses group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex.
##### Example:
\(abc\){3} matches abcabcabc. First group matches abc.


### Bracket Expressions

A bracket expression enclosed in square brackets is a regular expression that matches a single character, or ordered element. If the initial character is a circumflex ^, then this bracket expression is complemented.

* See Character Class to see examples.

### Greedy and Lazy Match

A Greedy quantifier always attempts to repeat the sub-pattern as many times as possible before exploring shorter matches by backtracking.  By default, all quantifiers are greedy.

A Lazy (also called non-greedy or reluctant) quantifier always attempts to repeat the sub-pattern as few times as possible, before exploring longer matches by expansion.  Generally, a lazy pattern will match the shortest possible string.

For more information:  https://riptutorial.com/regex/example/1439/greediness-versus-laziness

### Boundaries
The `\b` is an anchor like the caret and the dollar sign. It matches at a position that is called a word boundary. This match is zero-length.

Characters that are matched by the short-hand character class `\w` are the characters that are treated as word characters by word boundaries.

Since digits are considered to be word characters, `\b5\b` can be used to match a 5 that is not part of a larger number. Putting a `\b` before and after an alphanumeric sequence matches are more exact than putting it “before and after a word”.

`\B` is the negated version of `\b`. `\B` matches at every location where `\b` does not. Effectively, `\B` matches at any position between two word characters as well as at any position between two non-word characters.


### Back-references

A backreference in a regular expression identifies a previously matched group and looks for exactly the same text again.

* Named Backreferences
A named backreference is defined by using the following syntax:

`\k< name >`

or:

`\k' name '`

where name is the name of a capturing group defined in the regular expression pattern.

* Numbered Backreferences:
A numbered backreference uses the following syntax:

`\ number`

where number is the ordinal position of the capturing group in the regular expression.

### Look-ahead and Look-behind

Lookahead and lookbehind in a group are called “lookaround”, are zero-length declarations just like the start and end of line, and start and end of word anchors. There are positive and negative lookarounds.

##### Examples:

*	`(?=ABC)` is a positive lookahead and it matches a group after the main expression without including it in the result.
*	`(?!ABC)` is a negative lookahead and it stipulates a group that cannot match after the main expression. If it matches, the result is discarded. 
*	`(?<=ABC>)` is a positive lookbehind and matches a group before the main expression without including it in the result.
*	`(?<!ABC)` is a negative lookbehind and specifies a group that cannot match before the main expression. If it matches, the result is discarded.


## Author

Arlon Tuazon is currently a student in UCLA Coding Boot Camp.
[Github] https://github.com/ArlonTuazon