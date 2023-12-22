# ![RegEx - Validating Text](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand how to apply regular expressions to HTML5 `<input>` elements for text validation.

# Validating text in an `<input>`

Let’s take a look at an everyday, practical use for regular expressions - one that you can start applying to your apps immediately.

HTML5 `<input>` elements have a `pattern` attribute specifically designed for regex patterns. The `pattern` attribute prevents a form from being submitted if text in the `<input>` does not **completely** match the provided regular expression. 

Several types of patterns can be used with the `pattern` attribute. Let's take a look at a few examples.

### Literal characters

The first pattern we'll discuss is **literal characters**. A **literal** is the most straightforward of the regex characters. They are *literally* the character we want to match. 

Let's implement this pattern in HTML5. 

Add the following `<form>` to the `body` of `index.html`:

```html
<body>
  
  <form>
    <input type="text" required pattern="Fred">
    <button>Submit</button>
  </form>

</body>
```

The `pattern` attribute of our `<input>` has a regex pattern of `Fred`, consisting entirely of literal characters. This ensures that the only valid input for our `<form>` is a string reading `Fred`. Try submitting the `<form>` after entering in something other than `Fred`. You should see a message indicating that the submitted text is invalid.

> 🧠 We are looking at regex initially within the context of an HTML `<input>` element. If this were an ordinary regular expression, our pattern, `Fred`, would match the first occurrence of the letters `Fred` **anywhere** within a string, such as *Say hi to Fredrick, aka Fred, when you see him*.

## Character class

Next up is a **character class**. This tells the regex engine to match only one of several characters placed within square brackets.

Let’s change the value in our `pattern` attribute to `gr[ae]y` and check it out:

```html
<body>
  
  <form>
    <input type="text" required pattern="gr[ae]y">
    <button>Submit</button>
  </form>

</body>
```

With this pattern, the `<input>` will accept either "gray" or "grey" as valid inputs. This is because the character class `[ae]` matches either an `'a'` or an `'e'`. Try typing "gray", "grey", or other variations into the form and observe the behavior.

### Ranges in a character class

You can use a hyphen inside of a character class to specify a **range of characters**. For example, `[5-9]` will match a single digit of 5 to 9. You can also use more than one range. This pattern, `[0-9a-fA-F]`, would match any single hexadecimal digit regardless of case.

> 🏆 Character classes are great for matching frequently misspelled words like `li[cs]en[cs]e`.

### Negated character class

Putting a `^` (caret) symbol after the opening `[` means match any character **except** the character(s) in the brackets.

For example, `p[^ua]` will match the letter `p` followed by any single character except `u` or `a`.

### Shorthand character classes

Because character classes are used so often, there are several *shorthand character classes* available. For example, instead of using `[0-9]` to match a digit, you can use `\d` instead.

Here are some other useful shorthand character classes:

- **`\w`** will match any alphanumeric character, including digits and the underscore character.
- **`\s`** will match any “whitespace” character, including space, tab, newline, and carriage return.
- **`.`** (period) will match any character except line breaks.

> 😎 Google will be your friend when working with regular expressions. Unless you frequently work with them; there’s no way to remember all this stuff!

### Negating shorthand character classes

Interestingly, the uppercase versions of the previous shorthands match just the opposite of the lowercase versions:

- **`\D`** will match any character except a digit.
- **`\W`** will match anything but an alphanumeric character (and underscore).
- **`\S`** will match anything except space, tab, newline, or return.