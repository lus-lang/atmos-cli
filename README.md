# cli

Parses command line arguments into commands, options, and arguments, in the manner of commander.

```lus nocheck
local cli = require("https://atmosp.here/2.0/cli.lus")

local program = cli.program("todo", "1.0.0")
program:command("add <title>")
    :option("-p, --priority <n>", "priority", { type = "integer", default = 3 })
    :action(function(args, options)
        print(args.title, options.priority)
    end)

program:run(arg)
```

The package requires Lus 2.0. It declares no permissions. It calls no `pledge` of its own, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `cli.lus`. Run `lus doc cli.lus` to print it.
