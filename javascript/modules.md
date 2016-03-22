# Modules

JavaScript was never really constructed with modularity in mind. Everything is
global solves every problem. That was the philosophy. CommonJS puts an end to
this. Node is completely built around CommonJS modules, and you basically have
to write CommonJS modules for your JavaScript to work with Node.

## CommonJS Modules

CommonJS was never really meant to solve the front-end modularization. Instead,
recent years have seen the growth of Asynchronous Module Defintion (AMD). Most
notably RequireJS use AMD modules to load JavaScript asynchronously and handle
dependencies. However, AMD and RequireJS truly suck. I will explain more
thorougly later.

Enter Browserify.

For CommonJS to work optimally in the browser, they will have to be slightly
different.

## RequireJS

Poo. Real asyncronous poo.

## ES6 Modules

Not yet available in any environment (include Node v0.5.X).
