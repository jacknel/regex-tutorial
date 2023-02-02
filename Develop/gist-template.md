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

### Anchors

### Quantifiers

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

Regex: Matching a HEX Value

Gist file that will describe what makes up a particular regex used for HEX values.
Summary

The regex being evaluated:

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

Anchors

Anchors are special characters used in regular expressions to match the start or end of a string.

    The "^" anchor:

    Code: /^#
    Description: Matches the start of the input. If the multiline flag is set to true, it also matches immediately after a line break character. For example, the expression "/^A/" does not match the "A" in "an A", but does match the first "A" in "An A".
    In our example, the '^' anchor specifies that the start of the string must match the character '#'. This '#' distinguishes a hexadecimal number from a decimal number.

    The "$" anchor:

    Code: $/
    Description: Matches the end of the string. If the multiline flag is set to true, it also matches immediately before a line break character. For example, the expression "/t$/" does not match the "t" in "eater", but does match it in "eat".
    In our example, the '3' and '6' characters are quantifiers. They set the number of instances of those specific values that can exist at the end of a string.


Quantifiers

Quantifiers are used in regular expressions to specify the number of times a preceding expression should be matched.

    The "?" quantifier:

    Code: /^#?
    Description: Matches the preceding item either 0 or 1 time (a boolean value). For example, the expression "/e?le?/" matches "el" in "angel" and "le" in "angle."
    If used immediately after any of the quantifiers (*, +, ?, or {}), it makes the quantifier non-greedy (matching the minimum number of times), instead of the default greedy behavior (matching the maximum number of times).
    In our example, the character following the '?' is set to be optional.

    The "{}" quantifier:

    Code: Both [a-f0-9]{6} and [a-f0-9]{3}
    Description: Indicates how many times to apply the preceding expression. For example, the expression "/a{2}/" does not match the "a" in "candy", but matches all "a"s in "caandy" and the first two "a"s in "caaandy".
    In our example, there should be 6 instances of the value within the square brackets. This means there will be 6 characters between a-f and/or 0-9. The same goes for {3}, but there will be 3 characters instead of 6.

OR Operator

The OR operator, represented by the pipe symbol (|), is used in regular expressions to match either one expression or another.

    Code: [a-f0-9]{6}|[a-f0-9]{3}
    Description: Matches either "x" or "y", where each component separated by a pipe (|) is called an alternative. For example, the expression "/green|red/" matches "green" in "green apple" and "red" in "red apple".
    In our example, the regular expression will match either a 3 character string or a 6 character string, represented by [a-f0-9].


Character Classes

Character Classes are a special syntax used in regular expressions to match a specific set of characters.

    Code: a-f0-9
    Description: Matches any one of the enclosed characters. Ranges of characters can be specified by using a hyphen (-), but if the hyphen appears as the first or last character within square brackets, it is considered a literal hyphen to be included in the character class.
    In our example, the character class consists of lowercase letters 'a' to 'f' and numbers '0' to '9'.


Grouping and Capturing

Grouping and Capturing is a feature in regular expressions that allows you to group together certain parts of the expression and capture their matches as a single unit.

    Code: ([a-f0-9]{6}|[a-f0-9]{3})
    Description: The expression between parentheses is grouped and remembered as a single match. It is often stored in an array and can be accessed using indices. For example, the expression "/(foo)/" matches and captures "foo" in "foo bar".
    In our example, the character class previously discussed is now grouped within parentheses, creating a single unit for the regular expression to match.


Bracket Expressions

A Bracket Expression is a type of syntax in regular expressions that specifies a set of characters to match.

    Code: [a-f0-9]
    Description: The characters within the brackets are matched according to the specified parameters. Ranges of characters can be established using a hyphen. For example, the expression "[a-d 1-3]" would match any string that contains at least one character from the range of "a-d" or "1-3".
    In our regular expression, the bracket expression [a-f0-9] is used to match strings that contain either a lowercase letter from "a-f" or an integer from "0-9".


Greedy and Lazy Match

The code: [a-f0-9]{6} and [a-f0-9]{3}

Description: The distinction between greedy and lazy match is straightforward. A greedy match will attempt to match the longest possible string, while a lazy match will match the shortest possible string. For instance, the greedy pattern 'h.+l' matches 'hell' in 'hello', but the lazy pattern 'h.+?l' matches 'hel'.

In our regex, since there is no '?' after the quantifier, the match is not greedy (as discussed in the section on the ? quantifier).


Author

My name is Jack Nelson and I am an aspiring software engineer. I have posted this with a link to my Github page which includes all of my most recent projects.

GitHub profile: https://github.com/jacknel