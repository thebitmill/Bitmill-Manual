# Ratings Project

Bygg en episod rating webbsida.

1. Söka efter säsonger från en API, tex
	+ <https://www.themoviedb.org/documentation/api>
	+ <http://sickbeard.com/api/>
	+ <http://www.tvmaze.com/api>
	+ <http://thetvdb.com/wiki/index.php?title=Programmers_API>
	+ <http://docs.trakt.apiary.io/#>
2.  Lägga till säsonger i egen databas
3. Betygsätt (0-100) ett avsnitt
4. Sortera efter rating och dylikt

Jag rekommenderar att du inte utvecklar i Windows miljö. Node och framförallt
NPM beter sig underligt i Windows. Windows i sig beter sig för övrigt underligt
i allmänhet tycker jag.

Använd följande verktyg

+ Node & Npm
+ Express
+ MongoDB & Mongoose
+ jQuery om du vill använda front-end JS istället för att göra allt med HTML
+ Handlebars, Marko eller Dust som templating engine.

