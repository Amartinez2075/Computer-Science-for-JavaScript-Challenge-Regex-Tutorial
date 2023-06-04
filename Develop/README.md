# Ashara's HTML Tag Regex Tutorial

Hello, my Name is Ashara Martinez and I'm an aspiring fullstack coding developer and I'm currently attending the fullstack bootcamp class at Washington University. In this .md file, I will be explaining the specific regex in regards to the ones that have to do with matching an HTML tag.

## Summary

The regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` is used to match an HTML tag. It captures the opening tag name, any attributes, and the content within the tag if present. It also matches the closing tag or a self-closing tag. Throughout this tutorial, we will explain the various components of this regex and provide examples to illustrate their usage.

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
  - [Example 6: `<h1>Heading</h1>`](#example-6-h1headingh1)
- [Bracket Expressions](#bracket-expressions)
  - [Example 7: `<img src="image.jpg" alt="Sample image">`](#example-7-img-srcimagejpg-altsample-image)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
  - [Example 8: `<div><p>Some text</p></div>`](#example-8-divpsome-textpdiv)
- [Boundaries](#boundaries)
  - [Example 9: `<span>Some text</span>`](#example-9-spansome-textspan)
- [Back-references](#back-references)
  - [Example 10: `<h2>Subheading</h2>`](#example-10-h2subheadingh2)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
  - [Author](#author)

---

## Regex Components

When it comes to the specific regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` for matching an HTML tag, it consists of several essential components. In this tutorial, we will delve into each of these components and provide a detailed explanation for better understanding. The components covered include Anchors, Quantifiers, OR Operator, Character Classes, Flags, Grouping and Capturing, Bracket Expressions, Greedy and Lazy Match, Boundaries, Back-references, and Look-ahead and Look-behind. Let's explore each of these components in the following sections.

---

### Anchors

Anchors are used to match a specific position within the text. In this regex, we have two anchors:

- `^` - Start anchor: Matches the start of a line.
- `$` - End anchor: Matches the end of a line.

These anchors ensure that the regex matches the entire HTML tag and doesn't allow any additional characters before or after the tag.

Example 1: `<div>Some content</div>`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will match the entire HTML tag `<div>Some content</div>`.

---

### Quantifiers

Quantifiers specify the number of occurrences of a preceding element. In our regex, we have the following quantifiers:

- `+` - Matches one or more occurrences.
- `*` - Matches zero or more occurrences.

These quantifiers are used to define the opening tag name `([a-z]+)` and attribute values `([^<]+)`.

Example 2: `<p class="highlight">Some paragraph</p>`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will match the opening tag `<p class="highlight">`.

---

### OR Operator

The OR operator (`|`) allows you to match either one pattern or another. In our regex, the OR operator is used within a non-capturing group `(?:...)` to match either the tag content and closing tag or a self-closing tag.

Example 3: `<p>Some paragraph</p>`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will match the closing tag `</p>`.

---

### Character Classes

Character classes match a single character from a set of characters. In this regex, we have the character class `[a-z]`, which matches any lowercase letter. It is used to match the opening tag name.

Example 4: `<span>Some text</span>`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will match the opening tag `<span>`.

---

### Flags

Flags modify the behavior of the regex matching. In our regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`, there are no flags specified. However, depending on the programming language or tool you are using, you might have the option to include flags like case-insensitive matching (`i`) or global matching (`g`).

Example 5: In JavaScript, you can use the `i` flag to perform a case-insensitive match. The regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/i` will match both uppercase and lowercase HTML tags.

```javascript
const regex = /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/i;

console.log(regex.test('<DIV>This is a div.</DIV>')); // Output: true
console.log(regex.test('<span>This is a span.</span>')); // Output: true
```

# Grouping and Capturing

Grouping and capturing allow you to treat multiple characters as a single unit and capture the matched content for later use. In our regex, we have the following groups:

## Example 6: `<h1>Heading</h1>`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will capture "h1" in Group 1 and "Heading" in Group 2.

# Bracket Expressions

Bracket expressions are used to match a single character from a specific set of characters. In our regex, we don't have explicit bracket expressions. However, the attribute values `([^<]+)` are represented using a negated character class that matches any character except the angle bracket `<`.

## Example 7: `<img src="image.jpg" alt="Sample image">`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will match the attribute values "image.jpg" and "Sample image".

# Greedy and Lazy Match

By default, quantifiers in regex are greedy, meaning they match as much as possible. In our regex, the quantifiers `+` and `*` are greedy. However, they are limited by the presence of other regex components. The tag content capturing group `(.*)` is greedy, but it is restricted by the requirement to match the closing tag.

## Example 8: `<div><p>Some text</p></div>`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will match the opening tag `<div>` and the closing tag `</div>` individually, and the tag content captured will be `<p>Some text</p>`.

# Boundaries

Boundaries are used to match specific positions in the text. In our regex, we don't have explicit boundary indicators. However, the combination of start and end anchors `^` and `$` ensures that the regex matches the entire HTML tag without any additional characters before or after.

## Example 9: `<span>Some text</span>`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will match the entire HTML tag `<span>Some text</span>`.

# Back-references

Back-references allow you to match the same content as a previously captured group. In our regex, the back-reference `\1` is used to match the same opening tag name captured in Group 1. It ensures that the closing tag matches the corresponding opening tag.

## Example 10: `<h2>Subheading</h2>`

In this example, the regex `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/` will match the closing tag `</h2>`.

# Look-ahead and Look-behind

Look-ahead and look-behind assertions allow you to match a pattern only if it is followed or preceded by another pattern, without including the matched content in the final result. In our regex, we don't have look-ahead or look-behind assertions.

## Author

This tutorial was created by Ashara Martinez, an aspiring full-stack coding developer currently attending the full-stack bootcamp class at Washington University.

