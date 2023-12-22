# ![RegEx - Level Up - Alternation](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand the purpose of the alternation operator in regular expressions.

## What is alternation?

Alternation allows us to search for one of several characters or words. It can be useful when you have multiple valid options that might be present in a string.

Let’s say you want a single regex pattern that will match any of these sentences:

- *I have a dog.*
- *I have a cat.*
- *I have a bird.*
- *I have a fish.*

Using the alternation operator `|`, we could create the following pattern:

`/I have a (dog|cat|bird|fish)\./`

This allows the us to match any the words 'dog', 'cat', 'bird', or 'fish' within the sentence structure of "I have a ...". 

## Implementing alternation

Let's implement an example of alternation in JavaScript.

We'll create a regex object to match a CSS hex color like `#f355Ac` or `#D39`. Alternation will be useful here because CSS hex colors adhere to two common formats, one with **6** characters and another with **3** characters.

Add the following to `js/app.js`:

```javascript
// js/app.js
const cssRegex = /#([a-fA-F0-9]{6}|[a-fA-F0-9]{3})/;
```

Next, use the `test()` method to test out some hex colors: 

```javascript
// js/app.js
console.log(cssRegex.test('#f355Ac')); //  true
```

Let's breakdown the code used here:

- **`#`**: This matches the `#` character, which is always the first character in a hex color code.
- **`([a-fA-F0-9]{6}|[a-fA-F0-9]{3})`**: This uses the alternation operator `|` to account for the two possible hex color formats.