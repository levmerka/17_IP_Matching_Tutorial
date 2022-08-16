# IP Matching Tutorial
https://github.com/levmerka/17_IP_Matching_Tutorial.git 
### [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

 17th Challenge from the UT Coding Bootcamp: 

Regex: Matching and Validating IP Addresses

## Summary

Matching and validating IP addresses is an inherently critical process of the web. The utility of this regex is immeasurable and plays a role in countless applications used by millions all-day every day.

`\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b`  

for example, is a regex that accomplishes this. However, this particular regex will only find IP address from a search; not necessarily a valid one. It may turn up something written like: 000.000.000.000 which we know isn't valid. 
Something that would restrict the values to 0..255 would look like this: 

`\b(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b`

This is utilizing capture groups for individuals sets of number and incorporates them into the search pattern to refine results. This will be expounded upon further in the GIST.

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
First off, since regex's are literals we wrap them in (/)'s to signify or break out the pattern. 
This can be seen in both examples in the - [Summary Above](#summary)
### Anchors
An IP query similar to those above can turn up larger numbers if they are located within a larger string. We can validate that an input contains nothing but an IP address by adding some anchors to the front and rear of the pattern. 

`^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}
 (?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$`

Notice the (^) and the ($) at the biginning of the regex. 
The (^) declares that the results must contain an EXACT match to the pattern that follows it while the ($) restrains the results to the pattern that precedes it.
### Quantifiers
Additive in nature, Quantifiers are used to add additional runs of patterns or basically add relevant results in  variety of ways. 
In the example for anchors: 

`^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}
 (?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$`

 Notice the {3} after the first parenthises close. The {} quantifier tells the pattern preceding it to match the pattern a specified number of times. In our case with IP addresses this number is 3, leaving us with our initial IP address values.
### Grouping Constructs
Grouping Constructs allow us to "capture" a section of the pattern and apply it to the pattern following in a sense grouping different results together using (:)'s
Not all grouping construsts are capturing as in our case we see a (?) in front of our (:). The (?) declares the grouping to not capture and allow for more relevant data in this particular example.

`^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}
 (?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$`

 If we were to make this a capturing regex it would look more like:

 ^(?:[0-9a-fA-F]{1,4}:){7}[0-9a-fA-F]{1,4}$
### Bracket Expressions
By now, you've noticed all the number within brackets in the prior examples. These [] denote that the pattern will search for a match within the set range input. 
### Character Classes
Character Classes are used to define specific parts of the pattern to obtain better results.
In our IP regex's, the brackets used are a good example of a character class at work. Many more concise classes exist for alphabetic or alphanumeric strings, but as we are exclusively seeking numeric values the []'s suffice. 
### The OR Operator

### Flags
Flags are components added outside the /'s of a regex which add additional properties to the pattern.
Going back to our axample: 

`\b(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b`

  the \b is providing a boundary. This is what tells the regex to seek a match within a string that is no longer than what an IP address would be.
### Character Escapes
\'s are used to signify we want to escape the the characters so that the following charactar is not taken literally.
In:

`^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}
 (?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$`

 the \ before the (.) is our escape as it is telling the (.) to not be included in our pattern seeking the IP values. 
## Author
Mitchell Merka is currently enrolled in the UT Austin Coding Bootcamp
Github: https://github.com/levmerka