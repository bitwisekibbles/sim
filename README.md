# Sim

Sim is a scripting language with an emphasis on extreme simplicity. What makes Sim different than many other scripting languages is that it does not contain any object oriented constructs. Sim is a procedural language with a few structures for directing program flow.

```Batchfile
:: Comment
::

:: Print to STDOUT
print ""

:: Read from Terminal
prompt ""

:: Initialize a Variable
set {var}

:: Initialize and Set a Variable
set {var} = {expression}

:: Expand a Variable's Value
%{variable}%

:: Run an external program
start {program} {args}

:: Clear Screen
clear

:: 

```

## Examples

```Batchfile
:: A Simple Hello World Program

print "Hello World"
```

```Batchfile
:: A Simple Echo Program

set input = prompt "Input: "
echo "Output: %input%"
```

```Batchfile
:: Pause the Command Line

echo "Pausing using Prompt"
prompt "Press any key to continue..."

echo "Pausing using Pause"
pause

echo "Sleep for 10 seconds (10000 milliseconds)"
pause 10000
```

```Batchfile
:: Start Programs

if (UNIX) 
(
start "firefox"
)
if (WINDOWS)
(
start "explorer.exe"
)

```

```
:: Go to labels in program

:loop
print "This text is persistent."
clear
goto loop
```
