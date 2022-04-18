# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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
    Defines a search pattern in a body of text. Literal characters. Example is Rainbow, useing capital R and lowercase letters. Meta Character, does not indicate a single literal character but a generalized pattern. Example is any possible value, uppercase character, whitespace, nounse. in a phone number lets find any numbers in a phone number. 917-555-1234 and 646. 867-5309. What can I say. Make a list of meta characters. Match any digit 
    \d\d\d-\d\d\d-\d\d\d\d, 
    . dot, means any character.
    * star, means 0 or more. 
    .* dot-star, is a wildcard.
    \d is a digit that matches numbers 0-9
    \w is A-Z, a-z, 0-9 matches anyword. \W is anything that is a not a word.
    \s matches a space or a tab for white space. \S is anything that is a not white space.

### Anchors

    ^ (Upcarrot) Matches the beginning of the string, or the beginning of a line if the multiline flag(m) is enabled. This matches a posistion, not a character.
    Example: ^\w+, "This cat is gigantic." In this string only the first word "This" will be matched.

    $ (End) Matches the end of the string, or the end of a line if the multiline flag(m) is enabled. This matches a posistion, not a character.
    Example: \w+$, "This cat is gigantic." In this string only the last word "gigantic" will be matched.


### Quantifiers

    + (Plus) Matches 1 or more of the precedeing token.
    Example: c\w+ which gives any words that start with "c" and follow 1 letter after that letter.

    * (Star) Matches 0 or more of the precedeing token.
    Example: c\w* which gives any words that start with "c" and follow all letters after that letter.

    {} (Curly Braces) Matches the specified quantity of the previous token. {1,3} will match 1 to 3. {3} will match exactly 3. {3,} will match 3 or more.
    Example: c\w{2,3} which only matches any words that have 2 to 3 more letters after the first one.

    ? (Question Mark) Matches 0 or 1 of the preceding token, effectily making it option.
    Example: "colou?r" which matches the word color and colour because the "u" is optional.

    ? (Question Mark but Lazy) Which combines two quanitifiers which matches as few characters as possible.
    Example: c\w+? which only matches the first letter following our first letter. In "clone" only the "cl" will be selected.

    | (Alternation) Acts like a boolean OR. Matches the expression before or after the |. It can operate within a group, or on a whole expression. The patterns will be tested in order.
    Example: b(a|e|i)d which only matches words that have the letters in between the | like "bad" "bed" or "bid" but not "bud" or "bod".
    

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
