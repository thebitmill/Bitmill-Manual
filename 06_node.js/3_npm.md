# NPM

Make sure you have read the [JavaScript/Modules](../javascript/modules) section.

NPM is the package manager. It currently works for CommonJS, but ES6 modules will
soon be implemented. Hopefull Node.js 6.

Även om den inte fungerar riktigt lika
vackert som mogna Linux pakethanterare så fungerar den ändå rätt bra.

## Updating a project to latest version of installed packages

When starting a project from a skeleton or framework, copying another project
or updating old apps it is often beneficial and good practice to update all
dependencies to their latest stable versions.  The following command uses NPM
to update a single module without opening package.json:

```
$ npm install {package-name}@* {save flags?}
```

NPM does not have a method for updating all modules automatically, but it can
be done by replacing all version numbers in package.json with \*, and running

```
$ npm update --save
```

Simply change every dependency's version to \*, then run `npm update --save`.

```json
"dependencies": {
  "express": "*",
  "mongoose": "*",
  "lodash": "*",
  "dustjs-linkedin": "*"
}
```

There is well used module that does this automatically called `npm-check-updates`. Once installed globally, run

```
$ ncu
```

to see which updates will be installed. Run it with the -u flag to update your
package.json.

Use RegEx to filter packages:

```
$ npm-check-updates -f '/^(?!node-sass|gulp-sass).*$/'
```

## Python

THIS SECTION MIGHT BE OUTDATED

Almost all Node modules that require Python (most importantly node-gyp, require
version 2.7. If you have version >3 installed, then you either have to tell NPM
everytime using:

```
$ npm install --python=python2.7
```

or set it to be used always:

```
$ npm config set python python2.7
```

This will add `python=python2.7` to your `~/.npmrc`.

Apparently you can also do this as System Environment Variable.

## Managing dependancy versions

Node automatically prepends a caret (^) to the beginning of version numbers in
the package.json file when using the --save option. Before version 0.10.16 or
something it used to prepend a tilde (~) by default. The difference is
following:

"In the simplest terms, the tilde matches the most recent minor version (the
middle number). ~1.2.3 will match all 1.2.x versions but will miss 1.3.0. This
has been the default behavior of ‘—save’ since the start, and you are probably
already comfortable seeing it in your package.json. The caret, on the other
hand, is more relaxed. It will update you to the most recent major version (the
first number). ^1.2.3 will match any 1.x.x release including 1.3.0, but will
hold off on 2.0.0. npm’s semantic versioning parser clarifies the distinction."

+ Source: <http://fredkschott.com/post/2014/02/npm-no-longer-defaults-to-tildes/>

The problem is that many people do not follow the SEMVAR specification and
others release versions without proper testing which break applications. To
override the defaults use the commands below.

To set the default back to tilde:

```
$ npm config set save-prefix='~'
```

To remove auto-prefixing:

```
npm config set save-prefix=''
```

## Links

+ <https://nodesource.com/blog/eleven-npm-tricks-that-will-knock-your-wombat-socks-off/?utm_source=javascriptweekly&utm_medium=email>
