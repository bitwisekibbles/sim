# Sim Rationale

## The Sim Environment

The sim environment is split into two distinct *modes*. These are `dynamic` and `feed`. When you write a sim program, `feed` is the default mode. Feed mode is essentially just a REPL (read-evaluate-print-loop) like any normal terminal or batch program. `dynamic` mode is essentially just a curses mode made to be cross-platform and much easier to work with. 

#### Running a Sim Program

A sim program can be `interpreted` or it can be `compiled`. How the compiler, `simc`, works is by translating the sim code into compatable C code and includes the neccesary boilerplate code for getting the program to act as described. It then hands over the real compilation to a local compiler such as `gcc` or `clang`. If compilation returns an error stating that no compiler can be found, you must specify it using the `-c {path/to/compiler}` command. If you would like to take a look at the generated C code yourself perhaps to optimize it or critisize `simc`'s compiling abilities, pass the `-r` or `--raw` command to `simc`

## Variables

#### Strings

Strings hold a variety of letters. Strings are encased in `""` and can span multiple lines if needed.

#### Numbers
Numbers are any expression equivalent to a number. For instance, `1`, `3.14`, `6.02e23`, and `2+2i` are all numbers.

## Global Functions

#### Comments
```Batchfile
:: {comment}
:: This is a Comment
```

#### `pause`
```Batchfile
pause {optional:time in ms}
pause
pause 10000
```

#### `mode`
```Batchfile
mode {mode}
mode dynamic
```

#### `start`
```
start {command} {arguments}
start "firefox"
start "iexplore.exe" "IECOMPAT=0"
```

#### `eval`
```Batchfile
eval {expression}
eval (4^3 * (22/7))
```

#### `exit`
```Batchfile
exit {optional:return text}
exit
exit "...and nothing of value was lost."
```

## Feed Mode Functions

```print
print {string}
print "Hello Feed Mode"
```

## Dynamic Mode Functions

## Control Flow Structures

#### `if`
```Batchfile
if ({expression}) ({code})
if (1 is 1) ( print "TRUE" )
```

#### `while`
```Batchfile
while ( {condition} ) ( {expression} )
while ( 1 is 1 ) ( print "INFLOOP" )
```

#### `do while`
```Batchfile
do ( {expression} ) while ( {condition} )
do ( print "ONCE" ) while ( 1 is 0 )
```

#### `loop`
```Batchfile
loop ( {expression} )
loop ( print "INFLOOP" )
loop ( if (1 is 1) (break) )
```

#### Labels and `goto`
```
:{name}
:example

goto {label}
goto example
```

## Macros


#### Operating System Identifiers

```Batchfile
:: Cygwin
WINDOWS
:: Mac OSX
MAC
:: iOS
IOS
:: Linux
LINUX
:: Android
ANDROID
:: Solaris
SOLARIS
:: Berkeley Software Distribution
BSD
```
