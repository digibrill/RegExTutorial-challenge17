# Understanding HTML Tag-matching Regular Expressions

## Summary

This tutorial covers regular expressions that match HTML tags. The below is a sample string that can be used in a programming language like JavaScript.

Matching an HTML Tag – /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/

This may look a little cryptic, but regular expressions can be understood after a little study. They are defined as a sequence of alphanumeric and special (symbols or punctuation) characters that define a search pattern for a piece of text. In this tutorial we're going to break down how the characters of the above regex work. I will go through the whole regexp character by character (Regexp in Order) and then highlight each of the individual components separately.

## Table of Contents

- [Regexp in Order](#inorder)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Back-references](#back-references)

## Regex Components

### Regexp in Order

Firstly, a regex is is denoted as literal by the wrapping slash characters //.

Next, it is then followed by a literal < character denoting the beginning of the HTML tag. 

The parentheses contain square brackets with a-z inside [a-z], specifically matching a range of lowercase characters between a and z and one or more times in the string denoted by the + sign.

In the next grouping of characters () the less than symbol is negated by the carat ^, so that character will not appear in the search result and because of the following + sign, will not be present one or more times.

The following * denotes that the previous string will match zero or more times.

The next set of () starts with a grouping construct that is made non-capturing by adding the characters ?: at the beginning of an expression inside the parentheses. 

The following > closes out the first part of the HTML tag.

The group (.*) denotes the tag contents can be consisted of any character and any length.
 
Next the < is a literal character that begins the closing HTML tag. Then \/ is an escaped forward slash character, i.e. escaping characters allows special characters to be read as literal. 

The \1 denotes a repetition of the first parenthetical () that will again match the a-z character group one or more times in the string. This is so the first tag matches the second/last tag.
 
The pipe character | is used as an OR operator. Inside the second, compound group () it divides up the left and right options, so either the closing tag (above) or a space (s+ means any number of times) and then a closing tag are conditions that can be met.

The next \/ again is an escaped literal forward slash and closing greater than > that completes the HTML tag.

The $ anchor closes out the regex and denotes that the compound () (see above) string that precedes it must end the regex. 

The / closes off the regex.

Breaking it down below a little, according to the starter code's sections.

### Anchors
The ^ anchor at the start says that what follows must be at the beginning of the search string, namely the < mark.

The $ anchor closes out the regex and denotes that the string that precedes it must end the regex.

### Quantifiers
The + matches the preceding item 1 or more times and the * matches 0 or more times.

### OR Operator
The pipe character | is used as an OR operator. Inside the second, compound group () it divides up the left and right options, so either are conditions that can be met. 

### Character Classes
The first set of brackets will match the group of characters with a-z inside, specifically matching a range of lowercase characters between a and z and one or more times in the string.

### Grouping and Capturing

The ?: grouping construct at the beginning of the expression inside the compound, second parentheses denotes something not captured, i.e. does not affect the search results.

### Bracket Expressions
The bracket section with a-z denotes any range of characters. 

### Back-references
The first set of brackets will match the group of characters with a-z inside, specifically matching a range of lowercase characters between a and z and one or more times in the string. The \1 back reference expression later denotes this pattern being repeated at that place in the string. It will again match the a-z character group one or more times in the string.

## Author

Jonathan Berry, https://github.com/settings/profile, An Unassociated Press publication.

git remote set-url origin git@github.com:digibrill/https://gist.github.com/digibrill/d4033c1b0d33f5cf7764ebec37bf90c7
