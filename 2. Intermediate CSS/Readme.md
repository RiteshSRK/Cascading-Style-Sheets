## What is the CSS Box Model?
> CSS Box Model defines how elements are structured and displayed on a webpage.

**1. Content –** The actual `text`, `image`, or `media inside` the element.

**2. Padding –** The `space between the content and border` (transparent by default).

**3. Border –** A `line surrounding the padding and Content` (if defined).

**4. Margin –** The outermost layer, `creating space between this element and others.`

---

### Box Model Structure
![Box model](./Box%20model.png "Box Model")

--- 

### CSS Properties
| **Layer**   | **Properties**                                                              | **Example Values**       |
| ----------- | --------------------------------------------------------------------------- | ------------------------ |
| **Content** | `width`, `height`, `min-width`, `max-height`, etc.                          | `width: 300px;`          |
| **Padding** | `padding`, `padding-top`, `padding-right`, `padding-left`, `padding-bottom` | `padding: 10px 20px;`    |
| **Border**  | `border`, `border-width`, `border-color`, `border-style`, `border-radius`   | `border: 2px solid red;` |
| **Margin**  | `margin`, `margin-top`, `margin-right`, `margin-left`, `margin-bottom`      | `margin: 0 auto;`        |

---
### 🧠 Important Notes:
- Total Size = `content + padding + border + margin`

- By default, `width` and `height` apply to `content-box`

- Use `box-sizing: border-box;` to include padding & border in width

---

#### ✅ Example:
```css
.box {
  width: 200px;           /* content width */
  height: 100px;          /* content height */
  padding: 10px;
  border: 5px solid blue;
  margin: 20px;
  box-sizing: content-box;  /* or use border-box */
}
```
---

## CSS display Property:
> display property is used to specify how element is shown on a web page.

### Comparison Table
| Value          | Behavior                                                               | Example Tags                | Width/Height? | New Line? | Can Set Padding/Margin? |
| -------------- | ---------------------------------------------------------------------- | --------------------------- | ------------- | --------- | ----------------------- |
| `block`        | Starts on a **new line** and takes **full width**                      | `<div>`, `<p>`, `<h1>`      | ✅ Yes         | ✅ Yes     | ✅ Yes                   |
| `inline`       | Stays **in line with text**, only takes as much width as needed        | `<span>`, `<a>`, `<strong>` | ❌ No          | ❌ No      | ❌ Only left/right       |
| `inline-block` | Inline like text but **can have width/height** like block              | (Used via CSS)              | ✅ Yes         | ❌ No      | ✅ Yes                   |
| `none`         | **Completely hides** the element (it’s not in the page layout anymore) | (Any element)               | ❌ N/A         | ❌ N/A     | ❌ N/A                   |

---
#### display: none
> Removes the element completely from the layout (as if it doesn’t exist).

> Unlike visibility: hidden, it doesn’t take up space.
```html
<p>This is a <span style="display: none;">hidden</span> word.</p>
```
⚠️ Element is not visible and doesn’t take up space.

---

### Bonus: Common Use Cases:
#### 1. Horizontal Navigation Menu
```css
nav li {
  display: inline-block; /* Makes list items horizontal */
  margin: 0 10px;
}
```

#### 2. Hide/Show Elements with JavaScript
```js
document.getElementById("menu").style.display = "block"; // Show
document.getElementById("menu").style.display = "none";  // Hide
```

---

## 📍 CSS position Property

- The `position` property in CSS defines **how an element is positioned on a web page.**

#### Syntax

```css
.element {
  position: value;
}
```

#### Values:
`static`, `relative`, `absolute`, `fixed`, `sticky`

### Types of Position

### (a) Static (Default)

- Elements follow **normal document flow**.
- `top`, `left`, `right`, `bottom` do not work.

```css
div {
  position: static;
}
```





---

### z-index and stacking context
#### 1. What is z-index?

- Determines the **front-to-back order** of overlapping elements.

- Higher `z-index` = Closer to the user (appears on top).

- Only works on positioned elements (`relative`, `absolute`, `fixed`, `sticky`).

#### Example:
```css
.box1 {
  position: absolute;
  z-index: 10; /* Appears on top */
}
.box2 {
  position: absolute;
  z-index: 5; /* Appears below */
}
```

---

### CSS Units: `px`, `em`, `rem`, `%`, `vh`, `vw`
> CSS units define sizes, spacing, and dimensions in web layouts.

#### 1. `px` (Pixels)
Fixed size (like a ruler).  <br>
Example: `width: 100px` → Always 100 pixels.

#### 2. `em`
Relative to parent’s font size.   <br>
Example: If parent has `font-size: 20px`, then `1em = 20px`.

#### 3. `rem`
Relative to root (`<html>`) font size (default: `16px`).  <br>
Example: `2rem = 32px` (if root is `16px`).

#### 4. `%` (Percent)
Relative to parent’s size.  <br>
Example: `width: 50%` → Half of parent’s width.

#### 5. `vh` / `vw`
Relative to viewport screen size:  <br>
`100vh` = Full screen height. <br>
`50vw` = Half screen width.

### When to Use Which Unit?
| **Unit**    | **Best For**                             | **Scalable?** | **Relative To**                              |
| ----------- | ---------------------------------------- | ------------- | -------------------------------------------- |
| `px`        | Borders, fixed-size icons                | ❌ No          | Absolute (screen pixels)                     |
| `em`        | Text-related spacing (nested components) | ✅ Yes         | Parent’s font-size                           |
| `rem`       | Global sizing (fonts, spacing)           | ✅ Yes         | Root (`<html>`) font-size                    |
| `%`         | Fluid layouts (width/height)             | ✅ Yes         | Parent’s size                                |
| `vh/vw`     | Full-screen layouts                      | ✅ Yes         | Viewport height/width                        |
| `vmin/vmax` | Responsive squares or adaptive boxes     | ✅ Yes         | Smaller/larger of viewport (width or height) |


---
### Pro Tips
- Use `rem` for **fonts/padding** → Ensures consistency.

- Use `%` or `vw/vh` for **fluid layouts** → Better responsiveness.

- Avoid `em` for **deep nesting** → Prevents compounding issues.

- Combine units (e.g., `calc(50% - 20px)`).

### Summary
- `px` → Fixed sizes (borders, icons).

- `em` → Relative to **parent** (but compounds).

- `rem` → Relative to **root** (best for scalability).

- `%` → Relative to **parent’s dimensions**.

- `vh/vw` → Relative to **viewport size**.


---

## 🧩 What is a Pseudo-class?
> A **pseudo-class** define the **special state of an element.**

### 1. `:hover`
- Styles when you **mouse over** an element.  <br>
- Great for buttons, links, and interactive elements.

```css
button:hover {
  background: blue; /* Turns blue on hover */
  color: white;
}
```
---
### 2. `:focus`
- Styles when an element is selected (like an input field).   <br>
- Important for **keyboard** accessibility.

```css
input:focus {
  border: 2px solid green; /* Highlights when clicked */
}
```
--- 
### 3. `:nth-child()`
- Selects **specific child elements** (like every 2nd item).    <br>
- Useful for tables, lists, and grids.

| **Example**        | **Meaning**                                        |
| ------------------ | -------------------------------------------------- |
| `:nth-child(2)`    | Selects the **second** child only                  |
| `:nth-child(odd)`  | Selects **all odd-numbered** children (1st, 3rd…)  |
| `:nth-child(even)` | Selects **all even-numbered** children (2nd, 4th…) |
| `:nth-child(3n)`   | Selects **every 3rd** child (3rd, 6th, 9th…)       |

```css
tr:nth-child(odd) {
  background: lightgray; /* Zebra-striped table rows */
}
```

### Bonus: Other Useful Pseudo-classes
`:active` → When clicked (e.g., button pressed).

`:checked` → For checked checkboxes/radio buttons.

`:first-child` / `:last-child` → First/last item in a group.

---

## What are Pseudo-elements?
- Pseudo-elements **insert virtual content** into the DOM — **without adding HTML elements**.

- **Used to style parts of an element**.

### `::before` → Inserts content before an element.
```css
p::before {
  content: "👉 ";
  color: blue;
}
```

### `::after` → Inserts content after an element.
```css
p::after {
  content: " ✅";
  color: green;
}
```

⚠️ Note-: Both require the `content` property to work

---

### 1. `opacity` - Element Transparency
> Controls how transparent an element is.
```css
div {
  opacity: 0.5; /* 50% transparent */
}
```
### 2. visibility - Hide Without Removing Space
> Controls the element is **visible or hidden, without removing its space.**
```css
div {
  visibility: hidden; /* element is hidden but space remains */
}
```

### vs `display: none`:
`visibility: hidden` → **Keeps space** in layout  <br>
`display: none` → **Removes completely** (no space)

#### Example Use Cases:
- Hide form errors until needed   <br>
- Toggle UI elements without layout shifts

---

### 3. overflow - Handle Extra Content
> Controls content overflows its container.
```css
.container {
  overflow: hidden; /* Cuts off extra content */
}
```

| **Value** | **Effect**                                             |
| --------- | ------------------------------------------------------ |
| `visible` | Shows extra content outside the box (default behavior) |
| `hidden`  | Hides/cuts off any extra content outside the container |
| `scroll`  | Always shows scrollbars, even if content fits          |
| `auto`    | Shows scrollbars **only if** the content overflows     |

#### Variations:
- `overflow-x` (horizontal) / `overflow-y` (vertical)   <br>
- `overflow: clip` (new, stricter than `hidden`)

--- 
<br>

## `cursor`, `text-align`, `vertical-align`

### 1. `cursor` - Control Mouse Pointer Appearance
> Changes how the mouse cursor looks when hovering over an element.
```css
button {
  cursor: pointer; /* Hand icon for clickable items */
}
```

### Common Values:
| **Value**     | **Appearance** | **Best For**                |
| ------------- | -------------- | --------------------------- |
| `pointer`     | 👆 Hand        | Buttons, links              |
| `default`     | 🖱️ Arrow      | Normal/default text areas   |
| `text`        | ⎵ I-beam       | Selectable or editable text |
| `move`        | ✥ Crosshair    | Draggable/movable elements  |
| `not-allowed` | 🚫 Circle      | Disabled buttons/actions    |
| `wait`        | ⏳ Hourglass    | Waiting/loading states      |
| `zoom-in/out` | 🔍 Magnifier   | Zoomable images or maps     |

---
### 2. text-align - Horizontal Text Alignment
> Controls how text is aligned left-to-right in its container.
```css
p {
  text-align: center; /* Centers text */
}
```

| **Value** | **Effect**                                                           |
| --------- | -------------------------------------------------------------------- |
| `left`    | Aligns text to the **left** (default)                                |
| `right`   | Aligns text to the **right**                                         |
| `center`  | **Centers** the text horizontally                                    |
| `justify` | Stretches text to fill the full width, adjusting space between words |

#### Works With:
- Block elements (`div`, `p`, `h1`)

- Table cells (`td`, `th`)

---

### 3. vertical-align - Vertical Alignment
> Aligns inline/inline-block elements vertically (not for block elements!).
```css
img {
  vertical-align: middle; /* Aligns with text */
}
```
#### Common Values:
| **Value**     | **Effect**                                                               |
| ------------- | ------------------------------------------------------------------------ |
| `baseline`    | Aligns element with the **baseline** of the surrounding text *(default)* |
| `top`         | Aligns element to the **top** of the line                                |
| `middle`      | Vertically **centers** the element within the line                       |
| `bottom`      | Aligns element to the **bottom** of the line                             |
| `text-top`    | Aligns element with the **top of the parent text**                       |
| `text-bottom` | Aligns element with the **bottom of the parent text**                    |

#### Where It Works:
- Images (img)

- Icons (Font Awesome)

- Table cells (td, th)

- inline-block elements
---
