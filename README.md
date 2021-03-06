# EmberScript support for ember-cli
Adds precompilation of EmberScript files and all the basic generation
types to the `ember generate` command.

### Includes
- Generating files in EmberScript with `ember generate`
- Preprocessing EmberScript-files in your app

### Install
```
npm install ember-cli-emberscript --save-dev
```

Should work with ember-cli version `0.0.44` and up (if not let me know).

### How to use
Run `ember help generate` to get a list of available blueprints.
Use them by running `ember g <blueprint> <args>`, for instance `ember g
controller pants type:array`

## EmberScript version
Currently, the multi-compile version of EmberScript is used to allow for multi script languages to co-exide and be compiled separately for a single file. This is to overcome when EmberScript adds certain variables to the top (see [issue #44](https://github.com/ghempton/ember-script/issues/44.)

```json
  "dependencies": {
    ...
    "ember-script": "git://github.com/kristianmandrup/ember-script#0.0.16"
  }
```    

### Script file layout

The basic layout of a file is like this. In thee blueprints, `(ember)` is used as the emberscript indicator, but you might as well use simply `(em)`. See the full list of aliases on [emberscript multicompile](git://github.com/kristianmandrup/ember-script#multicompile).

By convention, the first fragment will now be treated as normal coffeescript and be compiled separately before the emberscript (or whatever) coming after. This allows you to insert the import statements etc.

```coffeescript
`import Ember from 'ember'`

# (ember)

class Post
  # ...

`export default Post`
```

### Status
Experimental, but a step in the right direction ;)

### Roadmap

Let me know what you would like to see...