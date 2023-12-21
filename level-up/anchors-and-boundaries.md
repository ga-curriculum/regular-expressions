# ![RegEx - Level Up - Anchors and Boundaries](./assets/hero.png)

# Anchors and Boundaries

Anchors and boundaries are unique because they don’t match a character; instead, they match a *position*.

They allow us to write patterns that match strings that contain only the characters we are interested in and only if they are isolated the way we want them to be.

- The `^` symbol is used to match the start of the line. This is very useful for processing a file containing multiple lines.
- The `$` symbol matches the end of the line.
- For example, without boundaries, the regex `/dog/` will return *true* when tested against any of these strings: “dog”, “dogs”, and “My dog is named Spot”. However, the regex `/^dog$/` will match only the string “dog” and when there is no other text in the line.

Let’s test the pattern, `cat`, with anchors (`/^cat$/`), and without (`/cat/`), against the strings “cat” and “catsup”.

There is also `\b`, which matches a position called a *word boundary*. For example, `\b` will match any of the following:

- Before the first character in the string
- After the last character in the string
- Between two characters in the string where one character is a word character, and the other is a non-word character such as a space, tab, or newline

The `\b` easily allows us to search for whole words only.

This is how could use the string `match()` method to return the matches by passing in a regex:

```jsx
// try with no word boundary
let re = /cat/g
let matches = "The catsup was eaten by the cat".match(re)
// ["cat", "cat"]

// try using word boundary
let re = /\bcat\b/g
let matches = "The catsup was eaten by the cat".match(re)
// ["cat"]
```

The `g` at the end of the regex is the *global* flag, and it tells the regex to search for all matches, not just the first.