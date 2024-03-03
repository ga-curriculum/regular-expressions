# ![Regular Expressions - Setup](./assets/hero.png)

## Setup

Open your Terminal application and navigate to your `~/code/ga/lectures` directory:

```bash
cd ~/code/ga/lectures
```

Make a new directory called `regex`, then enter this directory:

```bash
mkdir regex
cd regex
```

Create two directories - one called `js`, the other called `css`:

```bash
mkdir js css
```

Then, create an `index.html` file, a `style.css` file inside of the `css` directory, as well as a `app.js` file inside the `js` directory. These files will hold your work for this lecture:

```bash
touch index.html ./js/app.js ./css/style.css
```

With the files created, open the contents of the directory in VS Code:

```bash
code .
```

Open the `index.html` file and add HTML boilerplate by typing `!` and then hitting the `Tab` key. Then link the `app.js` file inside of the `js` directory and the `style.css` file inside of the `css` directory by adding these line inside the `<head>` tag:

```html
<link rel="stylesheet" href="./css/style.css"/>
<script defer src="./js/app.js"></script>
```

Open the `/css/style.css` file and add this code to assist in visually validating our work in this app:

```css
body {
  background-color: #101720;
}

form {
  padding: 50px;
  border: 4px solid lightgreen;
  border-radius: 20px;
}

input {
  font-size: 18px;
  padding: 8px 12px;
  border-width: 8px;
}

form:invalid {
  border-color: yellow;
}

input:invalid {
  border-color: red;
}
```

With this setup complete, open the `index.html` file in your browser.
