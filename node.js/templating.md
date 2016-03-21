# Templating

Du kommer snabbt märka att du behöver göra ett val av "templating engine". Vi
använder för närvarande Dust.js, men kommer sannolikt att byta till Marko rätt
snart. Eftersom Marko är rätt nytt kan det vara dåligt med dokumentation.
Handlebars är nog det mest populära alternativet. Så kör Marko, Handlebars
eller Dust.

## Dust.js

I realised i forgot to mention which templating system we use, which is Dust
and we use it both server and client side. <http://www.dustjs.com/> is a pretty
good resource to get the basics, but it is far more powerful than the
documentation might suggest. We do not use the dustjs-helpers package available
in the NPM registry, but have rather begun creating our own package at
<https://github.com/thecodebureau/sprinkles>.
