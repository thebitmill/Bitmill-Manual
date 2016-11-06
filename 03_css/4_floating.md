# Floating

Before flex-box, floating was essentially the only way to create
fluid and flexible layouts. Otherwise you had to resort to absolute positioning.

Learning to float your elements properly is detrimental to learning to layout a
page with CSS.Floating elements essentially lining them up in a rows, until
there is not space for another oneand then clearing and creating a new one.
Floating instead of using the position propertymakes for fluid designs that
adapt to screen sizes and varying sizes of dynamic contentsuch as images or
text. Once general layout is established, further adjustments can be done
withposition:absolute or position:relative. These should still be used with
caution and extensivetesting to ensure they are responsive.

As usual, read the applicable chapters in

+ Oreilly "CSS3: The Missing Manual" (4th Edition)
Also read the following links.

+ [CSS Tricks "All about floats"](https://css-tricks.com/all-about-floats/)

## Clearing

When you float elements you also need to decide how they are going to becleared
in relation to each other. Using the analogy that the floated elements become
linesof text (i.e letters), clearing is equivalent to a line-break. The
previous CSSTricks link covered it quickly, but the following two links cover
it in moredepth.

+ [CSS Tricks "The How and Why of Clearing Floats"](https://css-tricks.com/the-how-and-why-of-clearing-floats/)
+ [CSS Tricks "Why containers Don''t Clear Themselves"](https://css-tricks.com/containers-dont-clear-floats/)

There are several methods to clear floated elements, as is discussed in the two
resources above. The method we recommentis the micro clearfix hack, discussed
in depth in the following link:

Micro Clearfix Hack: http://nicolasgallagher.com/micro-clearfix-hack/

## Advanced Techniques

The grid in Foundation (at least up to v5) is based entirely around the
floating of elements. Study it closely to geta good understanding of how to
apply floats to create very complex layouts.

```css
.w { border: 1px solid #bbb;
    background: #eee;
}

.w > .i {
    width: 20%;
    height: 20%;
    border: 1px solid #333;
    background: #999;
}

css.w > .i {
    float: left;
}
```
