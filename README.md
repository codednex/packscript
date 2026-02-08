# PackScript - New Minecraft Coding language

PackScript is a small Programming language that uses a mod or a plugin, to translate PkS to Java.
It is meant to run with a server plugin/client mod that translates everything, to allow people write Plugins and Mods without knowing a bit of Java Programming Language.


PackScript examples and rules:

1. All scripts **MUST** have a header.
Header example
```
#init
modname(Test Mod)
modver(1.0 release)
overridegamefiles(true) ~/ This is a comment. And overridegamefiles is a parameter that tells the script to change game files like textures, languages, and GUI elements into your own.
```
All headers start with `#init`. If the Script doesn't contain a header, the script isn't even going to load.

----------------------------------------------------------------------------------------------

# Marking scripts

After you configured a header, now we need to define the "script start."
Script start is marked with `#script`. Anything after script start is loaded to the game.

----------------------------------------------------------------------------------------------

# Subscripts

Subscript is a block of script condensed into a function that can be called later.
Subscript defining example
```
subscript.define(
    name(example)
    script(
        log.print(Hello World!)
    )
)
```

Subscript calling with `trigger` example
```
trigger.add(
    name(hello)
    subscript(example)
)
run(trigger(hello))
```

----------------------------------------------------------------------------------------------

# Packages

If you want to organise your mod, you can use packages.
You can load pre-made packages on this repository, for example `easylog`.
This is a sample script that loads `easylog`:
```
#init
modname(sample)
modver(1.0 EXAMPLE)
overridegamefiles(false)
packages(easylog)
preload(
    import from(easylog) get(*)
)
```
You can also specify which parts of a package you want to import:
```
#init
modname(sample)
modver(1.0 EXAMPLE)
overridegamefiles(false)
packages(easylog)
preload(
    import from(easylog) get(chatlog, gamelog)
)
```
