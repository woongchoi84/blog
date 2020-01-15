---
layout: post
title: "[Blog] CSS Modifications"
description: "CSS Modifications Test!!!"
tags: Blog
---

# Head Color

## '_sass/dash/_base.css' file

```css
h1, h2, h3, h4, h5, h6 {
  color: $color-blue;
}

h1 {
  color: $color-red;
}
```

- 'h1 { ... }' block is overwritten.

# List

## '_sass/dash/_base.css' file

```css
/**
 * Lists
 */
ul, ol {
  margin-left: $spacing-unit;
}

ul {
  display: list-item;
  color: $color-ulist;
}

li {
  padding-left: 10px; 
  > ul,
  > ol {
    margin-bottom: 0;
  }
}
```

1. 'ul { ... }' block is added.

2. 'padding-left: 10px;' is added in 'li { ... }' block
