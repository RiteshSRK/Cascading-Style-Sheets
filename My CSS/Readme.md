### Text Properties

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

### Selectors

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

### Pseudo Class and Pseudo Elements

| Basis    | Pseudo Class                          | Pseudo Element                        |
| -------- | ------------------------------------- | ------------------------------------- |
| Purpose  | Selects a special state of an element | Selects a specific part of an element |
| Syntax   | Uses single colon `:`                 | Uses double colon `::`                |
| Example  | `:hover`, `:active`                   | `::first-letter`, `::first-line`      |
| Works On | Entire element state                  | Specific part of content              |
| Use Case | Styling user actions or conditions    | Styling portions of text/content      |

### Pseudo Class

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

### Pseudo Elements

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

### Selector Specificity in CSS

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

### `!important` in CSS 
- `!important` is used to give a CSS property the **highest priority**.

```css
h2{
	Background-color: blue  !important;
}
```

---

### Box Model in CSS

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
