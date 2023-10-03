# Regex Tutorial

Regex expressions, also known as regex, are a pattern for matching strings. Regex expressions are used by developers in validating input data, search for a specific text, and replacing parts of a string. 

## Summary

In this tutorial, I will be explaing the validation of Canadian phone numbers using a simple JavaScript code.

I will be defning the following regex pattern that I like to match the pattern for a phone number.
        
        const regexPattern = /^(\(\+[0-9]{2}\))?([0-9]{3}-?)?([0-9]{3})\-?([0-9]{4})(\/[0-9]{4})?$/;

So the above pattern suppose to match the below array contains a list of sample Canadian phone numbers.

const phoneNumbers = [
  "+1(123)-456-7890",
  "416-555-1234",
  "(613)555-9876",
  "123-456-7890",
  "123-456-7890/1234",
];

Lets break it down the regexPattern for explaniantion

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

Anchors specify the postion of the text where it matches the start and end of a string. In our specific pattern, we leverage two anchor symbols: ^ and $. The ^ anchor asserts the match's start position, ensuring that it begins at the very beginning of the string. On the other hand, the $ anchor asserts the match's end position, guaranteeing that it spans until the end of the string

       /^.............. $/

### Character Classes

Character classes are vital components of regex patterns that define sets of characters that can match at a particular position in the text. In our pattern, character classes are used to specify the acceptable characters for matching. However, it seems that there is an incomplete sentence in this section. Character classes serve as a way to define a range or a specific set of characters that we want to match. In our pattern, we use character classes to match digits, hyphens, and other characters commonly found in phone numbers.

For example, in the pattern [0-9], the character class [0-9] matches any single digit.


### Quantifiers

Quantifiers specify how many times a character should appear. For example, we use {3} quantifiers to specify it matches previous token exactly 3 times. In our pattern we have 
      [0-9]{2}   
This means the quantifier {2} has previous token 'Character Class' [0-9] that matches single character in the range between 0 and 9 and to have exactly 2 digits. 
 Similary [0-9]{3} and [0-9]{4} means it would have exactly 3 dignts and 4 digits respectively. 

### Grouping and Capturing

We employ parentheses () for the purpose of grouping and capturing relevant sections within the regex pattern. These grouped sections can later be utilized for additional processing. In our specific regex pattern, we make use of parentheses for grouping purposes; however, it's important to note that we do not explicitly store or capture the content within these groups for subsequent use.

For example, in the pattern ^(\(\+[0-9]{2}\))?, we are grouping the international prefix ((\+[0-9]{2})), but we're not capturing it.

### Bracket Expressions

Bracket expressions [...] allow us to specify a set of characters to match at a particular position. In our pattern, we use [0-9] to match any digit and [-\/] to match hyphens or slashes.

[0-9] matches any digit.
[-\/] matches hyphens or slashes.

### Greedy and Lazy Match

In general Regex matches as much as possible. For example, the * quantifier matches the maximum number of characters. To make it lazy, we can use *?.

For example, in the pattern ([0-9]{3}-?)?, the * quantifier is greedy and matches as many digits and hyphens as possible. To make it lazy and match as few characters as possible, we can use *?.

### Boundaries

'\b' is used to specify word boundaries. We can use it to ensure that the phone number is not part of a larger word. For example, \b[0-9]{3}\b matches exactly 3 digits as a whole word.

## Author

I invite you to learn more about me and explore my other projects on my GitHub profile at https://github.com/vikramadityad/.
