# ![RegEx - Level Up - Grouping and Capturing](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will understand the benefits of grouping and capturing in regular expressions.

## What is grouping?

Grouping in regex involves the use of parentheses to treat multiple characters as a single unit. Parentheses are used to create groups that can then have a quantifier applied to the group. Whereas the square brackets character class, `[]`, represents a **single** character to match, the parentheses `()` represent a **group** of characters to match.

One of the benefits of using grouping in regex is the ability to create more succinct and manageable patterns.

Let's say we want to match a string that repeats a certain pattern. Take the string `'hey!hey!hey!'` as an example. 

Without grouping, you would have to write out the pattern for each repetition:

```javascript
/hey!hey!hey!/
```

However, with grouping, we can simplify this by grouping the repeated pattern and then specifying how many times it should repeat:

```javascript
/(hey!){3}/
```

Let's take a look at a more realistic example. Say our application needed to match a computer’s IP Address. 

Ignoring the fact that we should limit the numbers to between 0 and 255, we could write something like this: 

```javascript
/\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}/
```

Using grouping we can shorten it to: 

```javascript
/(\d{1,3}\.){3}\d{1,3}/
```

## What is capturing?

Parentheses can also be used to define **capture** groups. Capturing is when matched text is “captured” into numbered groups. These groups can then be reused with a process called *backreferencing*. Capturing is beyond the scope of this module. However, here’s **[one of several articles out there](https://javascript.info/regexp-groups)** should you decide to explore more.

> 📚 Backreferencing in regex is a technique of reusing the text from capture groups to match other characters.