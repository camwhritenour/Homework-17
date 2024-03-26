# Match an Email RegEx Tutorial

Regular Expressions are a universal method of breaking down string data dynamically.  That may sound complicated, but it is less daunting than it sounds. RegEx uses specific sequences of characters, that are predefined, to create a search pattern. That search pattern then gets deciphered by RegEx and searches for a string that matches the search pattern. RegEx is mostly useful for validating input data to maintain uniformity in a database, or to retrieve groups of data that follow a similar pattern.

## Summary

A basic way to utilize RegEx is validating an email. I will be breaking down each part of the syntax and why it is neccesary for the functionality we are looking for.  The code snippet below is checking a string to make sure that not only each piece of an email address is present, but also that each piece conatains valid characters.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)

## Regex Components
In this example we are creating a literal search pattern using RegEx. Since this is the case we must wrap the pattern in slash characters. Every RegEx search pattern is made up of multiple different components. Below I have listed the various components, which we will go over one by one.

### Anchors
In our example we used both `^` and `$` at the beginning and end of our pattern. These are both considered anchors. 

The `^` anchor searches for a string that begins with the characters that follow it. This can be done two ways. The first is more basic: `^cam` would match "cam" and "cameron", but not "Cam" or "Cameron". The other, the one that we used in our example creates a range of possible matches using bracket expressions. 

The `$` anchor signifies the end of the string.

### Quantifiers
Quantifiers in RegEx are used to specify how many instances of a character, group, or character class must be present. In our example, we are using the `+` and `{2,6}` quantifiers. 

The `+` is used to connect different groups of characters together and also declares that at least one of characters matching the given expression are expected. We are using it to join the 3 elements of an email; email-name, @email-service, and .com. 

The `{2,6}` is used to signify that only 2-6 characters are expected to match the given bracket expression. We are using it to match the domain extention.

### Grouping Constructs
Creating groups is very important for more complex strings such as an email address. Each group serves a purpose and has specific criteria associated with it, in order to form a vaid email address.  

Group 1 captures the email name, which the expression consists of: `([a-z0-9_\.-]+)`. 

Group 2 captures the email service name, which consists of: `([\da-z\.-]+)`. 

Group 3 captures the domain extention, which the expression consists of: `([a-z\.]{2,6})`.

### Bracket Expressions
Bracket Expressions are used to define a range of valid characters in an expression.  

In this example we used `[a-z0-9_\.-]` for the email name validation. This matches any letter a-z(case sensitve), any number 0-9, and also the characters `_`, `.`, `-`. 

We also used `[\da-z\.-]` for the email service name validation. This matches a single digit 0-9, any letter a-z(cs), and the characters `.` and `-`. 

The last expression we used was `[a-z\.]` for the domain extention validation. This matches any character a-z(cs), and the character `.`.

### Character Classes
Character classes are predefined groups of characters. In this example we only used one, `\d`. This matches a single digit 0-9, so "2" would match but not "25".

## Author

I am a young developer named Cameron Whritenour, you can view more of my projects here: 
https://github.com/camwhritenour
