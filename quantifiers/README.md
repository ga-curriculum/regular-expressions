# ![RegEx - Quantifiers](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand the use cases for regex quantifiers.

## What are quantifiers?

In regex, quantifiers are special symbols or characters used to specify how many times a particular element should appear in a match. 

There are four different quantifiers:

1. **`{}`**: Sets a specific number or range of repetitions for the element that precedes it.
2. **`*`**: Matches the preceding element zero or more times.
3. **`+`**: Ensures the preceding element appears one or more times.
4. **`?`**: Indicates the preceding element may appear zero or one time, making it optional.

## The `{}` operator

Let's dive a bit deeper into the `{}` quantifier. These curly braces are used to specify the number of repetitions the preceding element should have in a string.

Take a look at the example below:

```javascript
\d{3}
```

Let's break down what we have here:

- `\d`: This is a regex character class that matches any digit (0-9).
- `{3}` The use of the `{3}` directly following `\d` specifies that **exactly three digits in a row** should be matched.

The `\d{3}` regex pattern will match any sequence of exactly three digits, like "123", "456", or "789". It will not accept sequences with more or less than three digits. This makes it useful for matching sequences of numbers, like an area code in a phone number.

> 🚨 Note that regular expressions by default are “greedy”; that is, they will match as many characters as possible (longest possible match).

## Implementing a quantifier

Let's see how a quantifier can be applied in a real world scenario. We'll create a pattern that matches a street address.

The street address should adhere to the following structure:

- **Start with 1 to 5 digits (no leading zero)**
- **Followed by a space**
- **Followed by a street name beginning with a capital letter, then 1-n characters, including spaces.**

For example, a string reading `123 Main Street` would be considered a match.

Update your `<form>` in `index.html` with the following:

```html
<body>

  <form>
    <input 
      type="text" 
      pattern="[1-9][0-9]{0,4} [A-Z][a-z]+"
      placeholder="Enter a valid street address"
    >
    <button>Submit</button>
  </form>

</body>
```

Let's breakdown the code above:

- **`[1-9]`**: Matches the first digit of the street number, requiring it to be something other than `0`.
- **`[0-9]{0,4}`**: Matches up to four additional digits, making the total number of digits in the street number between one and five.
- **` `**: Requires there to be a space after the street number.
- **`[A-Z]`**: Requires the street name to start with a capital letter.
- **`[a-z]`**: Requires character following the first letter of the street name to be lower case.
- **`+`**: Requires that the preceding lower case character appears one or more times in the string.

All of these individual character classes and quantifiers are concatenated to form a single pattern that the input must adhere to. 