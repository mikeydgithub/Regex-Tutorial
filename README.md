# Title Gist-Tutorial

A tutorial explaning how characters match in an email address. There is also other examples of other regex expressions included as well.

## Summary

* Matching an Email. `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

* Example Email `test22_cake@fortytwo.net`

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

* `/^([a-z0-9_\.-]+)`&ndash; `^` Starts the expression. `[a-z]`matches lower case letters a through z.`[0-9]` numbers match between 0 and 9.`[_\.-]+` matches underscores, periods, dashes, and characters precedding.

```md
`test22_cake`
```

* `@` Matches @ character.

```md
@
```

* `([\da-z\.-]+)`&ndash; `[\da-z]` matches any digit number(0-9) and letters that range (a-z) `[\.-]+` escaped character matches periods, dashes, and the precedding characters. 

```md
`fortytwo`
```

* `\.([a-z\.]{3})$/`&ndash; Matches a character between the range of (a-z) and can match words that preceed that first character that is up to 3, 6, or 8 characters exactly.  The `$` marks the end of the regular expression.

```md
`.net`
```


### Anchors

In our regex component our string has beginning which starts with an upcarrot `^` and an end which is the dollar sign `$`.

* `^` (Upcarrot) Matches the beginning of the string, or the beginning of a line if the multiline flag(m) is enabled. This matches a posistion, not a character.
    
```md
Example: `^\w+` In "test22_cake@fortytwo.net" only "test22_cake is matched". This is the beginning of the string. If we were to drop the underscore our match would be "test22". The underscore has to be included because emails cannot contain white space.
```

* `$` (Dollar Sign) Matches the end of the string, or the end of a line if the multiline flag(m) is enabled. This matches a posistion, not a character.

```md    
Example: `\w+$` In "test22_cake@fortytwo.net" matches the end of the string. Since this is all one string connected by an underscore the entire string is matched. Without the underscore "cake" would be our only match.
```


### Quantifiers

+ `(+)` (Plus) Matches 1 or more of the precedeing token.

```md 
Example: `c\w+` which gives any words that start with "c" and follow 1 letter after that letter. In "cake" only the "ca" will be matched.
```

* `(*)` (Star) Matches 0 or more of the precedeing token.

```md 
Example: `c\w*` which gives any words that start with `"c"` and follow all letters after that letter. In "cake" the whole word will match.
```

* `{}` (Curly Braces) Matches the specified quantity of the previous token. {1,3} will match 1 to 3. {3} will match exactly 3. {3,} will match 3 or more. 

```md
Example: In `c\w{2,3}` which only matches any words that have 2 to 3 more letters after the first one. "cake" would match because it's a whole word. "I" is a word but would not match.
```

* `?` (Question Mark) Matches 0 or 1 of the preceding token, effectily making it option.

```md
Example: `"colou?r"` which matches the word color and colour because the "u" is optional. The word will match without it.
```

* `?` (Question Mark but Lazy) Which combines two quanitifiers which matches as few characters as possible.

```md 
Example: `c\w+?` which only matches the first letter following our first letter. In "test" only the "te" will be selected.
```

### OR Operator

* `|` (OR) Acts like a boolean OR. Matches the expression before or after the |. It can operate within a group, or on a whole expression. The patterns will be tested in order.


```md
Example: `b(a|e|i)d` which only matches words that have the letters in between the | like "bad","bed" or "bid" but not "bud" or "bod".
```

### Character Classes

* Character Set matches any character in a set.

```md 
Example: `[aeiou]` with the string "How are you today?" will match all letters "o,"a","e","u" in this string.
```

* `\d` is a digit that matches numbers 0-9

```md
Example: `\d` in this string "d223abblcc" will only match "223"
```

* `\w` is `A-Z, a-z, 0-9` matches any word or number. `\W` is anything that is a not a word or a number.

```md
Example: "test22_cake@fortytwo.net" This will match everyone word a number in this string. `\W` will match no part of that string.
```

* `\s` matches a space or a tab for white space. `\S` is anything that is a not white space.
```md

Example: "  This taco is turning 9 today." This matches the white space or the tab between the beginning of the string to the first word "This".
```

### Flags

* `/i` Following the string makes the expression case-insensitive.

```md
Example: `/aBc/i` would match "aBc" 
```

* `/g` Retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.

* `/m` When the multiline flag is enabled, beginning and end anchors  `(^ $)` will match the start and the end of a line, instead of the start and end of the whole string.

```md
Example: `/^[\s\S]+$/m`
```

### Grouping and Capturing

* `()` Parenthesis groups multiple tokens together and creates a capture group for extracting a substrin or using a back refernce.

```md
Example: `([a-z0-9_\.-]+)` will match any string within our brackets  `"[]"`
```

### Bracket Expressions
* `[]` (Square Brackets) Matches any character in a set.

```md
Example: `([a-z0-9_\.-]+)` 
```

### Greedy and Lazy Match

* `( * + {})` Greedy and lazy matched are represented by an astrict plus curly braces. They expand a match as far as they can through the provided text. 

```md
Example: "<.*?>" takes "<div>simple div</div>" anything one or more times inside the "<>" arrows. 
```

### Boundaries

* `\babc\b` Performs a whole words only search.

```md
Example: In "ab", "abc", "abcc", "babc", only "abc" will match.
```

### Back-references


### Look-ahead and Look-behind

* `(?=) and (?<=)` Will only match if a specific character if the there is a character outside "(?=)" and there is a character following the "=".

```md
Example: "/d(?=r)" the characer "d" will only match if the "?" (preceeding characters) is equal to "r" in this case. In the string "drive", "d" will be matched.
```

## Author

Hi, my name is Mike Diamond, a full stack developer student for the UCF Coding Bootcamp. I created this tutorial to explain how regex systems work to match and filter what is located within strings. 

Link to my github: https://github.com/mikeydgithub
