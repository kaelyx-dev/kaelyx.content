{{
project 
name=Gump 
desc="Gump is a Python-based commandline utility for automatic common commands such as vsc workspace management and magento commands"
techstack=python
projectlink=https://github.com/kaelyx-dev/gump/
doclink=https://github.com/kaelyx-dev/gump/tree/main/docs
}}

Gump was a project that spawned from doing repetitve jobs such as running 5-8 magento commands in the command line every time I wanted to do something or made a certain change.
This project is a pure-python, modular command runner.

It works via 3 directories
```
/commands
/config
/utils
```

## /commands

When GUMP is invoked from the command line, the first argument is taken as the command: `gump [command] [args]`, Gump then scans the command folder for a python file matching the command provided and then invokes this, passing any further arguments to the command file.

## /config

Commands should be configurable, my machine is not the same as your machine. As such, each command in `/commands` also has its own directory in `/config` for example the command `/commands/helloworld.py` would have the config path `/config/helloworld/config.json` or any json config file in the commands subdirectory.

## /utils

Utils provides a place for common code to live that multiple commands can use, this may include common logging functions or connecting and executing a command in the active WSL Environment etc.
