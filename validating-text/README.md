<h1>
  <span class="headline">Regular Expressions</span>
  <span class="subhead">Validating Text</span>
</h1>

**Learning objective:** By the end of this lesson, students will understand how to apply regular expressions to HTML `<input>` elements for text validation.

## Validating text in an `<input>` element

HTML `<input>` elements have a `pattern` attribute specifically designed for regex patterns. The `pattern` attribute prevents a form from being submitted if the text in the `<input>` does not ***completely*** match the provided regular expression.

Several types of patterns can be used with the `pattern` attribute. Let's take a look at a few examples.

### Literal characters

The first pattern we'll discuss is literal characters. A literal is the most straightforward of the regex characters. They are ***literally*** the characters we want to match.

Let's implement this pattern in HTML. Add the following `<form>` inside the `<body>` of `index.html`:

```html
<body>
  <form>
    <input type="text" required pattern="Fred">
  </form>
</body>
```

The `pattern` attribute of our `<input>` has a regex pattern of `Fred`, consisting entirely of literal characters. This ensures that the only valid value in the input is a string reading `Fred`. Type `Fred` in the input now. The form's border will turn from yellow to green, indicating a match!

The `required` attribute of the `<input>` element means that the input must have content in it before it is considered valid.

> 🧠 Note that we are looking at regex initially within the context of an HTML `<input>` element.
>
> If this were an ordinary regular expression, our pattern, `Fred`, would match the first occurrence of the letters `Fred` ***anywhere*** within a string, such as ***Say hi to Fredrick, also known as Fred, when you see him***.

## Character class

Next up is a character class. This will match only one of the multiple characters placed within square brackets.

Let's change the value in our `pattern` attribute to `gr[ae]y` and check it out:

```html
<body>
  <form>
    <input type="text" required pattern="gr[ae]y">
  </form>
</body>
```

The `<input>` will accept 'gray' or 'grey' as valid inputs with this pattern. This is because the character class `[ae]` matches either an `a` or an `e` (but not both simultaneously!). Try typing `gray`, `grey`, or any other text into the input and observe the behavior.

> ❓ What regular expression would you use to match your name, whether it is capitalized or not?

### Ranges in a character class

You can use a hyphen inside of a character class to specify a range of characters. For example, `[5-9]` will match a single digit of 5, 6, 7, 8, or 9. You can also use more than one range. The pattern, `[0-9a-fA-F]`, would match any single hexadecimal digit regardless of case.

> 🏆 Character classes are great for matching frequently misspelled words like `li[cs]en[cs]e`.

### Negated character class

Putting a `^` (caret) symbol after the opening `[` will match any character ***except*** the character(s) in the brackets.

For example, `p[^ua]` will match the letter `p` followed by any single character except `u` or `a`.

### Shorthand character classes

Because character classes are used so often, several ***shorthand character classes*** are available. For example, instead of using `[0-9]` to match a digit, you can use `\d` instead.

Here are some other helpful shorthand character classes:

- `\d` will match any digit.
- `\w` will match any alphanumeric character, including digits and the underscore character.
- `\s` will match any "whitespace" character, including space, tab, newline, and carriage return.
- `.` (period) will match any character except line breaks.

> 💡 Google or AI assistants will be your friend when working with regular expressions. Unless you frequently work with them, you won't remember all this!
>
> Apps also exist to help construct and decode regex patterns such as: [regex101](https://regex101.com/). If you do start writing regex more often, regex [cheat sheets](https://www.rexegg.com/regex-quickstart.html) can help as well

### Negating shorthand character classes

The uppercase versions of the previous shorthands match the opposite of the lowercase versions:

- **`\D`** will match any character except a digit.
- **`\W`** will match anything but an alphanumeric character (and underscore).
- **`\S`** will match anything except space, tab, newline, or return.

## 🎓 You Do

Write a regex pattern that will match the word `File`, followed by a space and two uppercase letters from the alphabet, followed by a hyphen and three digits, except that the first of the three digits cannot be a zero.

For example, this text would be a match: `File XY-123`

But this text would not: `File XY-023`, because the sequence of numbers starts with a `0`.

Hint: Note that there is no shortcut character class to match a letter from the alphabet only, so we must use `[a-z]` (lowercase), `[A-Z]` (uppercase), or `[a-zA-Z]` (upper or lowercase)
