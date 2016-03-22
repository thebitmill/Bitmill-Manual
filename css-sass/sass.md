# Introduktion

SASS is a so called CSS preprocessor. Another one is LESS, but it isgenerally
known to be inferior, so we use SASS. Compass is sort of anadd on to SASS with
loads of helpers and libraries that can be usedto quickly produce amazing CSS.

SASS employs many familiar programming terms, such as variables andreusable
code in the form of functions and mixins. With variablesyou only have to keep
track of a certain colour value in one place,and thus changing it one place
cascades down the whole design.There are also plenty of built in functions like
`darken($blue-color, 20%)`that completely change the way we work with CSS and
the web.

There is an anology on the internet, comparing CSS, SASS & Compass to Captain
America.When you learn just plain CSS you are the skinny little bastard
beforeStark experiments on him. When you discover SASS, you feel like right
afterthe experiement; all big and buff. When you learn Compass, you then
feellike you have gotten your Captain America outfit. And you are just awesome.

## Mixins

Mixins are in many ways like functions, but instead of return values there main
purpose is to automate the output of CSS. Once you have created a CSS structure
that you are particularly pleased with, you can make it into a mixin and call
it simply by writing

```scss
@mixin someMixin($color:red,$width) {
	width: $width;
	> a {
		color: $color;
	}
}
```

You then call it using the `@include` command. Notice how only `$width` HAS to be
supplied. The `$color` parameter will be given a default value ofred, even if it
is not supplied.

```scss
@include someMixin($width:300px);
```

## Books

+ Pragmatic "Guide to Sass" (2011) [link]

## Web

+ SASS: http://sass-lang.com/
