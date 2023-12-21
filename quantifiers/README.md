# ![RegEx - Quantifiers](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## What are quantifiers?

In the previous exercise/solution, we repeated the same character classes when we wanted to match more than one. Well, there’s a better way: using **quantifiers**.

There are four different quantifiers:

- **`{}`**
- `*`
- **`+`**
- **`?`**

Let’s see how they work.

## Quantifiers - `{}`

We use curly braces to specify a specific quantity or range of quantities, to repeat a literal character, character class, etc.

- For example, `\d{3}` would match three digits.

**What regex pattern could you use to match a social security number with this format:
`###-##-####`**

We can also specify a range like `[A-Z]{1,5}`, which would match between 1 and 5 capital letters.

- A range from a number to infinity can be created by leaving off the second number, such as this `{5,}`.

Note that regular expressions by default are “greedy”; that is, they will match as many characters as possible (longest possible match).

## Other Quantifiers

In addition to the `{min,max}` quantifier, there are repetition operators:

- `*` - the star symbol will match the preceding character class zero or more times.
- **`+`** - the plus symbol will match the preceding character class one or more times.
- **`?`** - the question mark will match the preceding character class zero or one time.

<aside>
❓ What are **the curly brace equivalents for each of the above repetition operators (`*`, `+`, and `?`)**

</aside>

## You Do (5 mins) 💪

With your group:

**Write a pattern that would match a street address where the address:** 

- **Starts with 1 to 5 digits (no leading zero)**
- **Followed by a space**
- **Followed by a street name beginning with a capital letter, then 1-n characters, including spaces.**

For example, this text would be a match:`123 Main Street`

A solution is provided below, but try struggling with it together!

- Solution
    
    ```
    [1-9][0-9]{0,4} [A-Z].+
    ```
    