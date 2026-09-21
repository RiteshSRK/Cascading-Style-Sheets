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

## 12. CSS `box-shadow`

| Property | Meaning | Syntax / Example | Main Use |
|---|---|---|---|
| `box-shadow` | Adds a shadow around an element's box | `box-shadow: 5px 5px 10px gray;` | Creating depth and visual effects |
| **Offset X** | Moves the shadow horizontally | `5px` | Positive → right, Negative → left |
| **Offset Y** | Moves the shadow vertically | `5px` | Positive → down, Negative → up |
| **Blur Radius** | Controls how soft or sharp the shadow is | `10px` | Higher value → softer shadow |
| **Spread Radius** | Controls how much the shadow expands or shrinks | `2px` | Positive → expands, Negative → shrinks |
| **Color** | Defines the shadow color | `gray` / `rgba(0,0,0,0.3)` | Controls shadow appearance |
| `inset` | Places the shadow inside the element | `box-shadow: inset 0 0 10px gray;` | Inner shadow |


Syntax:
```css
box-shadow: offset-x offset-y blur-radius spread-radius color;
```

Example:
```css
box-shadow: 5px 5px 10px 2px rgba(0, 0, 0, 0.3);
```

```css
.card {
  width: 300px;
  padding: 20px;
  background: white;

  box-shadow: 5px 5px 10px gray;
}
```

```
X → Horizontal
Y → Vertical
Blur → Softness
Spread → Size
Color → Shadow color
```

---

## 13. CSS `Background` Image

| Property | Meaning | Example | Main Use |
|---|---|---|---|
| `background-image` | Sets an image as the background of an element | `background-image: url("image.jpg");` | Adding background images |
| `background-size` | Controls the size of the background image | `background-size: cover;` | Fit image to container |
| `background-position` | Controls the position of the background image | `background-position: center;` | Positioning the image |
| `background-repeat` | Controls whether the image repeats | `background-repeat: no-repeat;` | Preventing image repetition |
| `background-attachment` | Controls how the background moves while scrolling | `background-attachment: fixed;` | Fixed/parallax-style backgrounds |

```css
.hero {
  height: 500px;
  background-image: url("hero.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
```

Common Values

| Property | Common Values |
|---|---|
| `background-size` | `cover`, `contain`, `auto` |
| `background-position` | `center`, `top`, `bottom`, `left`, `right` |
| `background-repeat` | `repeat`, `no-repeat`, `repeat-x`, `repeat-y` |
| `background-attachment` | `scroll`, `fixed`, `local` |

<br>

---

### 🎯 `background: linear-gradient(...)`

| Part | Meaning | Example |
|---|---|---|
| `linear-gradient()` | Creates a smooth color transition | `linear-gradient(...)` |
| `to right bottom` | Sets the gradient direction from **top-left to bottom-right** | `to right bottom` |
| `yellowgreen` | First color | `yellowgreen` |
| `yellow` | Second color | `yellow` |
| `cyan` | Third color | `cyan` |
| `background` | Sets the gradient as the element's background | `background: linear-gradient(...);` |

```css
.box {
  width: 400px;
  height: 200px;
  background: linear-gradient(to right bottom, yellowgreen, yellow, cyan);
}
```

Direction:

```
Top-Left
   ↘
    ↘
     ↘
      Bottom-Right
```

The colors smoothly transition in this direction:  
Yellowgreen → Yellow → Cyan.

---

## 14. CSS `Flexbox`

Flexbox (**Flexible Box Layout**) is a **one-dimensional layout system** used to arrange elements in a **row or column**.

| Property | Meaning | Common Values | Example |
|---|---|---|---|
| `display` | Creates a flex container | `flex`, `inline-flex` | `display: flex;` |
| `flex-direction` | Sets the main axis direction | `row`, `row-reverse`, `column`, `column-reverse` | `flex-direction: row;` |
| `justify-content` | Aligns items along the **main axis** | `flex-start`, `center`, `flex-end`, `space-between`, `space-around`, `space-evenly` | `justify-content: center;` |
| `align-items` | Aligns items along the **cross axis** | `stretch`, `flex-start`, `center`, `flex-end`, `baseline` | `align-items: center;` |
| `flex-wrap` | Controls whether items wrap to a new line | `nowrap`, `wrap`, `wrap-reverse` | `flex-wrap: wrap;` |
| `align-content` | Aligns multiple flex lines | `flex-start`, `center`, `space-between`, `space-around`, `stretch` | `align-content: center;` |
| `gap` | Adds space between flex items | Length value | `gap: 20px;` |
| `row-gap` | Sets space between rows | Length value | `row-gap: 10px;` |
| `column-gap` | Sets space between columns | Length value | `column-gap: 20px;` |
| `flex-grow` | Controls how much an item can grow | Number | `flex-grow: 1;` |
| `flex-shrink` | Controls how much an item can shrink | Number | `flex-shrink: 0;` |
| `flex-basis` | Sets the initial size of a flex item | `auto`, length | `flex-basis: 200px;` |
| `flex` | Shorthand for grow, shrink, and basis | `flex-grow flex-shrink flex-basis` | `flex: 1;` |
| `align-self` | Overrides `align-items` for one item | `auto`, `flex-start`, `center`, `flex-end` | `align-self: center;` |
| `order` | Changes the visual order of an item | Number | `order: 2;` |

### Flexbox Direction

| `flex-direction` | Axis | Direction | Description |
|---|---|---|---|
| `row` | Main axis | Left → Right | Flex items are placed horizontally from left to right |
| `row-reverse` | Main axis | Right → Left | Flex items are placed horizontally from right to left |
| `column` | Main axis | Top → Bottom | Flex items are placed vertically from top to bottom |
| `column-reverse` | Main axis | Bottom → Top | Flex items are placed vertically from bottom to top |

### Flexbox Axes

| Axis | Controlled By | Meaning |
|---|---|---|
| **Main Axis** | `justify-content` | Primary direction of flex items |
| **Cross Axis** | `align-items` | Perpendicular direction to the main axis |

<br>

```html
<div class="container">
  <div>Box 1</div>
  <div>Box 2</div>
  <div>Box 3</div>
</div>
```

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
}
```

### Interview definition:

Flexbox is a one-dimensional CSS layout system used to arrange and align elements along a main axis and a cross axis, making responsive layouts easier to create.

---

## 15. CSS `Grid`

CSS Grid is a **two-dimensional layout system** used to arrange elements in **rows and columns**.

| Grid Property | Meaning | Common Values / Syntax | Main Use | Example |
|---|---|---|---|---|
| `display: grid` | Creates a grid container | `grid` | Enables CSS Grid | `display: grid;` |
| `grid-template-columns` | Defines the number and size of columns | `px`, `%`, `fr`, `repeat()` | Creates columns | `grid-template-columns: repeat(3, 1fr);` |
| `grid-template-rows` | Defines the size of rows | `px`, `%`, `fr`, `repeat()` | Creates rows | `grid-template-rows: 100px 200px;` |
| `gap` | Sets space between rows and columns | `px`, `rem`, etc. | Adds spacing | `gap: 20px;` |
| `row-gap` | Sets space between rows | Length | Controls row spacing | `row-gap: 20px;` |
| `column-gap` | Sets space between columns | Length | Controls column spacing | `column-gap: 20px;` |
| `grid-column` | Controls an item's column position | `start / end` | Places item across columns | `grid-column: 1 / 3;` |
| `grid-row` | Controls an item's row position | `start / end` | Places item across rows | `grid-row: 1 / 3;` |
| `grid-column-start` | Defines where a grid item starts horizontally | Grid line number | Sets starting column | `grid-column-start: 1;` |
| `grid-column-end` | Defines where a grid item ends horizontally | Grid line number | Sets ending column | `grid-column-end: 3;` |
| `grid-row-start` | Defines where a grid item starts vertically | Grid line number | Sets starting row | `grid-row-start: 1;` |
| `grid-row-end` | Defines where a grid item ends vertically | Grid line number | Sets ending row | `grid-row-end: 3;` |
| `grid-template-areas` | Creates named areas in the grid | String names | Creates structured layouts | `grid-template-areas: "header header";` |
| `grid-area` | Assigns an item to a named grid area | Area name | Places items in named areas | `grid-area: header;` |
| `justify-items` | Aligns grid items horizontally inside their cells | `start`, `center`, `end`, `stretch` | Horizontal item alignment | `justify-items: center;` |
| `align-items` | Aligns grid items vertically inside their cells | `start`, `center`, `end`, `stretch` | Vertical item alignment | `align-items: center;` |
| `place-items` | Shorthand for `align-items` + `justify-items` | Two values | Aligns all grid items | `place-items: center;` |
| `justify-content` | Aligns the entire grid horizontally | `start`, `center`, `end`, `space-between`, etc. | Positions the grid | `justify-content: center;` |
| `align-content` | Aligns the entire grid vertically | `start`, `center`, `end`, `space-between`, etc. | Positions the grid | `align-content: center;` |
| `place-content` | Shorthand for `align-content` + `justify-content` | Two values | Positions the entire grid | `place-content: center;` |

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
```

```
┌────────┐ ┌────────┐ ┌────────┐
│ Item 1 │ │ Item 2 │ │ Item 3 │
└────────┘ └────────┘ └────────┘

┌────────┐ ┌────────┐ ┌────────┐
│ Item 4 │ │ Item 5 │ │ Item 6 │
└────────┘ └────────┘ └────────┘
```

Grid works with **both rows and columns**.

---

### 1. display: grid

It makes an element a grid container.

```css
.container {
  display: grid;
}
```

The direct children become grid items.

```html
<div class="container">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

```
Grid Container
      │
      ├── Item 1 → Grid Item
      ├── Item 2 → Grid Item
      └── Item 3 → Grid Item
```

### 2. grid-template-columns

It defines the number and size of columns.

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px 200px;
}
```
```
┌──────────┐ ┌──────────┐ ┌──────────┐
│ Column 1 │ │ Column 2 │ │ Column 3 │
└──────────┘ └──────────┘ └──────────┘
```

👉 **Using `fr`**

`fr` means fraction of available space.

```css
grid-template-columns: 1fr 1fr 1fr;
```

This creates three equal columns.
```
┌────────┬────────┬────────┐
│   1fr  │   1fr  │   1fr  │
└────────┴────────┴────────┘
```

### 3. grid-template-rows

It defines the size of rows.

```css
.container {
  grid-template-rows: 100px 200px;
}
```

```
┌──────────────────────────┐
│        Row 1 — 100px     │
├──────────────────────────┤
│        Row 2 — 200px     │
└──────────────────────────┘
```

### 4. `repeat()`

Instead of writing the same value multiple times, we can use `repeat()`.

Instead of:

```css
grid-template-columns: 1fr 1fr 1fr;
```

Write:

```css
grid-template-columns: repeat(3, 1fr);
```

Meaning:
> Create 3 columns, each taking 1 fraction of the available space.

### 5. `gap` 

`gap` creates space between grid items.

```css
.container {
  display: grid;
  gap: 20px;
}
```

```
┌──────┐   20px   ┌──────┐
│ Item │ ←──────→ │ Item │
└──────┘          └──────┘
```

**You can also use:**

```css
row-gap: 20px;
column-gap: 30px;
```

---

### 6. `grid-column`
It controls how many columns a grid item occupies.

```css
.item {
  grid-column: 1 / 3;
}
```

The item starts at column line `1` and ends at line `3`.

```
┌───────────────────────┐
│        Item 1         │
│   Column 1 → 3        │
└───────────────────────┘

┌────────┐ ┌────────┐
│ Item 2 │ │ Item 3 │
└────────┘ └────────┘
```

---

### 7. `grid-row`

It controls how many rows a grid item occupies.

```css
.item {
  grid-row: 1 / 3;
}
```

```
┌────────┐
│        │
│ Item 1 │
│        │
│        │
└────────┘
```

The item spans from row line `1` to row line `3`.

---

### 8. `grid-template-areas`
This allows you to create a layout using named areas.

```css
.container {
  display: grid;

  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}
```

Visual structure:

```
┌───────────────┐
│    Header     │
├───────┬───────┤
│Sidebar│ Main  │
├───────┴───────┤
│     Footer     │
└───────────────┘
```

Then assign areas:

```css
.header {
  grid-area: header;
}

.sidebar {
  grid-area: sidebar;
}

.main {
  grid-area: main;
}

.footer {
  grid-area: footer;
}
```

This is very useful for complete webpage layouts.

---

### 9. justify-items
Controls the horizontal alignment of items inside their grid cells.

```css
.container {
  justify-items: center;
}
```

Common values:

```
start
center
end
stretch
```

Example:

```css
justify-items: center;
```

```
┌──────────────┐
│              │
│     Item     │
│              │
└──────────────┘
       ↑
    centered
```

### 10. `align-items`
Controls the vertical alignment of items inside their grid cells.

```css
.container {
  align-items: center;
}
```

```
start
center
end
stretch
```

### 11. `place-items`
Shorthand for:

```css
align-items
justify-items
```

Example:

```css
.container {
  place-items: center;
}
```

This centers items both horizontally and vertically.

---

### 12. `justify-content`
Controls the position of the entire grid along the horizontal axis when there is extra space.

```css
.container {
  justify-content: center;
}
```

```
start
center
end
space-between
space-around
space-evenly
```

---

