<h1>
  <span class="headline">Regular Expressions</span>
  <span class="subhead">Alternation</span>
</h1>

**Learning objective:** By the end of this lesson, students will understand the purpose of the alternation operator in regular expressions.

## What is alternation?

Alternation allows us to search for one of several characters or words. It can be useful when you have multiple valid options that might be present in a string.

Let's say you want a single regex pattern that will match any of these sentences:

- I have a dog.
- I have a cat.
- I have a bird.
- I have a fish.

Using the alternation operator `|`, we could create the following pattern:

`I have a (dog|cat|bird|fish)\.`

This allows for a match to any of the four animals ('dog', 'cat', 'bird', or 'fish') within the sentence structure of "I have a ...".

## Implementing alternation

Let's implement an example of alternation in our HTML input.

We'll create a pattern to match a CSS hex color like `#f355Ac` or `#D39`. Alternation will be helpful here because CSS hex colors adhere to two common formats, one with ***six*** characters and another with ***three*** characters.

Change the input in your form to the following:

```html
<body>
  <form>
    <input type="text" required pattern="#([a-fA-F0-9]{6}|[a-fA-F0-9]{3})">
  </form>
</body>
```

Test the pattern in your browser!

Let's break down the code used here:

- **`#`**: This matches the `#` character, which is always the first character in a hex color code.
- **`([a-fA-F0-9]{6}|[a-fA-F0-9]{3})`**: This uses the alternation operator `|` to account for the two possible hex color formats.
