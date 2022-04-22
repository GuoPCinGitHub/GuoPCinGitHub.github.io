---
layout: post
title: SVG Learning - 1
tags: 学习
---

SVG 学习第一部分，包括基本结构、`<line>`、`<rect>`、`<circle>`和`<ellipse>`图形元素。简单罗列，英文为主。

> References
>
> - [An SVG Primer for Today's Browsers](https://www.w3.org/Graphics/SVG/IG/resources/svgprimer.html)
>   - [Copyright](http://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2010 [W3C](http://www.w3.org/)® ([MIT](http://www.csail.mit.edu/), [ERCIM](http://www.ercim.org/), [Keio](http://www.keio.ac.jp/)), All Rights Reserved.

## Basic structure

```html
<svg xmlns="http://www.w3.org/2000/svg">
    ……
</svg>
```

### Example

```html
<svg xmlns="http://www.w3.org/2000/svg">
    <circle  cx="50" cy="50" r="50" fill="wheat"/>
</svg>
```

<svg xmlns="http://www.w3.org/2000/svg" width=100 height=100>
    <circle  cx="50" cy="50" r="50" fill="wheat"/>
</svg>

## SVG graphics elements

- `<path>`
- `<line>`
- `<rect>`
- `<circle>`
- `<line>`
- `<polyline>`
- `<polygon>`
- `<image>`
- `<use>`

### `<line>`

- `x1`, `y1` → `x2`, `y2`
  - `x1`, `y1`: Start position
  - `x2`, `y2`: End position

#### `stroke` & `stroke-width`

The effect of varying stroke widths

```html
<line x1="5" y1="10" x2="99" y2="30" stroke-width=".5" stroke="red"/>

<line x1="5" y1="30" x2="99" y2="50" stroke-width="1" stroke="red"/>

<line x1="5" y1="50" x2="99" y2="70" stroke-width="2.5" stroke="red"/>

<line x1="5" y1="70" x2="99" y2="90" stroke-width="4" stroke="blue"/>
```

<svg xmlns="http://www.w3.org/2000/svg" width=100 height=100>
    <line x1="5" y1="10" x2="99" y2="30" stroke-width=".5" stroke="red"/>
    <line x1="5" y1="30" x2="99" y2="50" stroke-width="1" stroke="red"/>
    <line x1="5" y1="50" x2="99" y2="70" stroke-width="2.5" stroke="red"/>
    <line x1="5" y1="70" x2="99" y2="90" stroke-width="4" stroke="blue"/>
</svg>

#### `stroke-dasharray` & `stroke-lineup`

The effect of other attributes on line elements

```html
<line x1="15" y1="15" x2="140" y2="135" stroke-width="25" stroke="blue" stroke-linecap="round"/>

<line x1="15" y1="15" x2="140" y2="135" stroke-width="25" stroke="aqua" stroke-dasharray="8,3,2,18"/>

<line x1="15" y1="155" x2="160" y2="60" stroke-width="25" stroke="blue"/>

<line x1="15" y1="155" x2="160" y2="60" stroke-width="25" stroke="orange" stroke-dasharray="8,3,2"/>
```

<svg xmlns="http://www.w3.org/2000/svg" width=200 height=200>
    <line x1="15" y1="15" x2="140" y2="135" stroke-width="25" stroke="blue" stroke-linecap="round"/>
    <line x1="15" y1="15" x2="140" y2="135" stroke-width="25" stroke="aqua" stroke-dasharray="8,3,2,18"/>
    <line x1="15" y1="155" x2="160" y2="60" stroke-width="25" stroke="blue"/>
    <line x1="15" y1="155" x2="160" y2="60" stroke-width="25" stroke="orange" stroke-dasharray="8,3,2"/>
</svg>

### `<rect>`

- `x`, `y`: Top-left corner position
- `height`, `width`

A variety of rectangles

```html
<rect x="62" y="25" height="110" width="16" fill="rgb(100%,50%,50%)" stroke="black" stroke-width="2"/>

<rect x="35" y="35" height="30" width="50" fill="red" stroke="black" stroke-width="2"/>

<rect x="5" y="60" height="30" width="50" fill="#f88" stroke="black" stroke-width="2"/>

<rect x="25" y="70" height="30" width="50" fill="#ff8888" stroke="black" stroke-width="2"/>

<rect x="65" y="60" height="30" width="50" fill="#eac" stroke="black" stroke-width="2"/>

<rect x="85" y="70" height="30" width="50" fill="#eeaacc" stroke="black" stroke-width="2"/>

<rect x="60" y="95" height="30" width="50" fill="rgb(255,0,0)" stroke="black" stroke-width="2"/>
```

<svg xmlns="http://www.w3.org/2000/svg" width=150 height=150>
    <rect x="62" y="25" height="110" width="16" fill="rgb(100%,50%,50%)" stroke="black" stroke-width="2"/>
    <rect x="35" y="35" height="30" width="50" fill="red" stroke="black" stroke-width="2"/>
    <rect x="5" y="60" height="30" width="50" fill="#f88" stroke="black" stroke-width="2"/>
    <rect x="25" y="70" height="30" width="50" fill="#ff8888" stroke="black" stroke-width="2"/>
    <rect x="65" y="60" height="30" width="50" fill="#eac" stroke="black" stroke-width="2"/>
    <rect x="85" y="70" height="30" width="50" fill="#eeaacc" stroke="black" stroke-width="2"/>
    <rect x="60" y="95" height="30" width="50" fill="rgb(255,0,0)" stroke="black" stroke-width="2"/>
</svg>

### `<circle>`

- `cx`, `cy`: Centre position
- `r`: Radius

Circles with varying fill, stroke, stroke-width and stroke-dasharray

```html
<circle cx="80" cy="50" r="40"/>

<circle cx="80" cy="110" r="40" fill="red"/>

<circle cx="80" cy="170" r="40" fill="yellow" stroke="blue" />

<circle cx="80" cy="160" r="20" fill="red" stroke="black" stroke-width="10"/>

<circle cx="140" cy="110" r="60" fill="none" stroke="#579" stroke-width="30" stroke-dasharray="3,5,8,13">
```

<svg xmlns="http://www.w3.org/2000/svg" width=250 height=250>
    <circle cx="80" cy="50" r="40"/>
    <circle cx="80" cy="110" r="40" fill="red"/>
    <circle cx="80" cy="170" r="40" fill="yellow" stroke="blue" />
    <circle cx="80" cy="160" r="20" fill="red" stroke="black" stroke-width="10"/>
    <circle cx="140" cy="110" r="60" fill="none" stroke="#579" stroke-width="30" stroke-dasharray="3,5,8,13">
</svg>

### `<ellipse>`

- `cx`, `cy`: Centre position
- `rx`: Half of the distance from the leftmost side to centre
- `ry`: Half of the distance from top to centre

```html
<ellipse cx="80" cy="110" rx="75" ry="105" fill="#538"/>

<ellipse cx="80" cy="110" rx="60" ry="40" fill="black" stroke="red" stroke-width="25"/>

<ellipse cx="80" cy="110" rx="35" ry="20" fill="#538" stroke="yellow" stroke-width="25"/>

<ellipse cx="80" cy="50" rx="40" ry="30" fill="red" stroke="black" stroke-width="25"/>

<ellipse cx="80" cy="50" rx="30" ry="20" fill="orange" stroke="red" stroke-width="10"/>

<ellipse cx="80" cy="170" rx="40" ry="30" fill="yellow" stroke="orange" stroke-width="25" />

<ellipse cx="80" cy="170" rx="30" ry="20" fill="red" stroke="black" stroke-width="10"/>
```

<svg xmlns="http://www.w3.org/2000/svg" width=200 height=250>
    <ellipse cx="80" cy="110" rx="75" ry="105" fill="#538"/>
    <ellipse cx="80" cy="110" rx="60" ry="40" fill="black" stroke="red" stroke-width="25"/>
    <ellipse cx="80" cy="110" rx="35" ry="20" fill="#538" stroke="yellow" stroke-width="25"/>
    <ellipse cx="80" cy="50" rx="40" ry="30" fill="red" stroke="black" stroke-width="25"/>
    <ellipse cx="80" cy="50" rx="30" ry="20" fill="orange" stroke="red" stroke-width="10"/>
    <ellipse cx="80" cy="170" rx="40" ry="30" fill="yellow" stroke="orange" stroke-width="25" />
    <ellipse cx="80" cy="170" rx="30" ry="20" fill="red" stroke="black" stroke-width="10"/>
</svg>
