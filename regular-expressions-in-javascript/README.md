# ![RegEx - Regular Expressions in JavaScript](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

# Regular Expressions in JavaScript

Before we begin to work with more complex regular expressions, let’s use the console in Chrome’s DevTools to check them out using JavaScript.

In JavaScript, regular expressions are special objects that we can create using a *regular expression literal* or the *RegExp()* constructor function.

The literal syntax uses forward slashes to delimit the regex:

```jsx
const re = /cats?/
```

The literal syntax is the best option if you know the pattern you want to use in advance. However, using the constructor approach allows you to pass in a string variable to create a regex dynamically:

```jsx
const str = "cats?"
const re = new RegExp(str)
```

A regex object has a `test()` method that returns `true` if there is at least one match:

```jsx
const re = /cats?/
re.test('fatcat')   // returns true
```

## You Do (3 mins) 💪

- **Create a JS regex in the console that would match a phone number with the following format:`(###) ###-####`**
    
    Hint, the parenthesis are *special characters*, **so we have to _________ them**.
    
- **Use the `test` method on the regex to test some phone numbers.**

A solution is provided below, but try struggling with it together!

- Solution
    
    Note the use of backslashes to escape the parens:
    
    ```
    var re = /\(\d{3}\) \d{3}-\d{4}/;
    ```
    

[These docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) discuss working with regular expressions in JavaScript, including the methods on *Strings* as well as the `test()` and `exec()` methods of the *regular expression* object.

[exec](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec)
A RegExp method that executes a search for a match in a string. It returns an array of information.

[test](https://www.notion.so/test-25832277026c471babc0c871770a3f3f?pvs=21)
A RegExp method that tests for a match in a string. It returns true or false.

[match](https://www.notion.so/match-e124b69a3d9c407fba5f7946a4fbeb44?pvs=21)
A String method that executes a search for a match in a string. It returns an array of information or null on a mismatch.

[search](https://www.notion.so/search-cb78be3e62f743cdb1736d2b7b94069d?pvs=21)
A String method that tests for a match in a string. It returns the index of the match, or -1 if the search fails.

[replace](https://www.notion.so/replace-f8360a64a87942f8b30a4a7a329fed88?pvs=21)
A String method that executes a search for a match in a string, and replaces the matched substring with a replacement substring.

[split](https://www.notion.so/split-a730b632a4d54bf19168fcbac079894d?pvs=21)
A String method that uses a regular expression or a fixed string to break a string into an array of substrings.



# Escaping Special Characters

We’ve seen how certain characters such as these, `/*+?.[]{}`, have special meaning in regular expressions.

That being the case, how do we match these special characters as literal characters? For example, what if you wanted a pattern to match a number that includes a decimal point?

- To accomplish this, you have to *escape* the special character by preceding it with a `\` (backslash); for example, `\+` would match the plus symbol.
- Note that we do not have to escape special characters within a *character class* (square brackets). So, if you wanted to match a plus or minus sign, you could use this pattern:`[+-]`.

## You Do (3 mins) 💪

1. **Write the regular expression that would match a floating-point number with one or more digits on both sides of the decimal.**
2. **Write the regular expression that would match this text: `What?`**

A solution is provided below, but try struggling with it together!

- Solution
    1. `\d+\.\d+`
    2. `What\?`