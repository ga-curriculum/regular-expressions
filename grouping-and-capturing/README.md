<h1>
  <span class="headline">Regular Expressions</span>
  <span class="subhead">Grouping and Capturing</span>
</h1>

**Learning objective:** By the end of this lesson, students will understand the benefits of grouping and capturing in regular expressions.

## What is grouping?

Grouping in regex involves using parentheses to treat multiple characters as a single unit.

Parentheses are used to create groups with a quantifier applied to the group. Whereas the square brackets character class, `[]`, represents a ***single*** character to match, the parentheses `()` represent a ***group*** of characters to match.

One benefit of grouping in regex is creating more concise and manageable patterns.

Let's say we want to match a string that repeats a certain pattern. Take the string `'hey!hey!hey!'` as an example.

Without grouping, you would have to write out the pattern for each repetition:

```javascript
/hey!hey!hey!/
```

However, with grouping, we can simplify this by grouping the repeated pattern and then specifying how many times it should repeat:

```javascript
/(hey!){3}/
```

## What is capturing?

Parentheses can also be used to define **capture** groups. Capturing is when matched text is "captured" into numbered groups. These groups can then be reused with a process called *backreferencing*.

> 📚 *Backreferencing* in regex is a technique of reusing the text from capture groups to match other characters.

Capturing is beyond the scope of this module. However, here's **[an article that covers capturing](https://javascript.info/regexp-groups)** should you decide to explore more.
