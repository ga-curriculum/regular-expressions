<h1>
  <span class="headline">Regular Expressions</span>
  <span class="subhead">Working with Special Characters</span>
</h1>

**Learning objective:** By the end of this lesson, students will understand how to use special characters as text within regular expressions.

## Escaping special characters

We've seen how certain characters such as `/*+?.[]{}`, have special meaning in regular expressions.

That being the case, how do we match these special characters as literal characters? For example, what if you wanted a pattern to match a number that includes a decimal point?

- To accomplish this, you have to *escape* the special character by preceding it with a `\` (backslash); for example, `\+` would match the plus symbol.
- Note that we do not have to escape special characters within a *character class* (square brackets). So, if you wanted to match a plus or minus sign, you could use this pattern:`[+-]`.

> 📚 *Escaping* characters can be necessary when using languages or technologies where certain characters are assigned special meaning, like in regex. Escaping a character strips the character of its special meaning, and makes it behave like any other character.

For example, this pattern: `What\?` would match the string `What?`.

## 🎓 You Do

Write the regular expression that would match a floating-point number with one more more digits on both sides of the decimal.
