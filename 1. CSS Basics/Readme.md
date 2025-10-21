## What is CSS?
> CSS (**Cascading Style Sheets**) is used to style and layout HTML elements 

### How to Apply CSS to HTML.
> There are 3 ways to apply CSS:

#### 1. Inline CSS
> Write CSS directly inside an HTML element using the style attribute.
```html
<p style="color: red; font-size: 20px;">This is a red paragraph.</p>
```

#### 2. Internal CSS
> Place CSS rules inside a `<style>` tag in the `<head>` of your HTML document.

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    h1 {
      color: blue;
      text-align: center;
    }
  </style>
</head>
<body>
  <h1>Hello World</h1>
</body>
</html>
```

#### 3. External CSS
> Link a separate `.css` file to your HTML using the `<link>` tag.
```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <p>This is a styled paragraph.</p>
</body>
</html>
```

```css
/* styles.css */
p {
  color: green;
  font-weight: bold;
}
```

### 🎯 What is a CSS Selector?
> A selector in CSS is used to "select" the HTML element(s) you want to style.

#### 🧱 Basic Syntax:
```css
selector {
  property: value;
}
```

### 🔹 Common CSS Selectors Explained

#### 1. Universal Selector (`*`)
> Selects all elements on the page.
```css
* {
  margin: 0;
  padding: 0;
}
```

#### 2. Type or Tag Selector (e.g., `p`, `div`, `h1`)
> Selects all elements of a specific HTML tag.
```css
p {
  color: blue;
}
```

#### 3. Class Selector (`.classname`)
> Targets all elements with a specific class attribute.
```html
<p class="info">This is a paragraph.</p>
```
```css
.info {
  color: green;
}
```
💡 You can use the same class on multiple elements.

#### 4. ID Selector (`#idname`)
> Targets a single element with a specific id.
```html
<h1 id="main-title">Welcome</h1>
```
```css
#main-title {
  color: red;
}
```
⚠️ ID must be unique per page.

#### 5. Group Selector (`selector1`, `selector2`)
> Apply the same style to multiple selectors at once.
```css
h1, h2, p {
  font-family: Arial;
}
```

#### 6. Descendant Selector (`ancestor descendant`)
> Targets elements inside other elements.
```css
div p {
  color: purple;
}
```
🎯 All `<p>` tags inside a `<div>`.

#### 7. Child Selector (`parent > child`)
> Selects only direct children.
```css
ul > li {
  list-style-type: square;
}
```

#### 8. Adjacent Sibling Selector (`A + B`)
> Selects the next sibling element.
```css
h1 + p {
  color: orange;
}
```

#### 9. Attribute Selector (`[attr=value]`)
> Targets elements with specific attributes.
```css
input[type="text"] {
  border: 1px solid gray;
}
```

### 🔎 Summary Table
| Selector Type | Symbol  | Example         | Selects                       |
| ------------- | ------- | --------------- | ----------------------------- |
| Universal     | `*`     | `*`             | All elements                  |
| Type          | `p`     | `p`             | All `<p>` tags                |
| Class         | `.`     | `.box`          | All elements with class "box" |
| ID            | `#`     | `#header`       | The element with ID "header"  |
| Group         | `,`     | `h1, p`         | All `<h1>` and `<p>` elements |
| Descendant    | (space) | `div p`         | All `<p>` inside `<div>`      |
| Child         | `>`     | `ul > li`       | Direct `<li>` inside `<ul>`   |
| Sibling       | `+`     | `h1 + p`        | First `<p>` after `<h1>`      |
| Attribute     | `[]`    | `[type="text"]` | Elements with attribute value |

---

### 🛠️ Common CSS Properties

| Property     | Purpose                | Example                    |
| ------------ | ---------------------- | -------------------------- |
| `color`      | Text color             | `color: blue;`             |
| `font-size`  | Text size              | `font-size: 20px;`         |
| `background` | Background color/image | `background: yellow;`      |
| `margin`     | Outer spacing          | `margin: 10px;`            |
| `padding`    | Inner spacing          | `padding: 15px;`           |
| `border`     | Element border         | `border: 1px solid black;` |
| `text-align` | Text alignment         | `text-align: center;`      |

---

### 📘 Basic CSS Properties

| Property           | Purpose                    | Example                           | Notes                                      |
| ------------------ | -------------------------- | --------------------------------- | ------------------------------------------ |
| `color`            | Sets text color            | `color: red;`                     | Accepts name, hex, rgb, etc.               |
| `background-color` | Sets background color      | `background-color: yellow;`       | Can be applied to any element              |
| `font-size`        | Sets text size             | `font-size: 16px;`                | Use `px`, `em`, `rem`, `%`                 |
| `font-family`      | Sets font style            | `font-family: Arial, sans-serif;` | Always include a fallback                  |
| `width`            | Sets element width         | `width: 300px;`                   | Use `px`, `%`, `vw`, etc.                  |
| `height`           | Sets element height        | `height: 150px;`                  | Similar units as `width`                   |
| `margin`           | Space outside the element  | `margin: 20px;`                   | Accepts 1–4 values (top/right/bottom/left) |
| `padding`          | Space inside the element   | `padding: 10px;`                  | Also accepts 1–4 values                    |
| `border`           | Adds border around element | `border: 2px solid black;`        | Format: width style color                  |

---

### 🧱 Margin & Padding Shorthand Breakdown

| Syntax Example             | Meaning                                  |
| -------------------------- | ---------------------------------------- |
| `margin: 10px;`            | All 4 sides: 10px                        |
| `margin: 10px 20px;`       | Top/Bottom: 10px, Left/Right: 20px       |
| `margin: 10px 20px 5px;`   | Top: 10px, Left/Right: 20px, Bottom: 5px |
| `margin: 10px 15px 5px 0;` | Top, Right, Bottom, Left (clockwise)     |

---

### CSS Comments
> CSS comments are used to **add notes** or **explanations** or **disable code** without affecting the output.

`/* comment */`
