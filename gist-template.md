# Intrduction to regex

AS A web development student, I structured a tutorial explaining a specific regex so my fellow mates can understand the search pattern the regex defines.

## Summary

Regular expressions are combinations of special character operators. A set of characters that together make a pattern, which are symbols that control the search, that you can use to construct search strings for advanced find and/or replace searches. You are probably familiar with wildcard notations such as *.txt to find all text files in a file manager. The regex equivalent is .*\.txt.

## Table of Contents

- [Intrduction to regex](#intrduction-to-regex)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
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
  - [Sources](#sources)

## Regex Components

### Anchors
* The correct regex to use is ^\d+$.
* Applying ^a to abc matches a. ^b does not match abc at all, because the b cannot be matched right after the start of the string, matched by ^. See below for the inside view of the regex engine in other word ^abc$ -^start / $end of the string.
* ^	By default, the match must start at the beginning of the string.
* $	By default, the match must occur at the end of the string or before \n at the end of the string.


### Quantifiers
Quantifiers are used very often. They serve as the main “building block” of complex regular expressions, it allow you to specify the number of occurrences to match against.
* The regexp looks for character '<' followed by one or more Latin letters, and then '>'.
* a*a+a? -0 or more, 1 or more, 0 or 1
* "*" Matches 0 or more of the preceding token.
* The {n,m} quantifier matches the preceding element at least n times, but no more than m times, where n and m are integers. {n,m} is a greedy quantifier whose lazy equivalent is {n,m}?.

### OR Operator
Regex recognizes range expressions inside a list. They represent those characters that fall between two elements in the current, it acts like a boolean OR. Matches the expression before or after the 

### Character Classes
The most basic form of a character class is to simply place a set of characters side-by-side within square brackets, There are a number of predefined character classes and you can also define your own sets.
* the regular expression [bcr]at will match the words "bat", "cat"
* [a-zA-Z] will match any letter of the alphabet: a to z (lowercase) or A to Z (uppercase).
* [ABC] Characters inside brakets will match any character in the set.[^ABC] Adding a caret will match any character that is not in the set.
* \W	Returns a match where the string DOES NOT contain any word characters

### Flags
A flag changes the default searching behavior of a regular expression. It makes a regex search in a different way. You'll find only the i and g flags to be easily understandable. Flags follow the closing forward slash of the expression.
* i Ignores case it makes the expression search case-insensitively.
* g Global |  s Dot all |  M Multiline |  y Sticky  |  u Unicode
When a regex engine finds the first match for a given pattern in a given test string, the engine is eager to give a match.
For example two expressions /cats/ and /cats/g and our string is "cats love cats". The first expression (/cats/, without the g flag) would match only the first word 'cats' ("cats love cats"). In contrast, the second expression (/cats/g, with the g flag) would match both 'cats' ("cats love cats").



### Grouping and Capturing
Capturing groups are a way to treat multiple characters as a single unit, In the expression ((A)(B(C))), for example, there are four groups.
* \k<Name> he last substring matching the Named capture group specified by <Name>.
* \n Where "n" is a positive integer.
* (x)



### Bracket Expressions
A bracket expression is either a matching list expression or a non-matching list expression. It consists of one or more expressions

### Greedy and Lazy Match
Greedy will try to match the longest possible string.
Lazy will try to match the smallest possible string.

### Boundaries
The \b is the word boundary. \B is Not a word boundary 
The regex \bcat\b would therefore match cat in a black cat, but it wouldn't match it in catatonic, tomcat or certificate. Removing one of the boundaries, \bcat would match cat in catfish, and cat\b would match cat in tomcat, but not vice-versa. Both, of course, would match cat on its own.

### Back-references
Backreferences match the same text as previously matched by a capturing group, the regex engine does not permanently substitute backreferences in the regular expression. It will use the last match saved into the backreference each time it needs to be used.
[A-Z0-9]* backtracks the first time, reducing the capturing group to bo, \b fails to match between o and o. This forces [A-Z0-9]* to backtrack again immediately.

### Look-ahead and Look-behind
Lookahead and lookbehind, collectively called “lookaround”.
Lookaround allows you to create regular expressions that are impossible to create without them, or that would get very longwinded without them.
(?!ABC) is a negitive lookahead and it specifies a group that can not match after the main expression.
(?<!ABC) is a negitive lookbehind and Specifies a group that can not match before the main expression.

## Author
Claudy Regis 

## Sources
regexr (https://regexr.com/)
https://www.regular-expressions.info/backref.html


My Github [github] https://github.com/ClaudyRegis/challenge17