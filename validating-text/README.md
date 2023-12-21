# ![RegEx - Validating Text](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

# Validating Text in an <input>

Let’s take a look at an everyday, practical use for regular expressions - one that you can start applying to your apps pronto.

HTML5 `<input>` elements have a `pattern` attribute just for regex patterns.

If the text in the `<input>` does not **completely** match the regular expression:

- The submit button will not submit the form to the server.
- The `<form>` will have the `:invalid` CSS pseudo-class applied to it.

## Patterns - *Literal Characters*

The first type of characters within a regex pattern that we'll discuss are **literal characters**.

- A **literal** is the most basic of the regex characters. They are *literally* the character we want to match.
- The first regex we have put in our `<input>`, `pattern="Fred"`, has a pattern, `Fred`, consisting entirely of literal characters.

Type “Fred”, and you will see the form’s border turn green indicating a match!

- **Reminder:** We are looking at regex initially within the context of an HTML `<input>` element. If this were an ordinary regular expression, our pattern, `Fred`, would match the first occurrence of the letters `Fred` **anywhere** within a string, such as*Say hi to Fredrick, aka Fred, when you see him*.

## Patterns - *Character Class*

Next up is a **character class**. They tell the regex engine to match only one of several characters placed within square brackets.

- Let’s change our pattern to `gr[ae]y` and check it out!

You can use a hyphen inside of a character class to specify a range of characters. For example, `[5-9]` will match a single digit of 5 to 9.

- You can use more than one range too. This pattern, `[0-9a-fA-F]`, would match any single hexadecimal digit regardless of case.
- Character classes are great for matching frequently misspelled words like `li[cs]en[cs]e`.

<aside>
❓ What regular expression would you use to match your name, whether it is capitalized or not?

</aside>

## Negated Character Class

Putting a `^` (caret) symbol after the opening `[` means match any character **except** the character(s) in the brackets.

So, `p[^ua]` will match the letter `p` followed by any single character except `u` or `a`.

## Shorthand Character Classes

Because character classes are used so often, there are several *shorthand character classes* available. For example, instead of using `[0-9]` to match a digit, you can use `\d` instead.

Here are more shorthand character classes:

- **`\w`** will match any alphanumeric character, including digits and the underscore character.
- **`\s`** will match any “whitespace” character, including space, tab, newline, and carriage return.
- **`.`** (period) will match any character except line breaks.

Google will be your friend when working with regular expressions. Unless you frequently work with them; there’s no way to remember all this stuff!

## Negating Shorthand Character Classes

Interestingly, the uppercase versions of the previous shorthands match just the opposite of the lowercase versions:

- `\D` will match any character except a digit.
- `\W` will match anything but an alphanumeric character (and underscore).
- `\S` will match anything except space, tab, newline, or return.

## You Do (5 mins) 💪

Based upon what you’ve learned already, work with a group and:

**Write a regex pattern that will match: The word “File”, followed by a space and two uppercase letters from the alphabet, followed by a hyphen and three digits, except that the first of the three digits cannot be a zero.**

For example, this text would be a match: `File XY-123`

A solution is provided below, but try struggling with it together!

`File [A-Z][A-Z]-[1-9][0-9][0-9]`

Note that there is no shortcut character class to match a letter from the alphabet only, so we must use: `[a-z]` (lowercase), `[A-Z]` (uppercase), or `[a-zA-Z]` (upper or lowercase)