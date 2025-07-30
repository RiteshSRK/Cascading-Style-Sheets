# CSS Animations & Transitions
- [Transition](#what-is-transition-in-css?)

---
## What is transition in CSS?
> The transition property lets you smoothly animate changes in CSS properties

## 1. Transition Syntax
```css
transition: [property] [duration] [timing-function] [delay];
```
### A. Property
- Specifies which CSS property to animate

- Use `all` to transition all animatable properties
```css
/* Animate only width */
transition: width 0.3s ease;

/* Animate multiple properties */
transition: width 0.3s ease, height 0.5s linear;

/* Animate all properties */
transition: all 0.3s ease;
```

### B. Duration
- How long the transition takes (in seconds `s` or milliseconds `ms`)
```css
transition: width 0.5s ease; /* Half second */
transition: opacity 300ms linear; /* 300 milliseconds */
```

### C. Timing Function
- Controls the acceleration curve of the animation.

```css
| **Value**     | **Effect**                                  |
|:-------------:|:-------------------------------------------:|
| `ease`        | Starts slow, speeds up, ends slow (default) |
| `linear`      | Same speed throughout                       |
| `ease-in`     | Starts slow                                 |
| `ease-out`    | Ends slow                                   |
| `ease-in-out` | Slow at both start and end                  |
```

```js
transition: transform 0.4s ease-in-out;
```

### D. Delay (Optional)
- Waits before starting the transition
```js
transition: opacity 0.3s ease 0.2s; /* Waits 0.2s before fading */
```

## 3. Practical Examples
### Button Hover Effect
```js
.button {
  background: blue;
  transition: background 0.3s ease, transform 0.2s ease-out;
}

.button:hover {
  background: darkblue;
  transform: scale(1.05);
}
```
------
## 4. What Properties Can Transition?
> Most numeric/color properties can transition, including:

- `opacity`

- `color`, `background-color`

- `width`, `height`

- `transform` (scale, rotate, translate)

- `box-shadow`

- `border-radius`

## 6. Shorthand vs Longhand
```js
/* Shorthand */
transition: all 0.3s ease-in-out 0.1s;

/* Longhand */
transition-property: all;
transition-duration: 0.3s;
transition-timing-function: ease-in-out;
transition-delay: 0.1s;
```
---

# What is transform?
> The `transform` property allows you to visually **manipulate an element’s shape, size, and position** without affecting the actual layout.

## Common transform Functions:
| **Function**      | **Effect**                          | **Example**                     |
| ----------------- | ----------------------------------- | ------------------------------- |
| `scale(x)`        | Resizes the element (x = 1 is 100%) | `scale(1.5)` = 150% size        |
| `rotate(deg)`     | Rotates the element                 | `rotate(45deg)` = 45° clockwise |
| `translate(x, y)` | Moves element on X and Y axes       | `translate(50px, 20px)`         |
---
## 1. scale() – Zoom In/Out
> Changes the size of an element.
### Basic Syntax
```js
transform: scale(x, y); /* x = width, y = height */
```
### Examples
```js
/* Uniform scaling */
.element {
  transform: scale(1.5); /* 150% of original size */
}

/* Different x/y scaling */
.element {
  transform: scale(1.2, 0.8); /* Wider but shorter */
}

/* Scale on hover */
.button:hover {
  transform: scale(1.1); /* 10% larger */
}
```
- `scale(1)` = no change

- `scale(2)` = double size

- `scale(0.5)` = half size

### Variations
- `scaleX()` - Horizontal scaling only

- `scaleY()` - Vertical scaling only
---

## 2. rotate() – Rotate Element
> Rotates an element around its center point.
### Basic Syntax
```js
transform: rotate(angle);
```
### Examples
```js
/* 45 degree rotation */
.element {
  transform: rotate(45deg);
}

/* Full rotation on hover */
.icon:hover {
  transform: rotate(360deg);
  transition: transform 0.5s ease;
}

/* Negative rotation */
.arrow {
  transform: rotate(-90deg);
}
```
---

## 3. translate() - Moving Elements
> Repositions an element without affecting other elements.
### Basic Syntax
```js
transform: translate(x, y);
```
### Examples
```js
/* Move right 20px, down 10px */
.element {
  transform: translate(20px, 10px);
}

/* Center positioning trick */
.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

/* Horizontal slide-in */
.slide-in {
  transform: translateX(100%);
  animation: slideIn 0.5s forwards;
}

@keyframes slideIn {
  to { transform: translateX(0); }
}
```
### Variations
- `translateX()` - Horizontal movement only

- `translateY()` - Vertical movement only

---
## Combining Transforms
> You can combine multiple transforms in one declaration:
```js
.element {
  transform: scale(1.2) rotate(15deg) translate(10px, 5px);
}
```
**Note:-** Order matters! The sequence changes the final result.

---

# What is CSS animation?
> CSS animations allow you to create smooth, step-by-step transitions of an element’s style using keyframes.
## 1. Creating Animations with @keyframes
> @keyframes defines the animation sequence:
```js
@keyframes animation-name {
  0% { /* Starting style */ }
  50% { /* Middle style */ }
  100% { /* Ending style */ }
}
```

## Example: Fade In
```js
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
```

## Basic Example: Slide Box
```js
//  HTML

<div class="box"></div>
```
```js
//  CSS

.box {
  width: 100px;
  height: 100px;
  background-color: red;

  animation-name: slide;
  animation-duration: 2s;
}

/* Define the animation */
@keyframes slide {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(200px);
  }
}
```
---
## 2. Applying Animations
- Essential Animation Properties

| **Property**                | **Description**                              | **Example**                     |
| --------------------------- | -------------------------------------------- | ------------------------------- |
| `animation-name`            | The `@keyframes` name to use                 | `fadeIn`                        |
| `animation-duration`        | Duration of the animation                    | `1s`, `2s`, `500ms`             |
| `animation-timing-function` | Speed curve of the animation                 | `ease-in-out`, `linear`         |
| `animation-delay`           | Delay before animation starts                | `0.5s`, `2s`                    |
| `animation-iteration-count` | Number of times animation runs               | `1`, `3`, `infinite`            |
| `animation-direction`       | Direction of play (normal/reverse/alternate) | `alternate`                     |
| `animation-fill-mode`       | How styles apply before/after                | `forwards`, `backwards`, `both` |


### Shorthand Syntax
```js
.element {
  animation: name duration timing-function delay iteration-count direction fill-mode;
}
```
### Example Usage
```js
.box {
  animation: fadeIn 1s ease-in-out 0.5s 1 normal forwards;
}

/* Equivalent to: */
.box {
  animation-name: fadeIn;
  animation-duration: 1s;
  animation-timing-function: ease-in-out;
  animation-delay: 0.5s;
  animation-iteration-count: 1;
  animation-direction: normal;
  animation-fill-mode: forwards;
}
```
