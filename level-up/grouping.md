# ![RegEx - Level Up - Grouping](./assets/hero.png)

tktk Optional student-facing level up content should be added here. Not all modules will have Level Up content - if it doesn't, the `level-up` directory should be deleted, and the **Level Up content** section in the main `README.md` file should be removed.


# Grouping

Parentheses are used inside regular expressions to create groups that can then have a quantifier applied to the group. Whereas the square brackets character class, `[]`, represents a **single** character to match, the parentheses `()` represent a **group** of characters to match.

Let’s say we wanted to match a computer’s IP Address. Ignoring the fact that we should limit the numbers to between 0 and 255, we could write something like this: `/\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}/`

- But using grouping we can shorten this to: `/(\d{1,3}\.){3}\d{1,3}/`

## Exercise (2 mins) 💪

**Write a regular expression that would match this string: `hey!hey!hey!`**

- Solution
    
    ```
    /(hey!){3}/
    ```