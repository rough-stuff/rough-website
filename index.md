---
layout: home-layout.njk
---

## Rough.js

**Rough.js** is a small (<9kB gzipped) graphics library that lets you draw in a _sketchy_, _hand-drawn-like_, style.
The library defines primitives to draw lines, curves, arcs, polygons, circles, and ellipses. It also supports drawing [SVG paths](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths).

Rough.js works with both [Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) and [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG).

![Rough.js sample](/images/cap.png)


## Install

Install from npm:

```bash
npm install --save roughjs
```

And use it in your code:

```javascript
import rough from 'roughjs';
```

## Usage

View [Full Rough.js API](https://github.com/rough-stuff/rough/wiki) is available on Github. 

![Rough.js rectangle](/images/m1.png)

```js
const rc = rough.canvas(document.getElementById('canvas'));
rc.rectangle(10, 10, 200, 200); // x, y, width, height
```

or SVG

```js
const rc = rough.svg(svg);
let node = rc.rectangle(10, 10, 200, 200); // x, y, width, height
svg.appendChild(node);
```

## Lines and Ellipses

![Rough.js rectangle](/images/m2.png)

```js
rc.circle(80, 120, 50); // centerX, centerY, diameter
rc.ellipse(300, 100, 150, 80); // centerX, centerY, width, height
rc.line(80, 120, 300, 100); // x1, y1, x2, y2
```

## Filling

![Rough.js rectangle](/images/m3.png)

```js
rc.circle(50, 50, 80, { fill: 'red' }); // fill with red hachure
rc.rectangle(120, 15, 80, 80, { fill: 'red' });
rc.circle(50, 150, 80, {
  fill: "rgb(10,150,10)",
  fillWeight: 3 // thicker lines for hachure
});
rc.rectangle(220, 15, 80, 80, {
  fill: 'red',
  hachureAngle: 60, // angle of hachure,
  hachureGap: 8
});
rc.rectangle(120, 105, 80, 80, {
  fill: 'rgba(255,0,200,0.2)',
  fillStyle: 'solid' // solid fill
});
```

Fill styles can be: **hachure**(default), **solid**, **zigzag**, **cross-hatch**, **dots**, **sunburst**, **dashed**, or **zigzag-line**

![Rough.js fill examples](/images/m14.png)

## Sketching style

![Rough.js rectangle](/images/m4.png)

```js
rc.rectangle(15, 15, 80, 80, { roughness: 0.5, fill: 'red' });
rc.rectangle(120, 15, 80, 80, { roughness: 2.8, fill: 'blue' });
rc.rectangle(220, 15, 80, 80, { bowing: 6, stroke: 'green', strokeWidth: 3 });
```

## SVG Paths

![Rough.js rectangle](/images/m5.png)

```js
rc.path('M80 80 A 45 45, 0, 0, 0, 125 125 L 125 80 Z', { fill: 'green' });
rc.path('M230 80 A 45 45, 0, 1, 0, 275 125 L 275 80 Z', { fill: 'purple' });
rc.path('M80 230 A 45 45, 0, 0, 1, 125 275 L 125 230 Z', { fill: 'red' });
rc.path('M230 230 A 45 45, 0, 1, 1, 275 275 L 275 230 Z', { fill: 'blue' });
```

SVG Path with simplification:

![Rough.js rectangle](/images/m9.png) ![Rough.js rectangle](/images/m10.png)

## Examples

![Rough.js map](/images/m6.png)

[View examples here](https://github.com/rough-stuff/rough/wiki/Examples)

## API & Documentation

[Full Rough.js API](https://github.com/rough-stuff/rough/wiki)



## Credits

Core algorithms for drawing lines and ellipse outlines were adapted from [handy](https://www.gicentre.net/software/#/handy/) processing lib.

Algorithm to convert SVG arcs to Canvas [described here](https://www.w3.org/TR/SVG/implnote.html) was adapted from [Mozilla codebase](https://hg.mozilla.org/mozilla-central/file/17156fbebbc8/content/svg/content/src/nsSVGPathDataParser.cpp#l887)


## Support this project

Support development of this project by sponsoring on [Open Collective](https://opencollective.com/rough) or [Github](https://github.com/sponsors/pshihn).

This project is supported by:

<a href="https://www.diagrams.net/" target="_blank" rel="noopener" class="sponsor-card">
  <img style="width: 90px; height: 90px; margin-right: 8px;" src="https://avatars.githubusercontent.com/u/1769238?s=96&v=4">
  <div>
    <h5>Diagrams.net</h5>
    <div>Security-first diagramming for teams.</div>
  </div>
</a>

<a href="https://sheetjs.com/" target="_blank" rel="noopener" class="sponsor-card">
  <img style="width: 90px; height: 90px; margin-right: 8px;" src="/images/sponsors/sheetjs.png">
  <div>
    <h5>SheetJS</h5>
    <div>Spreadsheets simplified.
Read, edit, and export spreadsheets.
Works in web browsers and servers.
Supports every Excel file format.</div>
  </div>
</a>



## License
[MIT License](https://github.com/rough-stuff/rough/blob/master/LICENSE) (c) [Preet Shihn](https://twitter.com/preetster)

## Sponsors

This project is supported by:

<a href="https://sheetjs.com/" target="_blank" rel="noopener" class="sponsor-card">
  <img style="width: 90px; height: 90px; margin-right: 8px;" src="/images/sponsors/sheetjs.png">
  <div>
    <h5>SheetJS</h5>
    <div>Spreadsheets simplified.
Read, edit, and export spreadsheets.
Works in web browsers and servers.
Supports every Excel file format.</div>
  </div>
</a>
<p></p>

<div id="sponsorPanel">
<p>This project is supported by:</p>
<a href="https://sheetjs.com/" target="_blank" rel="noopener" class="sponsor-card">
  <img style="width: 90px; height: 90px; margin-right: 8px;" src="/images/sponsors/sheetjs.png">
  <div>
    <h5>SheetJS</h5>
    <div>Spreadsheets simplified.
Read, edit, and export spreadsheets.
Works in web browsers and servers.
Supports every Excel file format.</div>
  </div>
</a>
</div>
