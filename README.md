# Ashara's HTML Tag Regex Tutorial

Hello, my Name is Ashara Martinez and I'm an aspiring fullstack coding developer and I'm currently attending the fullstack bootcamp class at washington univeristy. In this .md file I will be explaining the specific reges in regards to the ones that have to do with matching an HTML tag.

## Summary

The regex /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/ is used to match an HTML tag. It captures the opening tag name, any attributes, and the content within the tag if present. It also matches the closing tag or a self-closing tag. Throughout this tutorial, we will explain the various components of this regex and provide examples to illustrate their usage.

## Table of Contents

- [Ashara's HTML Tag Regex Tutorial](#asharas-html-tag-regex-tutorial)
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

## Regex Components

When it comes to the specific regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` for matching an HTML tag, it consists of several essential components. In this tutorial, we will delve into each of these components and provide a detailed explanation for better understanding. The components covered include Anchors, Quantifiers, OR Operator, Character Classes, Flags, Grouping and Capturing, Bracket Expressions, Greedy and Lazy Match, Boundaries, Back-references, and Look-ahead and Look-behind. Let's explore each of these components in the following sections.

### Anchors

Anchors are used to match a specific position within the text. In this regex, we have two anchors:

^ - Start anchor: Matches the start of a line.
$ - End anchor: Matches the end of a line.
These anchors ensure that the regex matches the entire HTML tag and doesn't allow any additional characters before or after the tag.

### Quantifiers

Quantifiers specify the number of occurrences of a preceding element. In our regex, we have the following quantifiers:

+ - Matches one or more occurrences.
* - Matches zero or more occurrences.
These quantifiers are used to define the opening tag name ([a-z]+) and attribute values ([^<]+).

### OR Operator

The OR operator (|) allows you to match either one pattern or another. In our regex, the OR operator is used within a non-capturing group (?:...) to match either the tag content and closing tag or a self-closing tag.


### Character Classes

Character classes match a single character from a set of characters. In this regex, we have the character class [a-z], which matches any lowercase letter. It is used to match the opening tag name.

### Flags

Flags modify the behavior of the regex matching. In our regex /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/, there are no flags specified. However, depending on the programming language or tool you are using, you might have the option to include flags like case-insensitive matching (i) or global matching (g).

### Grouping and Capturing

Grouping and capturing allow you to treat multiple characters as a single unit and capture the matched content for later use. In our regex, we have the following groups:

### Bracket Expressions

Bracket expressions are used to match a single character from a specific set of characters. In our regex, we don't have explicit bracket expressions. However, the attribute values ([^<]+) are represented using a negated character class that matches any character except the angle bracket <.

### Greedy and Lazy Match

By default, quantifiers in regex are greedy, meaning they match as much as possible. In our regex, the quantifiers + and * are greedy. However, they are limited by the presence of other regex components. The tag content capturing group (.*) is greedy, but it is restricted by the requirement to match the closing tag.

### Boundaries

In our regex, we don't have explicit boundaries. However, the start anchor ^ and end anchor $ serve as implicit boundaries, ensuring that the regex matches the entire HTML tag.

### Back-references

Back-references allow you to refer to a previously captured group within the regex pattern. In our regex, we have a back-reference \1 within the closing tag pattern <\/\1>. This ensures that the closing tag matches the same tag name as the opening tag.

### Look-ahead and Look-behind

In our regex, we don't have explicit look-ahead or look-behind assertions.

## Author

This is the end of the tutorial, I hope you found it helpful, if you want to look at any of my github code/projects my github profile can be found within the following link.
https://github.com/Amartinez2075

Your welcome to use any of my code if it helps you with understanding or learning coding in general :3
