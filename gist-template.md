# Regex This......Regex That

## Summary

In this tutorial we will be discussing the Regular Expression for matching an email address
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This regular expression pattern is a rather simple way to vaildate is an email address based on the syntax. This assumes that the email address has the following format:

The local part of the email address, which is the part before the @ symbol, can contain lowercase letters, digits, underscores, dots, and hyphens, and must be at least one character long.
The domain part of the email address, which is the part after the @ symbol, can contain digits, lowercase letters, dots, and hyphens, and must be at least one character long.
The top-level domain, which is the part after the final dot, must contain two to six lowercase letters or dots.

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

Anchors are special characters in regular expressions (regex) that match a position in the string being searched, rather than a character. There are two types of anchors: start and end.

Start Anchor ^: Matches the position at the start of the string. For example, ^A matches an A only if it appears at the beginning of the string.

End Anchor $ Matches the position at the end of the string. For example, A$ matches an A only if it appears at the end of the string.

### Quantifiers

Quantifiers in regex's are symbols that specify how many times a pattern should match. These are some of the quantifiers used in regular expressions.

"?" - matches zero or one occurrence of the preceding pattern.
"\*"- matches zero or more occurrences of the preceding pattern.
"+" - matches one or more occurrences of the preceding pattern.
"{n}" - matches exactly n occurrences of the preceding pattern.
"{n,}" - matches at least n occurrences of the preceding pattern.
"{n,m}" - matches at least n and at most m occurrences of the preceding pattern.

### OR Operator

The "or" operator in regular expressions, represented by the vertical bar symbol |, is used to specify multiple alternative patterns that can match a single piece of text. It allows you to specify multiple possibilities and match any of them. The operator is useful when you need to match different variations of the same text, such as different spellings, synonyms, or abbreviations. To ensure that the intended pattern is matched, it is best to group the alternative patterns using parentheses when combining them with the "or" operator.

### Character Classes

Character classes in regular expressions are a way to match a single character in the input text by specifying a set of characters. They are denoted by square brackets [] and can contain individual characters, ranges of characters, or predefined character sets like \d for digits, \w for word characters, and \s for whitespace characters. Character classes provide a convenient and flexible way to match specific types of characters in a string and are often used in regular expressions for validation purposes, such as checking if a string conforms to a specific pattern such as an email address, phone number, or date.

### Flags

Flags in regular expressions are optional symbols that change the way a pattern behaves when matching input text. Some commonly used flags are i for case-insensitivity, g for global matching, and m for multiline matching. The way to specify flags varies depending on the programming language and tool, but they allow a regular expression to be more flexible and suited to specific matching needs. For instance, the i flag can match text regardless of letter case, while the g flag can match all occurrences of a pattern in a string.

### Grouping and Capturing

Grouping and capturing in regular expressions refer to the process of grouping multiple patterns together and extracting specific parts of the matched text. Grouping is done using parentheses () to treat multiple subpatterns as a single unit. Capturing is the process of extracting the matched substrings, which can be accessed using backreferences that correspond to the grouped subpatterns. This is a useful way to match complex patterns and obtain relevant information from the input text. These concepts are frequently used in applications such as data validation, parsing, and string manipulation.

### Bracket Expressions

Bracket expressions in regular expressions are a way of matching a set of characters in a string. They are denoted using square brackets [] and can contain individual characters, ranges of characters, or both. For example, the pattern /[abc]/ matches any of the characters "a", "b", or "c", while the pattern /[a-z]/ matches any lowercase letter. Bracket expressions can also contain special characters and character classes, such as digits, whitespace, and word characters, making them a useful tool for matching different types of text patterns. They are widely used in applications such as data validation, pattern matching, and string manipulation.

### Greedy and Lazy Match

The terms "greedy" and "lazy" in regular expressions refer to how the regular expression engine matches a pattern in a string.

A greedy match is when the engine tries to match as much of the string as possible, provided that the entire pattern still matches. For example, the pattern /.\*/ is greedy and matches any string of any length.

On the other hand, a lazy match is when the engine matches only as much of the string as is needed to satisfy the pattern. This can be achieved using the ? quantifier, which makes the preceding match lazy. For instance, the pattern /.\*?/ is a lazy match that matches an empty string.

Choosing between greedy and lazy matching is important in cases where patterns overlap or are ambiguous. For example, in matching an HTML string, a greedy match might match the entire string from the first to the last tag, while a lazy match might only match the first tag.

By default, regular expressions use greedy matching. Lazy matching is used to override this behavior when needed. Understanding the difference between greedy and lazy matching is important for writing accurate regular expressions and avoiding unexpected results.

### Boundaries

Boundaries in regular expressions are special markers that define the location of a match within a string, instead of matching specific characters. These markers help specify the start or end of a line, word, or the entire string.

Common boundaries include:

The ^ (caret) symbol, which matches the beginning of a line.
The $ (dollar) symbol, which matches the end of a line.
The \b (word boundary) symbol, which matches the position between a word character (letters, digits, or underscore) and a non-word character.
The \B (non-word boundary) symbol, which matches the position between two word characters or between two non-word characters.
Boundaries are useful in providing constraints to where a match can occur in the string. For instance, the pattern /\bword\b/ only matches the word "word" when it appears as a standalone word in the text. Similarly, the pattern /^start/ matches lines that start with "start".

Boundaries are crucial in applications involving string manipulation, pattern matching, and data validation. Having a good understanding and effective use of boundaries can lead to more precise and trustworthy regular expressions.

### Back-references

Back references in regular expressions allow you to repeat a portion of a pattern that was previously matched. By referencing a previous match, you can ensure that a particular pattern appears twice in a string or that a pattern is repeated in a specific way.

Back references can be created by enclosing a portion of the pattern in parentheses and then referring to that portion in the expression using a special syntax, either a number (such as \1) or a name (such as \k name). For example, the pattern /(\w+)\s\1/ matches repeating words separated by a space, by referencing the first captured group ((\w+)) with the back reference \1.

Back references are a useful tool in string manipulation, pattern matching, and data validation. They allow you to write more compact and efficient expressions and can lead to more precise and accurate pattern matching.

### Look-ahead and Look-behind

Look-ahead and look-behind are features in regular expressions that allow you to match patterns without consuming any characters in the final match. They are essentially zero-width assertions that specify conditions for a match based on the surrounding context of a string.

Look-ahead, specified using (?=...), matches a pattern only if it appears ahead of the current position in the string, while look-behind, specified using (?<=...), matches a pattern only if it appears immediately behind the current position.

For instance, a pattern such as \w+(?=\s) matches one or more word characters only if they are followed by a space, and (?<=\s)\w+ matches one or more word characters only if they are preceded by a space.

Look-ahead and look-behind are useful in matching patterns that depend on their context, such as matching a word only if it appears after or before a specific pattern. They provide a way to specify constraints for a pattern to match, making them a powerful tool in pattern matching and string manipulation.

## Author

This tutorial was made by Tyler Bedard for my coding boot camp.
[tbedard126](https://github.com/tbedard126)
