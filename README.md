# Day 2

### Responsive Web Design

- Set the viewport
- Size content to the viewport
- Use CSS media queries for responsiveness
- How to choose break points
- How to choose breakpoints

A multitude of different screen sizes exist across phones, "phablets," tablets, desktops, game consoles, TVs, and even wearables. A user could be using mouse and keyboard, a touch screen, a controller, or voice access controls.

##### [Viewport](https://www.w3schools.com/css/css_rwd_viewport.asp)

The viewport varies with the device, and will be smaller on a mobile phone than on a computer screen.

We can tell our document to match a screens width in "device-independent pixels". A device-independent pixel is a representation of a pixel which on pixel dense screens may contain many pixels.

```html
<head>
  ...
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  ...
</head>
```

- `width=device-width` does exactly what is sounds like
- Some browsers will keep the width constant when a device is turned sideways and just zoom in by tell in document `initial-scale=1` we are say there is a 1:1 relationship between the pixels and the screen regardless of orientation by setting the zoom(scale).
- If you are familiar with VS code Emmet and use `!` to initialize your document you will notice these setting are already in your document.

##### Size content to the Viewport

- Images: Set a `max-width: 100%` if an image is too large for a screen this will make sure that it doesn't overflow.
  - Despite overwriting the width with max-width it is important you still set the `width` and `height` this will make sure the webpage dedicates space for the images before they load.
- Layout: By using percentages instead of a set amount of pixels this well make sure your elements change depending on the size of your display.
- Flexbox: With flex box we can can display multiple elements on a single row or wrapped onto multiple rows as space decreases.

```css
div {
  display: flex;
}
```

- [Flexbox MDN Doc](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

- CSS Grid-Layout: Rather then creating columns with float and percentages, we could use grid layout and the `fr` unit
  - `fr` stand for fractional unit so with 3 column at `1fr 3fr 2fr`one column takes up 1/5 the screen 3/5, 2/5 respectively.

```css
section {
  display: grid;
  grid-template-columns: 1fr 3fr 2fr;
}
```

- [Grid MDN Doc](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids)

##### [Media Queries](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)

For example say you want your webpage to be print friendly you might have a css document specifically for print you can link the style sheet in your `<head>` or you can add it to your main style sheet with `@media print`

```html
<head>
  …
  <link rel="stylesheet" href="print.css" media="print" />
  …
</head>
```

```css
@media print {
  /*...*/
}
```

There are many more media queries for testing what kind of device a user has whether they have the ability to hover or tap and much more. On of the most common media queries is the `max-width` and `min-width` to establish break points for different blocks of css

##### Picking Break Points

This can be kinda subjective you can try using common device resolution width like 2048, 1024, 768/720, 480 but one of the best methods is to start with a design that looks best in a mobile format and then define different styles when it starts feel like there is too much white space.

```css
@media (min-width: 768px) and (max-width: 1024px) {
  section {
    display: flex;
    flex-direction: column;
  }
}
@media (min-width: 1024px) {
  section {
    display: flex;
  }
}
```

- Use browser dev tools to view different media break points

### [Flex Box](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

```css
.container {
  display: flex; /* or inline-flex */
  flex-direction: row | row-reverse | column | column-reverse;
  flex-wrap: nowrap | wrap | wrap-reverse;
  flex-flow: column wrap;
  justify-content: flex-start | flex-end | center | space-between | space-around
    | space-evenly | start | end | left | right... + safe | unsafe;
  align-items: stretch | flex-start | flex-end | center | baseline | first
    baseline | last baseline | start | end | self-start | self-end +... safe |
    unsafe;
  align-content: flex-start | flex-end | center | space-between | space-around |
    space-evenly | stretch | start | end | baseline | first baseline | last
    baseline +... safe | unsafe;
  gap: 10px 20px; /* row-gap column gap */
  row-gap: 10px;
  column-gap: 20px;
}
.item {
  order: 5; /* default is 0 */
  flex-grow: 4; /* default 0 */
  flex-shrink: 3; /* default 1 */
  flex-basis: | auto; /* default auto */
  flex: none | [ < "flex-grow" > < "flex-shrink" >? || < "flex-basis" > ]; /*short hand*/
  align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```
