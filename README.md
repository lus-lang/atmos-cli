# cli

`cli` parses command line arguments into commands, options, and arguments, with an API modeled on commander, the command line library for Node.js.

The following example defines a to-do list tool whose `add` command takes a title and an integer priority.

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

The package requires Lus 2.0 and declares no permissions. It never calls `pledge`, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `cli.lus`, which `lus doc cli.lus` prints.
