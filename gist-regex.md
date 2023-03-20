# Computer Science for JavaScript: Regex Tutorial

I have watched videos and read pages about how a Regex works. It is a very helpful tool at narrowing down text, numbers, and more. With a regex, regular expression, you can tell what the fields will be for an email, username, password, etc. Reqex will initially look like the strangest line of code, but each part is significant in describing what youre trying to accomplish.

## Summary

A regex I will use as an example is /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/   . This line of code is validating an email address. I will go into more detail about what each mean in the provided sections below.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components
Regex components are wrapped inside (/) characters like the beginning and ending of the code above. This will show that the expression is literal.

### Anchors
Anchors are the characters ^ and $ you see in the code provided. The ^ symbol is used to show where the string begins, so it will look for the following information after ^. The $ symbol signifies the end of the string.

### Quantifiers
Quantifiers, will add limits to your regex matches. This might include min and max characters. For instance, in the line of code we have {2,6}, this will put the minimum at 2 and the maximum at 6. so it will see that if you had a line longer than 6, it will not be a match. Some other quantifiers in our snipit would be the +, but other snipits might include a ? or *. The +, will match the pattern one or more times. The *, matches the pattern zero or more times and the ? matches the pattern zero or one time. Curly brackets will provide different ways of limiting the match. Having just { b }, will match the pattern EXACTLY b number of times. { b, } will match the pattern AT LEAST b number of times. finally { b, z } matches a minimum of b and a maximum of z. In our case this goes back to {2,6}, 2 being the minimum and 6 being the maximum. 

### Grouping Constructs
In order to break things up and have different requirements you will use () . In our code above we split ([a-z0-9_\.-]+) before the @ symbol, ([\da-z\.-]+) after the at symbol, and ([a-z\.]{2,6}) after the period. This is because it is the structure of, in our case, an email string. We used the paranthesis to break up which part were specifically looking at for those requirements. Most of the time grouping constructs will have a : between parenthesis. This means that it is looking for an exact match. Were not using it because were inserting different emails. 

### Bracket Expressions
Bracket Expressions are anything inside [] . In this case we have [a-z0-9_\.-] , [\da-z\.-] , and [a-z\.] . This shows what can be included in the email. a-z, will look for any letters a-z NOT capitolized, for that we would use A-Z. 0-9, looks for numbers anywhere from 0-9. _ - or special characters, are also included as viable options. Adding a ^ inside the brackets will tell it not to include the following information after it. The remaining  backslashes and backslash d will be under Character Classes.

### Character Classes
Character Classes will define a set of characters. The information from bracket expressions are considered character classes. Looking once again at [a-z0-9_\.-] , [\da-z\.-] , and [a-z\.], you will notice some other characters we have yet to go over. the period will match any characters except the newline character, \n. \d will match numerical digits like in our case 0-9. Some others not included in ours is \w(for alphanumeric charecters), and \s(for matching a single whitespace characters which also include tabs and line breaks)

### The OR Operator
The string doesnt always require certain information. In our case, [a-z0-9_\.-], it will look for a-z0-9 OR _-. A way to deal with this would be breaking it up using OR. you can take the string (efg):(hij) and convert it to (e|f|g):(h|i|j), now if you have fge:hij , they would now match.

### Flags
Flags can be added at the end of the snipit. added the letter g will make the regex test on a global search. the letter i will look for case insensitive, which will ignore case while searching for the information. And finally the letter m will do a multi-line search and will take ulti line information as multi- line information.

### Character Escapes
the backslash will helps stop the search from taking something literally, for instance, \{} adding the backslash before the curly bracket will tell it to look for character and not define a quantifier. If it does not have a backslash, it will consider it as a quantifier. If using this inside a bracket, it will lose its significance.

## Author
Maynardj123 
https://github.com/Maynardj123

