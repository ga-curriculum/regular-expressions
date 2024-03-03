# ![ - Level Up - Anchors and Boundaries](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand the benefits of anchors and boundaries for more precise pattern matching.

## What are anchors and boundaries?

Anchors and boundaries are unique because they don't match a character; instead, they match a *position*. They allow us to write patterns that match strings that contain only the characters we are interested in, and only if they are isolated in the way we want them to be.

- **`^`**: This symbol is used to match the start of the line. This is very useful for processing a file containing multiple lines.
- **`$`**: This symbol matches the end of the line.

Without boundaries, the regex `/dog/` will return *true* when tested against any of these strings: "dog", "dogs", and "My dog is named Spot". However, the regex `/^dog$/` will match only the string "dog" when no other text is on the line.

## Implementing anchors and boundaries

Let's test the pattern `cat` with anchors (`/^cat$/`) and without (`/cat/`) against the strings "cat" and "catsup".

There is also `\b`, which matches a position called a *word boundary*. For example, `\b` will match any of the following:

- Before the first character in the string.
- After the last character in the string.
- Between two characters in the string, where one character is a word character, and the other is a non-word character such as a space, tab, or newline.

`\b` allows us to search for whole words only.

Let's see how we could use the string `match()` method to return the matches by passing in a regex.

First, we'll try it with no word boundary. In your `js/app.js` file, add:

```javascript
const noBoundary = /cat/g;
const noBoundaryMatches = 'The cat ate the catsup'.match(noBoundary);
console.log(noBoundaryMatches); // ['cat', 'cat']
```

Now, let's try it using a word boundary:

```javascript
const withBoundary = /\bcat\b/g;
const withBoundaryMatches = 'The cat ate the catsup'.match(withBoundary);
console.log(withBoundaryMatches); // ['cat']
```

> 💡 The `g` at the end of the regex is the *global* flag, and it tells the regex to search for all matches, not just the first.
