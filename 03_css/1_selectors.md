# Selectors Introduction

Selectors are essentially different ways to select elements in the DOM (the
Document Object Model). They enable you to tell the browser what to do with
what objects, and how they should look. Thus being able to efficiently select
what you want is extremely important, if not detrimental, to your abilities as
a web developer.

As usual, read the applicable chapters in

+ Oreilly "CSS: The Missing Manual" (4th Edition)

Also, these following resources cover selectors in depth (including Pseduo elements and classes)

TODO recheck tese links

+ [W3C Advanced SS3 Selectors](https://www.w3.org/community/webed/wiki/Advanced_CSS_selectors)
+ [Smashing Magizine "Taming Advanced CSS Selectors"](http://coding.smashingmagazine.com/2009/08/17/taming-advanced-css-selectors)
+ [Design Shack "CSS Selectors - Just The Tricky Bits"](http://designshack.net/articles/css/css-selectors-just-the-tricky-bits)

## List of Selectors

+ <http://www.w3schools.com/cssref/css_selectors.asp>

NOTE: The `::before` and `::after` "selectors" listed in that list are not
actually selectors, but will are known as [Pseudo
Elements](./pseudo-elements.md) and can generate content.

NOTE: Pseudo Classes is simply a define a special state of an element, eg
`:hower`, `:first-child`.

## Browser Support

+ <http://caniuse.com/>

## Child Selectors

The child selector differs from the standard descendant selector in that it
stop searching the DOM tree once the children have been checked. Even though
the CSS renderers of todays browsers are blisteringly fast, it is a very easy
way to prevent lots of redundant searching through the DOM. It would be
interesting to make a test and see if it produces notably differences.

Another bonus with using child selectors heavily is you can be much less
careful about repeating class names. For example, the two following selectors
would only affect one h2 tag each, not the others:

```
.cars.list > .item > h2 {
	color: red;
}

.articles > h2 { color: white; }
```

Try to ALWAYS use child selectors, instead of descendants selectors.

## Specificity

A concept that is very useful to understand is the concept of specificity. If
you have several different selectors that affect the same object, the selectors
specificity will prevail. A general rule of thumb, is that the more selectors
you use in a selector, the more specific it is. So, .wrapper .container .item
is more specific than just .container.

However, the different kinds of selectors have different specificity. Just a
tag name has a specificity of 1, a classname 10 and an ID 100. So, for example,
the tag below has a specificity of 22 (2 classes, 2 tagnames):

.wrapper article.main a { color: blue; }

## Try to Only Use Class Names

Understanding how specificity works, and making avid use of child selectors,
one is able to create very intriquite structures. It also becomes very easy
overriding a selector by including an ID, since it has so much higher
specificity than anything else.

As such, I believe ID tags should mainly be used for overriding previous styles
or for easily identifying an element in JavaScript.

Everybody needs to stop using ID''s for CSS selection and use child selectors
anywhere possible.
