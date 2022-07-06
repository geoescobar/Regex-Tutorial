# Regex Tutorial: Matching a URL 

Regex which is short for Regular Expressions are a series of special characters that define a search pattern. 

## Summary

While the series of characters may look like random buttons clicked on a keyboard they are actually searching for patterns for validation. We're going to talk about how Regex can be used in validating URL's. 

Below is an example of how you can take a regex string and turn it into a variable:

`const urlReader = /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`




## Table of Contents

- [Demo](#demo)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Demo 
- Check out this QR Generator project I created. This requires a valid URL to create the code. Using the URL regex we are able to validate the input to determine if it's a URL or not. 

   - [Repo](https://github.com/geoescobar/QR-Code-Generator/blob/main/assets/script.js)
   - [Demo](https://geoescobar.github.io/QR-Code-Generator/)




## Regex Components
In JavaScript, regex is considered a literal. Due to that the pattern must be wrapped in forward slash characters `(/)`.



 

### Anchors
- The `^` and `$` characters are both anchors.
- `^` states that a string begins with the characters that follow it. It is important to pay attention to what is passed as it is also case sensitive. 
- `$` states that a string ends with the character that precedes it. 

### Quantifiers
- Quantifiers set limits of the string that your regex matches. They always look got the most possible outcomes as long as they are within the pattern.

- Below are examples of quantifiers and what they do: 
   - `*`— Matches the pattern zero or more times

   - `+`— Matches the pattern one or more times

   - `?`— Matches the pattern zero or one time

   - `{}`— Curly brackets can provide three different ways to set limits for a match:

   - `{ n }`— Matches the pattern exactly n number of times

   - `{ n, }`— Matches the pattern at least n number of times

   - `{ n, x }`— Matches the pattern from a minimum of n number of times to a maximum of x number of times

### Grouping Constructs
- As expressions grow and become more complex you may want to check multiple parts of the string to determine if the different sections are fulfilled. This is when you would use a grouping construct. 

- You group sections using parantheses `(())` and each section within the parent is called a subexpression.
  - EX: `(abc):(123)`


### Bracket Expressions
- Anything inside the square brackets represents the range of characters that you are trying to match. 
- They are also viewed as positive character groups because they are the characters we want to include. 
- They are set to what you need but they can be formatted as below:
   - `[a-z]`
   - `[0-9]`
   - `[_-]`

### Character Classes
- Character classes in regex define a set of characters. 
- Some character classes can look like the ones below: 
  - `.` - Matches any character except the newline character 
  - `\d` - Matches any Arabic numeral digit. It is also equivalent to the bracket expression `[0-9]`
  - `\w` - \w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore. This is equivalent to the bracket expression `[A-Za-z0-9_]`
  - `\s` - Matches a single whitespace character & it also includes tabs and line breaks
  

### The OR Operator
- Since bracket expressions don't require the string to meet all the requirements in the pattern, you'll often want to add an OR Operator outside bracket expressions within constructs. 
- Using the example from constructs we can demonsttrate how that would look:
  `(abc):(123)` => `(a|b|c):(1|2|3)`
  - Now `abc:123` & `cba:321` would match. Even `a:1`, `2:b`, & `3:c` would work.
  - These would not work `321:abc` & `1:a`

### Flags
- As a literal, regex must be wrapped in slash characters. This isn't always the case. There is one exception - Flags! 
- They are placed at the end, after the second slash of regex. 
- Flags define additional functionality/ limits. 
- Below are the types of flags: 
   - `g` - Global search 
   - `i` - Case
   - `m` - Multi-line search 

### Character Escapes
- In regex the backslash is used as an escape for characters. If not included they would be interpreted literally. 
- Curly braces are used to begin a quantifier but adding the backslash would tell the regex to look for the open curly brace character to define the quantifier. 
- Not just the backslash but all specal characters lose their significance inside bracket expressions so it's something to look out for.

## Author

Full Stack Web Developer - Passionate about coding and continuing to learn. Check out my [GitHub](https://github.com/geoescobar)! 
