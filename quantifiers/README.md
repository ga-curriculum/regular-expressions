<h1>
  <span class="headline">Regular Expressions</span>
  <span class="subhead">Quantifiers</span>
</h1>

**Learning objective:** By the end of this lesson, students will understand the use cases for regex quantifiers.

## What are quantifiers?

In regex, quantifiers are special symbols or characters that specify how many times a particular element should appear in a match.

There are four different quantifiers:

1. **`{}`**: Sets a specific number or range of repetitions for the preceding element.
2. **`*`**: Matches the preceding element zero or more times.
3. **`+`**: Ensures the preceding element appears one or more times.
4. **`?`**: Indicates the preceding element may appear zero or one time, making it optional.

## The `{}` operator

Let's dive a bit deeper into the `{}` quantifier. These curly braces specify the number of repetitions the preceding element should have in a string.

Take a look at the example below:

```plaintext
\d{3}
```

Let's break down what we have here:

- **`\d`**: This regex character class matches any digit (0-9).
- **`{3}`**: The `{3}` directly following `\d` specifies that **exactly three digits in a row** should be matched.

The `\d{3}` regex pattern will match any sequence of exactly three digits, like "123", "481", or "064". It will not accept sequences with more or less than three digits. This makes it useful for matching sequences of numbers, like an area code in a phone number.

We can also specify a range like `[A-Z]{1,5}`, matching between 1 and 5 capital letters.

- A range from a number to infinity can be created by leaving off the second number, such as this `{5,}`.

> 🧠 Note that regular expressions, by default, are greedy; that is, they will match as many characters as possible. An example of this is `{5,}` as demonstrated above.

## Implementing a quantifier

Let's see how a quantifier can be applied in a real-world scenario. We'll create a pattern that matches a specific type of street address.

The street address should adhere to the following structure:

- Start with 1 to 5 digits (but may not start with zero).
- Followed by a space.
- Followed by a street name beginning with a capital letter.
- Followed by at least one more space, upper case character, or lower case character.

For example, a string reading `123 Main Street` ***would*** be considered a match.

A string reading `01 My Way` ***would not*** be considered a match because it starts with a `0`.

A string reading `1701 12th St` ***would not*** be considered a match because the street name does not start with a capital letter.

A string reading `201 A` ***would not*** be considered a match because there are no more letters or spaces after the first capital letter of the street name.

Update your `<form>` in `index.html` with the following:

```html
<body>
  <form>
    <input type="text" required pattern="[1-9]\d{0,4} [A-Z][A-Za-z ]+">
  </form>
</body>
```

Let's break down the code above:

- **`[1-9]`**: Matches the first digit of the street number, requiring it to be something other than `0`.
- **`\d{0,4}`**: Matches up to four additional digits, making the total number of digits in the street number between one and five. `[0-9]{0,4}` could also be used here!
- **` `**: Requires there to be a space after the street number.
- **`[A-Z]`**: Requires the street name to start with a capital letter.
- **`[A-Za-z ]`**: Requires the character following the first letter of the street name to be upper case, lower case, or be a space.
- **`+`**: Requires that the preceding upper/lower case or space character appears one or more times in the string.

All of these individual character classes and quantifiers are concatenated to form a single pattern that the input must adhere to.
