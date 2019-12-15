# my-cli

_This is a fork of the original magic-cli project, rewritten to pure Bash. The original project, while an excellent
concept, was written in Ruby. I wanted a pure Bash solution instead, as I didn't want to force a dependency on Ruby
to use it._

**A foundation for building your own suite of command line tools.**

my-cli exists to make it easy to create a set of tools that work together.  It's not a tool you use as-is; it's here to offer a starting point for your own custom command line tools.

Learn more about the origins of magic-cli in [The Joy of Internal Tools](https://medium.com/@SlackEng/4a1bb5fe905b), a post on the Slack Engineering blog.

## Customization
Rename the `my-cli` script to whatever you want — for example, if you happen to work for example.com, you might rename it to `example`. (If you want to keep any of the example commands that come with it, rename them to have that new name as a prefix — for example, rename `example-update`.)

Now, when you run `example`, it will look for executables in the same directory as itself which have filenames that begin with `example-`. If there's an executable called `example-build`, you could run it by typing `example build`.

Now, when you type `example`, you'll see `example build` in the list of supported subcommands. 

For extra credit, you can add a human-readable description in that list by putting a comment immediately under the `#!` line:

````bash
#!/usr/bin/env bash
# This line will be shown in the list of commands.
````

You can also define any extra parameters that are required for the script with a `# @param` line for each parameter:

````bash
#!/usr/bin/env bash
# This line will be shown in the list of commands.
# @param <command_param> - Longer Description of the Parameter
# @param - If you don’t give a parameter name, a default one will be created for you
````

## Installation
This repository includes a Makefile that will install `my-cli` and all of its subcommands into `/usr/local/bin`:

````bash
$ my-cli --install
````

You can also use it to uninstall `magic-cli`:

````bash
$ my-cli --uninstall
````
