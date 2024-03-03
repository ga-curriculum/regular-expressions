# ![Regular Expressions - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand the role of regular expressions in programming.

## What are regular expressions?

Regex, short for Regular Expression or Regular Expressions, is a **sequence of characters** that defines a pattern used to match and manipulate text in strings.

Regex is the standard approach for *pattern matching*, used across various programming languages. It is commonly used to facilitate the functionality of word processors, text editors, and file system searches. Regex patterns can even be used for web scraping and form input validation.

Regex may appear complex at first, but it's a powerful tool that's incredibly useful for a wide range of tasks.

> 📚 *Pattern matching* helps to identify characters that match a sequence of defined characters.

## Regular expression patterns

Let's take a look at a real-world example of a regex pattern.

Imagine your application needs an expression to match/validate a 10-digit phone number like `(310) 555-1212`.

Here is an example of how that regex pattern could be implemented in JavaScript:

```javascript
/\(\d{3}\) \d{3}-\d{4}/
```

Don't worry if this looks overwhelming or indecipherable! It'll make more sense as we dive into some of the basic patterns.
