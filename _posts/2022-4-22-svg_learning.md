---
layout: post
title: SVG Learning - 1
tags: 学习
---

<div lang="en">

References

- [An SVG Primer for Today's Browsers](https://www.w3.org/Graphics/SVG/IG/resources/svgprimer.html)
  - [Copyright](http://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2010 [W3C](http://www.w3.org/)® ([MIT](http://www.csail.mit.edu/), [ERCIM](http://www.ercim.org/), [Keio](http://www.keio.ac.jp/)), All Rights Reserved.
- [SVG Tutorial - SVG: Scalable Vector Graphics | MDN](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial)
  - [SVG Tutorial](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial) by [Mozilla Contributors](https://developer.mozilla.org/en-US/docs/MDN/About/contributors.txt) is licensed under [CC-BY-SA 2.5](https://creativecommons.org/licenses/by-sa/2.5/).

## Basic structure

```html
<svg xmlns="http://www.w3.org/2000/svg">
    ……
</svg>
```

### Example

**SVG Code**

```html
<svg xmlns="http://www.w3.org/2000/svg">
    <circle  cx="50" cy="50" r="50" fill="wheat"/>
</svg>
```

**Outcome**

<svg xmlns="http://www.w3.org/2000/svg">
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

- $(x_1, y_1) \xrightarrow[]{\mathtt{stroke}} (x_2, y_2)$
  - $(x_1, y_1)$: Start position
  - $(x_2, y_2)$: End position

#### `stroke` & `stroke-width`

**SVG Code**

```html
<line x1="5" y1="10" x2="99" y2="30" stroke-width=".5" stroke="red"/>

<line x1="5" y1="30" x2="99" y2="50" stroke-width="1" stroke="red"/>

<line x1="5" y1="50" x2="99" y2="70" stroke-width="2.5" stroke="red"/>

<line x1="5" y1="70" x2="99" y2="90" stroke-width="4" stroke="blue"/>
```

**Illustration**

![The effect of varying stroke widths](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m42c2d85a.png "The effect of varying stroke widths")

#### `stroke-dasharray` & `stroke-lineup`

**SVG Code**

```html
<line x1="15" y1="15" x2="140" y2="135" stroke-width="25" stroke="blue" stroke-linecap="round"/>

<line x1="15" y1="15" x2="140" y2="135" stroke-width="25" stroke="aqua" stroke-dasharray="8,3,2,18"/>

<line x1="15" y1="155" x2="160" y2="60" stroke-width="25" stroke="blue"/>

<line x1="15" y1="155" x2="160" y2="60" stroke-width="25" stroke="orange" stroke-dasharray="8,3,2"/>
```

**Illustration**

![The effect of other attributes on line elements](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m64bf4551.png "The effect of other attributes on line elements")

### `<rect>`

- $(x, y) \xrightarrow[\mathtt{width}]{\mathtt{height}} \xrightarrow[\mathtt{fill}]{\mathtt{stroke}}$
  - $(x, y)$: Top-left corner position

**SVG Code**

```html
<rect x="62" y="25" height="110" width="16" fill="rgb(100%,50%,50%)" stroke="black" stroke-width="2"/>

<rect x="35" y="35" height="30" width="50" fill="red" stroke="black" stroke-width="2"/>

<rect x="5" y="60" height="30" width="50" fill="#f88" stroke="black" stroke-width="2"/>

<rect x="25" y="70" height="30" width="50" fill="#ff8888" stroke="black" stroke-width="2"/>

<rect x="65" y="60" height="30" width="50" fill="#eac" stroke="black" stroke-width="2"/>

<rect x="85" y="70" height="30" width="50" fill="#eeaacc" stroke="black" stroke-width="2"/>

<rect x="60" y="95" height="30" width="50" fill="rgb(255,0,0)" stroke="black" stroke-width="2"/>
```

**Illustration**

![A variety of rectangles](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/5e23cc1b.png "A variety of rectangles")

### `<circle>`

- $(c_x, c_y) \xrightarrow[]{r} \xrightarrow[\mathtt{fill}]{\mathtt{stroke}}$
  - $(c_x, c_y)$: Centre position
  - $r$: Radius

**SVG Code**

```html
<circle cx="80" cy="50" r="40"/>

<circle cx="80" cy="110" r="40" fill="red"/>

<circle cx="80" cy="170" r="40"
fill="yellow" stroke="blue" />

<circle cx="80" cy="160" r="20" fill="red" stroke="black" stroke-width="10"/>

<circle cx="140" cy="110" r="60" fill="none" stroke="#579" stroke-width="30"
stroke-dasharray="3,5,8,13">
```

**Illustration**

![Circles with varying fill, stroke, stroke-width and stroke-dasharray](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m3e417928.png "Circles with varying fill, stroke, stroke-width and stroke-dasharray")

### `<ellipse>`

- $(c_x, c_y, r_x, r_y) \xrightarrow[\mathtt{fill}]{\mathtt{stroke}}$
  - $(c_x, c_y)$: Centre position
  - $r_x$: Half of the distance from the leftmost side to centre
  - $r_y$: Half of the distance from top to centre

**SVG Code**

```html
<ellipse cx="80" cy="110" rx="75" ry="105" fill="#538"/>

<ellipse cx="80" cy="110" rx="60" ry="40" fill="black" stroke="red" stroke-width="25"/>

<ellipse cx="80" cy="110" rx="35" ry="20" fill="#538" stroke="yellow" stroke-width="25"/>

<ellipse cx="80" cy="50" rx="40" ry="30" fill="red" stroke="black" stroke-width="25"/>

<ellipse cx="80" cy="50" rx="30" ry="20" fill="orange" stroke="red" stroke-width="10"/>

<ellipse cx="80" cy="170" rx="40" ry="30" fill="yellow" stroke="orange" stroke-width="25" />

<ellipse cx="80" cy="170" rx="30" ry="20" fill="red" stroke="black" stroke-width="10"/>
```

**Illustration**

![Identical clusters of ellipses except for stroke-dasharray. The ellipses on the left use dash array, those on the right do not. ](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m75ab8246.png "Identical clusters of ellipses except for stroke-dasharray. The ellipses on the left use dash array, those on the right do not. ")

### `<path>`

#### `M` & `L`

- `M x y`: Move pen to $(x, y)$
- `M x1,y1[ x2,y2[…]]`: Move pen to $(x_1, y_1)$, then $(x_2, y_2)$, …
- `M x1 y1 L x2 y2[ x3 y3[…]]`, `M x1 y1 L x2,y2[ x3,y3[…]]`: Draw linearly from $(x_1, y_1)$ to $(x_2, y_2)$, then $(x_3, y_3)$, …

**SVG Code**

```html
<path stroke="black" d="M 100 100 L 200 200"/>
```

**Illustration**

![A diagonal line from (100,100) to (200,200)](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m40b9361c.png "A diagonal line from (100,100) to (200,200)")

**SVG Code**

```html
<path d="M 100 100 L 200 200 100 150"/>
```

**Illustration**

![Concatenated pairs of coordinates](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m6b9cad89.png "Concatenated pairs of coordinates")

**SVG Code**

```html
<path d="M 50,100 150,200 50,150"/>

<path d="M 100 50 L 200 150 100 100" fill="none" stroke="black"/>
```

![The effect of adding fill="none" (but note that the stroke attribute is defined) ](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m6daeff2a.png "The effect of adding fill=\"none\" (but note that the stroke attribute is defined) ")

- `z`: Close path

**SVG Code**

```html
<path d="M 100,50 200,150 100,100" fill="none" stroke="black"/>

<path d="M 100,50 200,150 100,100 z" fill="none" stroke="black"/>
```

#### `fill-rule="even-odd"`

**SVG Code**

```html
<path d="M 70,290 L 150,150 200,250 40,250 100,150 170,290"/>

<path d="M 70,290 L 150,150 200,250 40,250 100,150 170,290" fill-rule="evenodd"/>
```

![An example to show the difference between the default and "even-odd" fill rules](https://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/798df064.png "An example to show the difference between the default and \"even-odd\" fill rules")

![An example to show the difference between the default and "even-odd" fill rules](https://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/2329cb12.png "An example to show the difference between the default and \"even-odd\" fill rules")

#### Combine multiple path segments

**SVG Code**

```html
<path fill="orange"
    d="M 10,215 210,215 110,42 z
    M 10,100 210,100 110,273 z"
    stroke="purple" stroke-width="3"/>
```

![A <path> with fill="green" et cetera... is also included in the drawing.](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m36f8c292.png "A <path> with fill=\"green\" et cetera... is also included in the drawing.")

#### `Q`: Quadratic Bézier curves

- `M x1 y1 Q x2,y2 x3,y3`: Draw quadratically from $(x_1, y_1)$, then $(x_2, y_2)$, towards $(x_3, y_3)$

**SVG Code**

```html
<path d="M 100 200 Q 200,400 300,200" fill="none" stroke="blue" />

<path d="M 100 200 L 200,400 300,200" fill="none" stroke="red"/>
```

**Illustration**

![Bézier curve example](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m69cd8b78.png "Bézier curve example")

**SVG Code**

```html
<path fill-rule="evenodd"
    d="M 70 140 L 150,0 200,100 L 40,100 100,0 L 170,140 70 140"/>

<path fill="red" fill-rule="evenodd"
    d="M 70 140 Q 150,0 200,100 Q 40,100 100,0 Q 170,140 70 140"/>
```

**Illustration**

![An example of a graphic using a quadratic spline](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/me702c4.png "An example of a graphic using a quadratic spline")

### `C`: Cubic Bézier curves

- `M x1 y1 C xt1,yt1[ xt2,yt2[…]] x3,y3`: Draw cubically from $(x_1, y_1)$ to $(x_3, y_3)$, with control points $(x_{t_1}, y_{t_1})$, $(x_{t_2}, y_{t_2})$, …

![A family of cubic curves sharing endpoints and tangents](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m499a2128.png "A family of cubic curves sharing endpoints and tangents")

![Limiting case for a family of curves](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/mcbf3920.png "Limiting case for a family of curves")

![Cubic beziers sharing tangents and endpoints](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m31556306.png "Cubic beziers sharing tangents and endpoints")

![Adjoining two cubic curves smoothly](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m5fbfc0c1.png "Adjoining two cubic curves smoothly")

**SVG Code**

```html
<path stroke="black" stroke-width="3" fill="#eec1c2"
d="M 99 192
C 137 160 204 133 141 124
C 78 115 34 167 47 129
C 60 91 20 65 77 71
C 134 77 206 43 196 101
C 186 159 118 368 119 299
C 120 230 201 169 138 206
C 75 243 53 231 99 192" />
```

**Illustration**

![Several smoothly stitched Bézier segments](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/4418afb.png "Several smoothly stitched Bézier segments")

### `A`: Elliptical arc

![Four elliptical arcs sharing endpoints](http://www.w3.org/Graphics/SVG/IG/resources/StateOfArt/m38b4a957.png "Four elliptical arcs sharing endpoints")

</div>
