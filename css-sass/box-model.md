# Box Model

A very subtle but extremely useful addition to CSS3 is the ability to choose
different box models. When an objectis set to display:block or
''display:inline-block'' it essentially becomes a box that adheres to a box
model.A box is composed of four parts; the content area, the padding, the
border anda margin. The sizes of these parts are styled individually using
height/width, padding,border and margin properties respectively.

Where it gets a little more confusing is how these properties relate to each
other.This is where the box-model property and its different values come in,
and makes life much much easier.

As usual, read the applicable chapters in

1. Oreilly "CSS3: The Missing Manual" (4th Edition)

CSS tricks cover it very well in the following link:

+ [CSS Tricks "Box-Sizing"](http://css-tricks.com/box-sizing)

## Different Box Models

You might be lead to believe there are more, such as `padding-box` but
these are generally not implemented.

### Content-box

Before CSS3 you could not change the box-sizing of your boxes, and all
wherecontent-boxes. This meant that the height and width properties set the
exact sizeof the content area, then padding, border and margin where added to
this. As a resultthe total size of the box is almost always much bigger than
the height or width you set.Do not use this, only for legacy browser support
(such as IE 7 and earlier).

### Border-box

This is the new way of the internet. Works all the way back to IE8. Setting
box-sizing:border-boxinstead means height and width refers the size of the
content-box plus the padding and border. Thus,setting a fixed width then adding
padding will make the actual content area smaller than the set width.Note that
this often behaves weird when you set height:0 or width:0 and add border.
