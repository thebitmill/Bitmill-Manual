# Positioning

Position should NEVER be used to create the basic layout of your page. This
would usuallyentail positioning everything absolutely to your body element.
While this is possible,it is hopelessly archaic and as far from responsive as
one can get.

Instead, position is meant for finetuning, or create graphical effects to
stylecertain parts of your website. Absolute positioning should almost always
be positionedrelative to a floated or in other ways responsive element. This is
discussed in the article"Absolute Position Inside Relative Positioning" below.

If elements overlap their z-index will decide who will be ontop of who.
Z-indexingwith weird relationships (not plain sibling elements) can sometimes
get confusingas children often inherit their parents z-index.

As usual, read the applicable chapters in

+ Oreilly "CSS3: The Missing Manual" (4th Edition)

CSS Tricks also have some good articles on the subject.

+ [CSS Tricks "Positioning"](https://css-tricks.com/almanac/properties/p/position/)
+ [CSS Tricks "Differences Between Different Positionings"](https://css-tricks.com/absolute-relative-fixed-positioining-how-do-they-differ/)
+ [CSS Tricks "Absolute Position inside Relative Positioning"](https://css-tricks.com/absolute-positioning-inside-relative-positioning/)
