Erusage
=======

Installation
------------

Add to your parsekit.json file new dependency:
```json
{
    "require": {
        "artlebedev/parser3-erusage": "~1.5.0"
    }
}
```

Update your project dependencies:

```shell
$ parsekit update
```


And just add use statement
```parser
@USE
artlebedev/parser3-erusage/Erusage.p
# or
^use[artlebedev/parser3-erusage/Erusage.p]
```


Usage
-----

First call(can be omitted):
```parser
^Erusage:init[$.iLimit(2048)]
```

Others calls:
```parser
^Erusage:compact[]
```

Real `^memory:compact[]` will be called if used more then `$iLimit` KB since
last compact or if `$.bForce(1)` option is specified.

At the end (in `@postprocess` for ex.) you can analyze statistics or call
`^Erusage:log[]` or `^Erusage:print[]`.
