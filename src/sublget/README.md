# sublget - Prints the title of the currently open sublime window 

USAGE
-----

`sublget` uses `wmctrl` to get the title of the window with
the class name **Sublime_text**. The title looks different
depending on the status of the file, if Sublime is
registered and if a project is open. Below are the different
title variations:  

``` text
# FILE (PROJECT) - Sublime Text
~/git/lab/budlime/scripts/tits/tits.sh (budlime) - Sublime Text

# FILE DIRTY (PROJECT) - Sublime Text
~/git/lab/budlime/scripts/tits/tits.sh • (budlime) - Sublime Text

# FILE - Sublime Text
~/git/lab/budlime/scripts/tits/tits.sh - Sublime Text

# FILE DIRTY - Sublime Text
~/git/lab/budlime/scripts/tits/tits.sh • - Sublime Text
```


If `sublget` is executed without any arguments, the
filename is printed.

EXAMPLES
--------


Goto the same directory as the currently open file:  
`$ cd "$(sublget -d)"`  

`$ alias cds='cd "$(sublget -d)"'`  


OPTIONS
-------

```text
sublget [--follow|-o] [--long|-l] [--print|-r OUTPUT]
sublget --class|-c CLASS  [--follow|-o] [--long|-l] [--print|-r OUTPUT]
sublget --instance|-i INSTANCE [--follow|-o] [--long|-l] [--print|-r OUTPUT] 
sublget --help|-h
sublget --version|-v
```


`--follow`|`-o`  
Will print the source of file/directory if it is symlinked.

`--long`|`-l`  
Will replace `~` with expanded `$HOME` of file.

`--print`|`-r` OUTPUT  
*OUTPUT* can be one or more of the following  characters:  

|character | print
|:---------|:-----
|`f`       | File  
|`d`       | Directory  
|`p`       | Project  
|`s`       | Status  
|`n`       | Window ID  
|`w`       | workspace  



`--class`|`-c` CLASS  
Sets `SUBLIME_TITS_CRIT` to c and `SUBLIME_TITS_SRCH` to
*CLASS*

`--instance`|`-i` INSTANCE  
Sets `SUBLIME_TITS_CRIT` to i and `SUBLIME_TITS_SRCH` to
*INSTANCE*

`--help`|`-h`  
Show help and exit.

`--version`|`-v`  
Show version and exit



