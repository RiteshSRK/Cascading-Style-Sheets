# 🔹 What is Flexbox?
> FlexBox arranging items in rows or columns with smart spacing and alignment.  <br>
> And flexbox is one-dimensional layout method.

## 1. Start Flexbox
```bash
.container {
  display: flex; /* Turns on Flexbox */
}
```
## 2. Key Flexbox Properties
### A) flex-direction (Flow Direction)
| **Value**        | **Effect**              |
| ---------------- | ----------------------- |
| `row`            | Left-to-right (default) |
| `row-reverse`    | Right-to-left           |
| `column`         | Top-to-bottom           |
| `column-reverse` | Bottom-to-top           |

```bash
.container {
  flex-direction: column; /* Stacks items vertically */
}
```

### B) justify-content (Horizontal Alignment)
> Controls spacing flex direction (main axis).

| **Value**       | **Effect**                                  |
| --------------- | ------------------------------------------- |
| `flex-start`    | Left-aligned (default)                      |
| `flex-end`      | Right-aligned                               |
| `center`        | Centered horizontally                       |
| `space-between` | Equal gaps **between** items                |
| `space-around`  | Equal gaps **around** each item             |
| `space-evenly`  | Equal gaps **between and around** all items |

### C) align-items (Vertical Alignment)
> Controls spacing flex direction (cross axis).

| **Value**    | **Effect**                                         |
| ------------ | -------------------------------------------------- |
| `stretch`    | Items stretch to fill container height *(default)* |
| `flex-start` | Items align to the **top** of the container        |
| `flex-end`   | Items align to the **bottom** of the container     |
| `center`     | Items are **vertically centered**                  |
| `baseline`   | Items align along their **text baselines**         |

### D) gap (Spacing Between Items)
> Adds gaps **between** flex items (no margins needed!).
```bash
.container {
  gap: 20px; /* Space between all items */
}
```

## 3. Practical Examples
### Navigation Bar
```bash
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}
```
### Centered Card
```bash
.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
}
```

## Pro Tips
- Use `flex: 1` to make items fill available space
```bash
.item { flex: 1; } /* All items grow equally */
```
- Add flex-wrap: wrap for responsive wrapping
- Combine with margin: auto for smart spacing

---

# 🔹 What is CSS Grid?
> Grid is a powerful 2D layout system and that create complex designs with rows and columns.


---

# ✅ What Are Media Queries?
> **Media queries** allow you to apply different styles for different screen sizes or device types.

## Syntax
```bash
@media (condition) {
  /* CSS rules for that condition */
}
```

## 🔸 Common Media Query Syntax
| **Breakpoint** | **Use Case**                   | **Example**                       |
| -------------- | ------------------------------ | --------------------------------- |
| `max-width`    | Apply styles **below** a width | `@media (max-width: 768px)`       |
| `min-width`    | Apply styles **above** a width | `@media (min-width: 1024px)`      |
| `min-height`   | Based on screen height         | `@media (min-height: 600px)`      |
| `orientation`  | Landscape or portrait          | `@media (orientation: landscape)` |

## 📱 Breakpoint Examples
| **Device Type** | **Width Range**  | **Media Query**                                     |
| --------------- | ---------------- | --------------------------------------------------- |
| Mobile          | 0 – 480px        | `@media (max-width: 480px)`                         |
| Tablets         | 481px – 768px    | `@media (min-width: 481px) and (max-width: 768px)`  |
| Laptops         | 769px – 1024px   | `@media (min-width: 769px) and (max-width: 1024px)` |
| Desktops        | 1025px and above | `@media (min-width: 1025px)`                        |

### 🧪 Example
```bash
/* Base style */
body {
  font-size: 16px;
}

/* Tablets */
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}

/* Mobile */
@media (max-width: 480px) {
  body {
    font-size: 12px;
  }
}
```
# Advanced Techniques
## 🎯 Pro Tip
### You can combine queries:
```bash
@media (min-width: 600px) and (max-width: 900px) {
  .container {
    padding: 20px;
  }
}
```
---
## Combined Conditions
```bash
/* Applies only to tablets in landscape */
@media (min-width: 768px) and (orientation: landscape) {
  /* ... */
}
```