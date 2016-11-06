# ES2015 Modules

Not yet native available in any environment (include Node v0.5.X).

# Rollup

Rollup enables you to use ES6 modules for front end code today.

Essentially, just like Browserify or Webpack, it bundles all
your seperate JS modules into a single file. Due to inherent
differences between CommonJS and ES6 modules, methods such as
Tree-Shaking can greatly reduce the final filesize. Due to
the lack of wrapper functions are modules, Rollup bundles are
also several orders of magnitude faster during runtime.
