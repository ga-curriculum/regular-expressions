# ![Regular Expressions - Used in JavaScript](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to apply regular expressions in JavaScript.

## Regular expressions in JavaScript

In JavaScript, regular expressions are objects we can create using a regular expression literal or the `RegExp()` constructor function. See [MDN's documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) for more detail.

The literal syntax uses forward slashes (`/`) to *delimit* the regex:

```javascript
const regexLiteral = /cat/;
```

> 📚 In the context of regular expressions, *delimit* means to mark the boundaries of the pattern.

The literal syntax is the best option if you know the pattern you want to use in advance. However, using the constructor approach allows you to pass in a string variable to create a regex dynamically:

```javascript
const str = 'llama';
const regex = new RegExp(str);
```

A regex object has a `test()` method that returns `true` if there is at least one match:

```javascript
console.log(regexLiteral.test('fatcat')); // prints: true
console.log(regex.test('fatcat')); // prints: false
```

## Implementing regular expressions in JavaScript

Let's return to an earlier example and create a regex object to match a phone number.

The phone numbers should adhere to the following format:

```plaintext
(###) ###-####
```

Add the following to the `js/app.js` file:

```javascript
const phoneNumRegex = /\(\d{3}\) \d{3}-\d{4}/;
```

Next, use the `test()` method to test out some phone numbers:

```javascript
console.log(phoneNumRegex.test('(800) 222-5555')); // prints: true
```

> 💡 Notice the use of backslashes to escape special characters in our regex.

## JavaScript methods for regular expressions

Below, you'll find a list of JavaScript methods that can utilize regular expressions:

| Method | Description |
| ------ | ----------- |
| [`exec()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec)       | A `RegExp` method that executes a search for a match in a string. It returns an array of information.                             |
| [`test()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test)       | A `RegExp` method that tests for a match in a string. It returns true or false.                                                   |
| [`match()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match)     | A `String` method that executes a search for a match in a string. It returns an array of information or null on a mismatch.       |
| [`search()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search)   | A `String` method that tests for a match in a string. It returns the index of the match or -1 if the search fails.                |
| [`replace()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) | A `String` method that executes a search for a match in a string and replaces the matched substring with a replacement substring. |
| [`split()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)     | A `String` method that uses a regular expression or a fixed string to break a string into an array of substrings.                 |
