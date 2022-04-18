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

* Matching an Email. &ndash; `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

* Example Email &ndash;`test22_cake@fortytwo.net`

### Anchors

In our regex component our string has beginning which starts with an upcarrot &ndash;`^` and an end which is the dollar sign &ndash;`$`.

* &ndash;`^` (Upcarrot) Matches the beginning of the string, or the beginning of a line if the multiline flag(m) is enabled. This matches a posistion, not a character.
    
```md
Example: ^\w+ In "test22_cake@fortytwo.net" only "test22_cake is matched". This is the beginning of the string. If we were to drop the underscore our match would be "test22". The underscore has to be included because emails cannot contain white space.
```

* &ndash;`$` (Dollar Sign) Matches the end of the string, or the end of a line if the multiline flag(m) is enabled. This matches a posistion, not a character.

```md    
Example: \w+$ In "test22_cake@fortytwo.net" matches the end of the string. Since this is all one string connected by an underscore the entire string is matched. Without the underscore "cake" would be our only match.
```


### Quantifiers

+ &ndash;`(+)` (Plus) Matches 1 or more of the precedeing token.
```md 
Example: c\w+ which gives any words that start with "c" and follow 1 letter after that letter. In &;"cat" only the "ca" will be matched.
```

* &ndash;`(*)` (Star) Matches 0 or more of the precedeing token.
* Example: &ndash;`c\w*` which gives any words that start with &ndash;`"c"` and follow all letters after that letter. In &ndash;`"cat"` the whole word iwll match.

* &ndash;`{}` (Curly Braces) Matches the specified quantity of the previous token. {1,3} will match 1 to 3. {3} will match exactly 3. {3,} will match 3 or more.
* Example: &ndash;`c\w{2,3}` which only matches any words that have 2 to 3 more letters after the first one.

* &ndash;`?` (Question Mark) Matches 0 or 1 of the preceding token, effectily making it option.
* Example: &ndash;`"colou?r"` which matches the word color and colour because the "u" is optional.

* &ndash;`?` (Question Mark but Lazy) Which combines two quanitifiers which matches as few characters as possible.
* Example: &ndash;`c\w+?` which only matches the first letter following our first letter. In &ndash;`"clone"` only the &ndash;`"cl"` will be selected.

### OR Operator

* &ndash;`|` (OR) Acts like a boolean OR. Matches the expression before or after the |. It can operate within a group, or on a whole expression. The patterns will be tested in order.
* Example: &ndash;`b(a|e|i)d` which only matches words that have the letters in between the | like &ndash;`"bad"` &ndash;`"bed"` or &ndash;`"bid"` but not &ndash;`"bud"` or &ndash;`"bod"`.

### Character Classes

* Character Set matches any character in a set.
* Example: &ndash;`[aeiou]` with the string "How are you today?" will match all letters &ndash;`"o,"a","e","u"` in this string.

* &ndash;`\d` is a digit that matches numbers 0-9
* Example: &ndash;`\d` in this string &ndash;`"d223abblcc"` will only match &ndash;`"223"`

* &ndash;`\w` is &ndash;`A-Z, a-z, 0-9` matches any word or number. \W is anything that is a not a word or a number.
* Example: "This taco is turning 9 today." This will match everyone word a number in this string. \W will match no part of that string.

* &ndash;`\s` matches a space or a tab for white space. \S is anything that is a not white space.
* Example: "  This taco is turning 9 today." This matches the white space or the tab between the beginning of the string to the first word "This".

### Flags

* &ndash;`/i` Following the string makes the expression case-insensitive.
* Example: &ndash;`/aBc/i` would match "aBc" 

* &ndash;`/g` Retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.

* &ndash;`/m` When the multiline flag is enabled, beginning and end anchors  &ndash;`(^ $)` will match the start and the end of a line, instead of the start and end of the whole string.
* Example: &ndash;`/^[\s\S]+$/m`

### Grouping and Capturing

* &ndash;`()` Parenthesis groups multiple tokens together and creates a capture group for extracting a substrin or using a back refernce.
* Example: &ndash;`([a-z0-9_\.-]+)` will match any string within our brackets  &ndash;`"[]"`


### Bracket Expressions
* &ndash;`[]` (Square Brackets) Matches any character in a set.
* Example: &ndash;`([a-z0-9_\.-]+)` 

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
