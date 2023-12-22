# ![RegEx - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand the role of regular expressions in programming.

## What are regular expressions?

RegEx, short for regular expression, is a **sequence of characters** that defines a pattern used to match and manipulate text in strings. 

RegEx is the standard approach for pattern matching, used across a variety of programming languages. It is commonly used to facilitate the functionality of word processors, text editors, and search engines. RegEx patterns can even be used for things like web scraping and validation.

RegEx is a powerful tool that may appear complex at first, but it's incredibly useful for a wide range of tasks.

# Regular expression patterns

Let's take a look at a real-world example of a regex pattern. 

Imagine your application needs an expression to match/validate a typical 10-digit phone number like `(310) 555-1212`. 

Here is an example of how that regex pattern could be implemented in JavaScript:

```javascript
/^\(\d{3}\)\s\d{3}-\d{4}$/
```