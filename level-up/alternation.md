# ![RegEx - Level Up - Alternation](./assets/hero.png)

tktk Optional student-facing level up content should be added here. Not all modules will have Level Up content - if it doesn't, the `level-up` directory should be deleted, and the **Level Up content** section in the main `README.md` file should be removed.

# Alternation

Alternation allows us to search for one of several characters or words easily.

Let’s say you want a single regex that will match any of these sentences:

- *I have a dog.*
- *I have a cat.*
- *I have a bird.*
- *I have a fish.*

This would do the trick:`/I have a (dog|cat|bird|fish)\./`.

## You Do (5 mins) 💪

**Write a regex that would match a CSS color hexadecimal (3 or 6 characters), such as`#f355Ac` or `#D39`**

- Solution
    
    ```
    /#([a-fA-F0-9]{6}|[a-fA-F0-9]{3})/
    ```
    
    **Why can’t we use the alphanumeric character shortcut `\w`, instead of the much longer `[a-fA-F0-9]`?**