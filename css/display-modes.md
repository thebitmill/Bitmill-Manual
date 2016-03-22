# Display Modes

The most basic property in CSS is the display property. The four most important
values it can be set as is none, inline, block, inline-block and flex.

As usual, read the applicable chapters in

+ Oreilly "CSS3: The Missing Manual" (4th Edition)

+ [CSS Tricks "Display Property"](https://css-tricks.com/almanac/properties/d/display)
+ [CSS Tricks "Display Run-In"](https://css-tricks.com/run-in)

## None

Different from `visibility: hidden;`.

## Block

TODO copy in a list of default block tags
Also see [Box Model](./box-model.md)

## Inline

TODO copy in a list of default inline tags

## Inline-block


TODO copy in a list of default inline-block tags

Inline-block creates an element where the element itself is inline with otherobjects around, but the inside of the box is formatted as block-level box.Inline block can be a useful alternative to floating block elements (discussedbelow). It is also, very annoyingly, one of the only ways to vertically alignelements in relation to each other in CSS. Flexbox is promising, but support intodays browsers is shaky at best.

There is an exhaustive list of all display modes at w3schools:

<http://www.w3schools.com/cssref/pr_class_display.asp>

## Block vs Inline

Below, 'some text' is actually inline, but unstylable.

```
<div>
	Some text
	<div>Nested text</div>
	<span>More text</span>
</div>
```
