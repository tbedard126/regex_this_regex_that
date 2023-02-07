# Regex This......Regex That

## Summary

In this tutorial we will be discussing the Regular Expression for matching an email address
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This regular expression pattern is a rather simple way to vaildate is an email address based on the syntax.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Boundaries](#boundaries)
- [Back-references](#back-references)

## Regex Components

### Anchors

Anchors are special characters in regular expressions (regex) that match a position in the string being searched, rather than a character. There are two types of anchors: start and end.

Start Anchor ^: Matches the position at the start of the string. For example, ^A matches an A only if it appears at the beginning of the string.

End Anchor $ Matches the position at the end of the string. For example, A$ matches an A only if it appears at the end of the string.

### Quantifiers

Quantifiers in regex's are symbols that specify how many times a pattern should match. These are some of the quantifiers used in regular expressions.

`?` - matches zero or one occurrence of the preceding pattern.
`\*`- matches zero or more occurrences of the preceding pattern.
`+` - matches one or more occurrences of the preceding pattern.
`{n}` - matches exactly n occurrences of the preceding pattern.
`{n,}` - matches at least n occurrences of the preceding pattern.
`{n,m}` - matches at least n and at most m occurrences of the preceding pattern.

The first quantifier in this regex are `+` and it is used in two places `/^([a-z0-9_\.-]+)` and `([\da-z\.-]+)`. The second quantifier in this is `{2,6}` and this one matches between 2 and 6 of the preceding pattern.

### Character Classes

Character classes in regular expressions are a way to match a single character in the input text by specifying a set of characters. They are marked by square brackets [] and can contain individual characters, ranges of characters, or predefined character sets like \d for digits, \w for word characters, and \s for whitespace characters. There are three character classes in this regex expression. The first one is `[a-z0-9_\.-]` and this matches lowercase letters, digits, underscores, dots and hyphens. The second one is `[\da-z\.-]` that matches digits, lowercase letters, dots and hyphens. The third one in the regex is `[a-z\.]` this one only matches lowercase letters and dots.

### Flags

### Grouping and Capturing

Grouping in regex's allows you to group together parts of the pattern that are supposed to be one single unit. Capturing in regular expressions allows you to extract the text that was matched by each group. This text can be used later in backreferences. In this regex there are three capture groups. The first one is `([a-z0-9_\.-]+)` and this matches lowercase letters, digits, underscores dots and hyphens grouped as one. The second one is `([\da-z\.-]+)` this is for the second group and it matches digits, lowercase letters, dots and hyphens. The third in the regex is `([a-z\.]{2,6})` and this one matches 2 to 6 lowercase letters and dots.

### Bracket Expressions

A bracket expression is a type of character class that allows you to match one set of characters. Bracket expressions are defined using square brackets `[]` and can contain individual charcters, ranges of characters and special characters! In this regex two bracket expressions are used. The first one is `[a-z0-9_\.-]` and it matches any one of the specific characters lowecase letters, digits, underscores, dots and hyphens. The second one is `[\da-z\.-]` and this one matches any one of the specific characters digits, lowercase letters dots and hyphens.
Both of these bracket expressions are used as part of the capture groups.

### Boundaries

Boundaries in regex's define the starting and ending points of the string. They are used to make sure the pattern matches the entire string. There are 2 boundaiers being used in this regex.
The first one is `^` and this one matches the start of the string (the same as the ancor) and the second one is `$` and this one matches the end of the string. (also the same as the anchor)
Together these make it so it will only match an email address that starts in the beginning of the string and ends at the end of it.

### Back-references

Back-references in regex's allow you to refer to a previously matched pattern in the expression. This is useful for checking if a pattern appears twice in a string or verifying the pattern is repeated in a specific way. The back-references for this regex are for the first capturing group `([a-z0-9_\.-]+)` and this is referred to as `/1` later in the expression. This is for the part before the @ symbol in an email. The second one is in the second capturing group `([\da-z\.-]+)` and is referred to as `/2` later in the expression. This capturing group is for the portion between the @ and the . symbol. The third one is for the third capturing group `([a-z\.]{2,6})` and is refferd to as `/3` later in the expression. This capturing group is for portion of the email after . witch is usually .com .org etc.

## Author

This tutorial was made by Tyler Bedard for my coding boot camp.
[tbedard126](https://github.com/tbedard126)
