# Regex Tutorial

A regular expression (shortened as regex or regexp; also referred to as rational expression) are literal strings or a sequence of characters that define a search pattern. It is a pattern used to match texts.

## Summary

This tutorial will explain the features of Regex and how we can take advantage of it.  Regular Expressions  to search for HTML tags is:

`/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Back-references](#back-references)
- [Author](#author)

## Regex Components
A regex is a string of text that allows you to create patterns that help match, locate, and manage text. 

### Anchors
In regex, anchors are not used to match characters, they match a position before, after, or between characters. To match start and end of line, we use following anchors:

Caret (^) matches the position before the first character in the string.
Dollar ($) matches the position right after the last character in the string.

### Quantifiers

 Quantifiers are used to quantify how many times a part of your regular expression should be repeated.  Every time you want to repeat something in a regex, you can write a quantifier after it to specify how many times it should be repeated.  This regular expression uses 2 types of quantifiers, the + symbol which highlights 1 or more of the previous requirements and it uses the * symbol to select 0 or more instances. There is a + sign in the first capture group to select the opening HTML element.

 `([a-z]+)`

Another + sign captures a group followed by a * symbol to indicate that it needs to select everything before the end of the opening tag.

`([^<]+)*`

This * symbol gathers anything in between the opening and closing tags.

`(.*)`

### OR Operator
You can use the | operator (logical OR) to match characters or expression of either the left or right of the operator.  In a regular expression it is denoted with a vertical line character |.

`/\1>|\s+`

### Character Classes

Character classes match a character from a specific set. There are a number of predefined character classes but you can also define your own sets.

`[a-z]+`      after the < in the regular expression and that searches for any more than 1 letter (+ sign) that is a-z.
`([^<]+)*`    captures 1 or more of anything that is not (^ symbol inside the brackets) a < symbol.
`\s+\/>`      matches a whitespace character that includes tabs and line breaks
`.*`          matches any character 

### Flags
Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression. 

 `$/gm` 
 
 `g` 
The (global) flag search retains the index of the last match, allowing subsequent searches to start from the end of           
the previous match. Without the global flag, subsequent searches will return the same match.

  `m`
When the multiline flag is enabled, the beginning and end anchors (^ and $) will match the start and end of a line instead of the start and end of the whole string.

### Grouping and Capturing
Parentheses group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex.

`(?:>(.*)<\/\1>|\s+\/>)`

### Bracket Expressions

A bracket expression enclosed in square brackets is a regular expression that matches a single character, or ordered element. If the initial character is a circumflex ^, then this bracket expression is complemented.

`[a-z]+)([^<]+)`

### Back-references

A backreference in a regular expression identifies a previously matched group and looks for exactly the same text again. The regular expression only has one back-reference towards the end in order to make sure the closing HTML tag matches the first capture group which got the element of the opening HTML tag.

`<\/\1>`

## Author

Arlon Tuazon is currently a student in UCLA Coding Boot Camp.
[Github] https://github.com/ArlonTuazon