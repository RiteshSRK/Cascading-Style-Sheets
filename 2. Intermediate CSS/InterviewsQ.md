## 1. `fixed` vs `sticky`

| `fixed` | `sticky` |
|---|---|
| Relative to viewport | Works within its scrolling/container context |
| Removed from normal flow | Remains in normal flow |
| Always fixed | Becomes sticky after reaching threshold |
| Usually stays visible during page scroll | Sticking depends on scrolling/container boundaries |

### Interview Answer  
A fixed element is positioned relative to the viewport and stays fixed during scrolling. A sticky element remains in the normal flow and becomes fixed-like after reaching a specified scrolling threshold.

---

## 2. `relative` vs `absolute`

| Relative | Absolute |
|---|---|
| Remains in normal flow | Removed from normal flow |
| Keeps original space | Does not occupy normal-flow space |
| Relative to its original position | Relative to its containing block |
| Useful for small adjustments | Useful for precise positioning |

### Interview Answer
Relative positioning keeps the element in the normal document flow and moves it from its original position. Absolute positioning removes the element from normal flow and positions it relative to its containing block.

---

## 3. `absolute` vs `fixed`

| Absolute | Fixed |
|---|---|
| Removed from normal flow | Removed from normal flow |
| Positioned relative to containing block | Positioned relative to viewport |
| Usually scrolls with page | Normally stays fixed during scrolling |
| Common for overlays/badges | Common for floating UI |

### Interview Answer
Absolute positioning is generally based on the element's containing block, while fixed positioning is based on the viewport.

## 4. `static` vs `relative`

| Static | Relative |
|---|---|
| Default position | Explicitly positioned |
| Normal flow | Normal flow |
| Offset properties don't normally work | Offset properties work |
| Cannot be used as a normal positioned ancestor for an absolute child | Can establish a positioning context |

## 5. The Offset Properties
The four main offset properties are:

```css
top
right
bottom
left
```

## 6. `z-index` and `Position`
When positioned elements overlap, you may need:

```css
.box1 {
  position: relative;
  z-index: 2;
}

.box2 {
  position: relative;
  z-index: 1;
}
```

## 7. Complete Comparison

| Property | Normal Flow? | Reference | Typical Use |
|---|---:|---|---|
| `static` | Yes | Normal flow | Default layout |
| `relative` | Yes | Own original position | Small movement / positioning context |
| `absolute` | No | Containing block | Badge, overlay, icon |
| `fixed` | No | Viewport | Floating button, fixed UI |
| `sticky` | Yes | Scroll/container context | Sticky navbar/sidebar |

---

## 8. Interview Explanation — Ready-to-Speak Answer
If an interviewer says:  
#### "Explain CSS position."

"The CSS position property controls how an element is positioned in the document. It has five commonly used values: static, relative, absolute, fixed, and sticky. Static is the default position and follows the normal document flow. Relative keeps the element in the normal flow but allows us to move it relative to its original position. Absolute removes the element from the normal flow and positions it relative to its containing block. Fixed removes the element from the normal flow and positions it relative to the viewport, so it normally stays in the same place while scrolling. Sticky keeps the element in the normal flow and makes it stick when a specified scrolling threshold is reached. We commonly use relative on a parent and absolute on a child when we need to position the child precisely inside the parent."

---

## 9. Final Revision Cheat Sheet

```
┌─────────────────────────────────────────────┐
│ CSS POSITION                                │
├─────────────────────────────────────────────┤
│                                             │
│ static                                      │
│ → Default                                   │
│ → Normal document flow                     │
│                                             │
│ relative                                    │
│ → Stays in normal flow                     │
│ → Moves from original position              │
│                                             │
│ absolute                                    │
│ → Removed from normal flow                 │
│ → Positioned relative to containing block  │
│                                             │
│ fixed                                       │
│ → Removed from normal flow                 │
│ → Relative to viewport                     │
│ → Normally stays during scrolling          │
│                                             │
│ sticky                                      │
│ → Remains in normal flow                   │
│ → Sticks after scroll threshold             │
│                                             │
└─────────────────────────────────────────────┘
```