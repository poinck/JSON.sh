# JSON.sh

yo, so it's a json parser written in bash

pipe json to it, and it traverses the json objects and prints out the 
path to the current object (as a JSON array) and then the object, without whitespace.

``` bash
$ json_parse < package.json
["name"]  "JSON.sh"
["version"]  "0.0.0"
["description"]  ""
["homepage"]  "http://github.com/dominictarr/JSON.sh"
["repository","type"]  "git"
["repository","url"]  "https://github.com/dominictarr/JSON.sh.git"
["repository"]  {"type":"git","url":"https://github.com/dominictarr/JSON.sh.git"}
["bin","json_parse"]  "./JSON.sh"
["bin"]  {"json_parse":"./JSON.sh"}
["dependencies"]  {}
#  ... etc
```

a more complex example:

``` bash
curl registry.npmjs.org/express | ./JSON.sh | egrep '\["versions","[^"]*"\]'
... try it and see
```

## Options

-b
> Brief output. Combines 'Leaf only' and 'Prune empty' options.

-l
> Leaf only. Only show leaf nodes, which stops data duplication.

-p
> Prune empty. Exclude fields with empty values.

-s
> Remove escaping of the solidus symbol (stright slash).

-h
> Show help text.

## Cool Links

* [step-/JSON.awk](https://github.com/step-/JSON.awk) JSON.sh ported to awk
* [kristopolous/TickTick](https://github.com/kristopolous/TickTick) Object Oriented BASH
* [archan937/jsonv.sh](https://github.com/archan937/jsonv.sh)

## Installation

install via npm, from AUR on archlinux or from overlay ["koo"](https://github.com/poinck/koo) on Gentoo

* `npm install -g JSON.sh`
* `yaourt -Sy json-sh`
  ([json-sh on aur](https://aur.archlinux.org/packages/json-sh/)
  thanks to [kremlin-](https://github.com/kremlin-))
* `emerge -av JSON-sh`

## License

This software is available under the following licenses:

  * MIT
  * Apache 2
