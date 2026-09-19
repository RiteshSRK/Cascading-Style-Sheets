## 1️⃣ Text Properties

| Property                | Values / Examples                                      | Description                      |
| ----------------------- | ------------------------------------------------------ | -------------------------------- |
| `text-align`            | `left` / `right` / `center` / `justify`                | Aligns text horizontally         |
| `text-transform`        | `uppercase` / `lowercase` / `capitalize` / `none`      | Changes letter case of text      |
| `text-decoration`       | `underline` / `overline` / `line-through` / `none`     | Adds or removes decoration lines |
| `text-decoration-color` | `red` / `green` / `blue` / etc.                        | Changes decoration line color    |
| `text-decoration-style` | `solid` / `double` / `dotted` / `dashed` / `wavy`      | Sets style of decoration line    |
| `line-height`           | `normal` / `1` / `1.5` / `2` / `3em` / `150%` / `32px` | Controls spacing between lines   |
| `letter-spacing`        | `normal` / `10px`                                      | Controls space between letters   |
| `font-weight`           | `normal` / `bold` / `bolder` / `lighter` / `100-900`   | Sets thickness of text           |
| `font-size`             | `px` / `%` / `em` / `rem`                              | Controls size of text            |
| `font-family`           | `sans-serif` / `serif`                                 | Sets font style family           |

---

## 2️⃣ Selectors

| Selector                    | Syntax                 | Description                                     |
| --------------------------- | ---------------------- | ----------------------------------------------- |
| Universal Selector          | `*{}`                  | Selects all elements                            |
| Element Selector            | `h1, h2{}`             | Selects all specified HTML elements             |
| ID Selector                 | `#myId{}`              | Selects element with specific ID                |
| Class Selector              | `.myClass{}`           | Selects elements with specific class            |
| Descendant Selector         | `div p{}`              | Selects all `<p>` inside `<div>`                |
| Adjacent Sibling Combinator | `p + h3{}`             | Selects first `<h3>` immediately after `<p>`    |
| Child Combinator            | `span > button{}`      | Selects direct child `<button>` inside `<span>` |
| Attribute Selector          | `input[type="text"]{}` | Selects elements based on attribute             |


```css
*{
    margin: 0;
}

h1, h2{
    color: blue;
}

#myId{
    background-color: yellow;
}

.myClass{
    font-size: 20px;
}

div p{
    color: green;
}

p + h3{
    color: red;
}

span > button{
    border: 2px solid black;
}

input[type="text"]{
    border: 1px solid gray;
}
```

---

## 3️⃣ `Pseudo` Class and `Pseudo` Elements

| Basis    | Pseudo Class                          | Pseudo Element                        |
| -------- | ------------------------------------- | ------------------------------------- |
| Purpose  | Selects a special state of an element | Selects a specific part of an element |
| Syntax   | Uses single colon `:`                 | Uses double colon `::`                |
| Example  | `:hover`, `:active`                   | `::first-letter`, `::first-line`      |
| Works On | Entire element state                  | Specific part of content              |
| Use Case | Styling user actions or conditions    | Styling portions of text/content      |

### `Pseudo` Class

| Pseudo Class     | Example              | Description                                          |
| ---------------- | -------------------- | ---------------------------------------------------- |
| `:hover`         | `button:hover{}`     | Applies style when mouse is over the element         |
| `:active`        | `button:active{}`    | Applies style when element is being clicked          |
| `:checked`       | `input:checked{}`    | Applies style to checked radio buttons or checkboxes |
| `:nth-of-type()` | `p:nth-of-type(2){}` | Selects specific element based on position           |

```css
button:hover{
    background-color: blue;
    color: white;
}

button:active{
    background-color: red;
}

input:checked{
    width: 20px;
    height: 20px;
}

p:nth-of-type(2){
    color: green;
    font-weight: bold;
}
```

### `Pseudo` Elements

| Pseudo Element   | Example             | Description                      |
| ---------------- | ------------------- | -------------------------------- |
| `::first-letter` | `p::first-letter{}` | Styles the first letter of text  |
| `::first-line`   | `p::first-line{}`   | Styles the first line of text    |
| `::selection`    | `p::selection{}`    | Styles selected/highlighted text |

```css
p::first-letter{
    font-size: 30px;
    color: red;
}

p::first-line{
    font-weight: bold;
    color: blue;
}

p::selection{
    background-color: yellow;
    color: black;
}
```

---

## 4️⃣ Selector Specificity in CSS

| Priority Level | Selector Type                   | Examples                            |
| -------------- | ------------------------------- | ----------------------------------- |
| Highest        | ID Selector                     | `#myId`                             |
| Medium         | Class, Attribute & Pseudo-class | `.box` , `[type="text"]` , `:hover` |
| Lowest         | Element & Pseudo-element        | `h1` , `p` , `::first-letter`       |


```css
ID > Class/Attribute/Pseudo-class > Element/Pseudo-element
```

#### Specificity Values

| Selector                         | Specificity Value |
| -------------------------------- | ----------------- |
| Inline Style                     | `1000`            |
| ID                               | `100`             |
| Class / Attribute / Pseudo-class | `10`              |
| Element / Pseudo-element         | `1`               |

```css
Inline Style > ID > Class > Element
```

---

## 5️⃣ `!important` in CSS 
- `!important` is used to give a CSS property the **highest priority**.

```css
h2{
	Background-color: blue  !important;
}
```

---

## 6️⃣ Box Model in CSS

| Property        | Syntax / Values              | Description                |
| --------------- | ---------------------------- | -------------------------- |
| `height`        | `height: 100px;`             | Sets height of element     |
| `width`         | `width: 100px;`              | Sets width of element      |
| `border`        | `border: 2px solid red;`     | Adds border around element |
| `border-width`  | `border-width: 2px;`         | Sets border thickness      |
| `border-style`  | `solid / dashed / dotted`    | Sets border style          |
| `border-color`  | `border-color: red;`         | Sets border color          |
| `padding`       | `padding: 10px;`             | Space inside border        |
| `margin`        | `margin: 50px;`              | Space outside border       |
| `border-radius` | `border-radius: 10px / 50%;` | Rounds element corners     |


#### Padding Shorthand

| Values                          | Meaning                     |
| ------------------------------- | --------------------------- |
| `padding: 10px;`                | All sides                   |
| `padding: 10px 20px;`           | Top-Bottom / Left-Right     |
| `padding: 10px 20px 30px;`      | Top / Left-Right / Bottom   |
| `padding: 10px 20px 30px 40px;` | Top / Right / Bottom / Left |


#### Margin Shorthand

| Values                         | Meaning                     |
| ------------------------------ | --------------------------- |
| `margin: 20px;`                | All sides                   |
| `margin: 10px 20px;`           | Top-Bottom / Left-Right     |
| `margin: 10px 20px 30px;`      | Top / Left-Right / Bottom   |
| `margin: 10px 20px 30px 40px;` | Top / Right / Bottom / Left |


#### Border Radius Shorthand

| Values                                | Meaning                                           |
| ------------------------------------- | ------------------------------------------------- |
| `border-radius: 10px;`                | All corners                                       |
| `border-radius: 10px 20px;`           | Top-Left & Bottom-Right / Top-Right & Bottom-Left |
| `border-radius: 10px 20px 30px 40px;` | Top-Left / Top-Right / Bottom-Right / Bottom-Left |

---

##  7️⃣ `Display` Property

| Display Value  | Meaning                       | Behavior                              | Width & Height           | Common Use |
|----------------|-------------------------------|---------------------------------------|--------------------------|------------|
| `inline`       | Inline element                | Stays on the same line                | Generally not applicable | Text, links, `<span>` |
| `block`        | Block-level element           | Starts on a new line                  | Works | Sections, containers |
| `inline-block` | Combination of inline + block | Stays on the same line                | Works | Buttons, menu items |
| `flex`         | Flex container                | Arranges children in a row or column  | Works | Navigation bars, alignment   |
| `grid`         | Grid container                | Arranges children in rows and columns | Works | Cards, page layouts         |
| `none`         | Hidden element                | Completely removed from the layout    | No space occupied | Hiding elements    |

---

| `display` Value | Main Use                                        | Example                       |
|-----------------|-------------------------------------------------|-------------------------------|
| `inline`        | Text/inline content                             | `<span>`, `<a>`               |
| `block`         | Sections & containers                           | `<div>`, `<p>`, `<section>`   |
| `inline-block`  | Same line + custom size                         | Buttons, menu items           |
| `flex`          | **1D layout** (row/column)                      | Navbar, cards                 |
| `grid`          | **2D layout** (rows + columns)                  | Page/card layouts             |
| `none`          | Completely hides/removes element from layout    | Hide menu/modal               |

---

## 8️⃣ Units in CSS

| Unit Type | Unit | Based On | Main Use | Example |
|---|---|---|---|---|
| **Absolute** | `px` | Fixed pixels | Precise sizing | `width: 200px;` |
| **Relative** | `%` | Parent element | Responsive sizing relative to parent | `width: 50%;` |
| **Relative** | `em` | Parent element's font size | Scaling based on font size | `font-size: 1.5em;` |
| **Relative** | `rem` | Root (`html`) font size | Consistent, scalable sizing | `font-size: 2rem;` |
| **Relative** | `vh` | Viewport height | Sizing based on screen height | `height: 100vh;` |
| **Relative** | `vw` | Viewport width | Sizing based on screen width | `width: 100vw;` |

<br> 


| Property | Meaning | Purpose | Example |
|---|---|---|---|
| `max` | Maximum limit | Prevents an element from becoming larger than a specified value | `max-width: 1200px;` |
| `min` | Minimum limit | Prevents an element from becoming smaller than a specified value | `min-width: 300px;` |
| `max-width` | Maximum width | Sets the maximum allowed width | `max-width: 100%;` |
| `min-width` | Minimum width | Sets the minimum allowed width | `min-width: 200px;` |
| `max-height` | Maximum height | Sets the maximum allowed height | `max-height: 500px;` |
| `min-height` | Minimum height | Sets the minimum allowed height | `min-height: 200px;` |

## 9️⃣ Alpha Channel

| Property / Concept | Meaning | Range | Example | Use |
|---|---|---|---|---|
| **Alpha Channel** | Controls the **opacity/transparency** of a color | `0` to `1` | `rgba(255, 255, 255, 0.3)` | Making colors transparent or semi-transparent |
| `0` | Completely transparent | `0` | `rgba(255, 255, 255, 0)` | Invisible color |
| `0.5` | 50% transparent | `0`–`1` | `rgba(255, 255, 255, 0.5)` | Semi-transparent color |
| `1` | Completely opaque | `0`–`1` | `rgba(255, 255, 255, 1)` | Fully visible color |

```html
<div class="box">Hello CSS</div>
```

```cs
.box {
  background-color: rgba(0, 0, 255, 0.5);
  color: white;
}
```

| Value | Meaning |
|---|---|
| `0` | Red |
| `0` | Green |
| `255` | Blue |
| `0.5` | 50% opacity / transparency |

⚡ Important: Alpha affects the color, not the entire element.

## 🔟 Opacity

| Property | Meaning | Range | Example | Effect |
|---|---|---|---|---|
| **`opacity`** | Controls the transparency of the **entire element** | `0` to `1` | `opacity: 0.5;` | Makes the element 50% transparent |
| `0` | Completely transparent | `0` | `opacity: 0;` | Element becomes invisible |
| `0.5` | 50% transparent | `0`–`1` | `opacity: 0.5;` | Semi-transparent element |
| `1` | Completely opaque | `0`–`1` | `opacity: 1;` | Fully visible element |

```html
<div class="box">Hello CSS</div>
```

```css
.box {
  background-color: blue;
  color: white;
  opacity: 0.5;
}
```

---

## 11. CSS Position Property

| `position` Value | Meaning | How It Works | Common Use | Example |
|---|---|---|---|---|
| `static` | Default position | Element stays in the normal document flow | Default layout | `position: static;` |
| `relative` | Relative to its normal position | Element remains in the document flow and can be moved using `top`, `right`, `bottom`, `left` | Creating a reference point for absolute children | `position: relative; top: 10px;` |
| `absolute` | Positioned relative to the nearest positioned ancestor | Removed from normal document flow | Badges, dropdowns, overlays | `position: absolute; top: 0; right: 0;` |
| `fixed` | Fixed relative to the viewport | Removed from normal flow and stays in the same position while scrolling | Fixed navbar, floating button | `position: fixed; bottom: 20px; right: 20px;` |
| `sticky` | Combination of relative and fixed behavior | Stays in normal flow until a specified scroll position is reached | Sticky navbar, headings | `position: sticky; top: 0;` |

