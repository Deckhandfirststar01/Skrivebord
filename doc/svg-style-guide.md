# SVG Style Guide

## When to use SVG

SVG is an XML based Vector Graphics format as such it makes sense to use when
ever something need to be scaleable and consists of different shapes, it
doesn't make sense to SVG use for pictures.

## Application

Most of the time you want to use an ```<img>``` tag to include the SVG into the
document. In case you need to alter the src of the SVG itself it might make
sense to embed it using ```<svg>``` tags.

## Sprites

Whenever an assets needs to change over the course of it's lifetime (custom
checkbox input, icon with states (hover, disabled, focused)), it makes sense to
combine the different states into a single SVG file.

Every asset represents a logical entity (an icon, a button, toggle). If the
entity can have different states that need to be represented visually we need
different "images", one for each state.

To avoid scattering the different states of the "logical entity" across
multiple files use don't create multiple files. SVG allows us to handle this
more elegenatly by using:

[SVG CSS](https://www.w3.org/TR/SVG/styling.html#StylingWithCSS)

```svg
<svg xmlns="http://www.w3.org/2000/svg">
  <style type="text/css">
    <![CDATA[
    .icon:hover { fill: red; }
    ]]>
  </style>
  <!-- rest of the icon -->
</svg>
```

If that's not sufficient create use an svg sprite using [Fragment Identifiers](https://css-tricks.com/svg-fragment-identifiers-work/)


Create a [viewBox](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/viewBox) for each icon.
```svg
<view id="icon-a" viewBox="0 0 32 32" />
<view id="icon-b" viewBox="32 0 32 32" />
<view id="icon-c" viewBox="63 0 32 32" />
```

For easy reference in html.
```html
<img src="sprite.svg#icon-a" alt="Icon a">
<img src="sprite.svg#icon-c" alt="Icon b">
<img src="sprite.svg#icon-d" alt="Icon c">
```

***NOTE:*** This technique doesn't [work in all Browsers](http://caniuse.com/#feat=svg-fragment)

## Optimization

Generated SVG files often contain a lot of unnessesary or redundant information
which can be safely removed to safe bandwith.

Use [SVGO](https://github.com/svg/svgo) to optimize your SVG file. SVGO also
exists as a [webapp](https://jakearchibald.github.io/svgomg/) so you can use it
without installing anything.

## Accessibility

***NOTE***: This is not stricly SVG related, but because we have no
accessibility guidelines yet we have included it here for now.

- When embedding an SVG using img tags always add alt tags, see [WCAG 1.1](https://www.w3.org/TR/2008/REC-WCAG20-20081211/#text-equiv)
- When creating SVGs for user interaction honor the
[WCAG 1.4.3 Contrast (Minimum)](https://www.w3.org/TR/2008/REC-WCAG20-20081211/#visual-audio-contrast-contrast)
guidelines.

## Compatibility

If you need to support IE8 you can create a PNG from the SVG and use it as its *1x srcset*.

```html
<img src="example-1x.png" srcset="example-2x.svg 2x">
```

## Resources

- [How Designers Should Think About SVG](https://medium.com/sketch-app-sources/how-designers-should-think-about-svg-b2b92efc4d77)
- [A Practical Guide to SVGs on the web](https://svgontheweb.com/)
- [SVG Guidelines - Mozilla | MDN](https://developer.mozilla.org/en-US/docs/Mozilla/Developer_guide/SVG_Guidelines)
- [An Overview of SVG Sprite Creation Techniques](https://24ways.org/2014/an-overview-of-svg-sprite-creation-techniques/)
- [How SVG Fragment Identifiers Work](https://css-tricks.com/svg-fragment-identifiers-work/)

## Tools

- [svgo](https://github.com/svg/svgo)
