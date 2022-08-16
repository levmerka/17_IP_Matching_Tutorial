# IP Matching Tutorial
### [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

 17th Challenge from the UT Coding Bootcamp: 

Regex: Matching and Validating IP Addresses

## Summary

<!-- Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary. -->
Matching and validating IP addresses is an inherently critical process of the web. The utility of this regex is immeasurable and plays a role in countless applications used by millions all-day every day.
\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b , for example, is a regex that accomplishes this. However, this particular regex will only find IP address from a search; not necessarily a valid one. It may turn up something written like: 000.000.000.000 which we know isn't valid. 
Something that would restrict the values to 0..255 would look like this: 

\b(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.
  (25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b

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

### Anchors

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

<!-- A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile) -->