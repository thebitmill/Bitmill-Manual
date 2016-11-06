# Recommended Libraries

Not only has the actual JavaScript language (EcmaScript rather), but the amount
of amazing JavaScript libraries thatare being produced are just ridiculous. We
have mentioned the huge and revolutionising node.js, require.js and yeoman.

+ Raphael.js
+ Leflet.js
+ D3.js
+ BackboneJS
+ AngularJS

## Modernizr

Modernizr is probably the easiest JavaScript library to learn. All you have
todo is include it early in your page, and it generates CSS classes that it
addsto the html tag, depending on what technologies the browsers support.

Essentially we no longer have to make browser specific CSS or hacks, we just
testif a certain functionality is available, and respond appropriately.

### Web

One really does not need anything more than Modernizr''s own website...

+ <http://modernizr.com/>	

## jQuery

THIS IS OLD. DO NOT USE JQUERY

Easily one of the most under- and overestimated JavaScript framework on the
web, it is hated, loved and mocked. With CSS3 transitions and animations
essentiallyall animation should be placed in CSS3. Why? Because it is cleaner,
shorter and simpler code thatis much much easier to reuse AND itis also
hardware accelerated. Which normal JavaScript normally is not. However, CSS is
not veryonly good at registering user interactions, so we have recently found
thatCSS3 is used to designate how elements should be animated, while JavaScript
is usedto say when the animations should happen.

Also, CSS Transitions do not work from `height: 0`, to `height: auto`., so right now
we use jQueryto dynamically insert the required height as an inline CSS on the
element. Then add for example .hiddenwith height:0 and use jQuery to toggle the
.hidden class when things need to be animated. This is howthe menu on the left
of these learning pages is made.
