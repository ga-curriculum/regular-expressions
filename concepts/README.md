# ![RegEx - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## What are Regular Expressions?

A **sequence of characters** that define a pattern used to search/match, and optionally replace, text in strings and files.

Grounded in Computer Science and used throughout computing by: 

- Programming languages
- Word processors & text editors
- System utilities like Unix’s `grep`

They are even handy for things like web scraping and validation! They're so comprehensive that they are their own computer language. 

# Regular Expression patterns

To get orientated, this is what a regular expression to match/validate a typical 10-digit phone number like `(310) 555-1212` looks like in JavaScript:

```jsx
/^\(\d{3}\)\s\d{3}-\d{4}$/
```

Crazy looking stuff - yes? Don’t sweat it. By the end of the lesson, this gibberish will all make sense.