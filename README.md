# TCL Workshop: From Introduction to Advanced Scripting
--------------------------------------------------------------------------------------------------------
_Author: Ankur Sharma_

_Acknowledgements: TCL Workshop by [Mr. Kunal Ghosh](https://github.com/kunalg123) , [VLSI System Design](https://www.vlsisystemdesign.com/)_

## Introduction
TCL is a dynamic scripting language that is used for scripting, automation and rapid prototyping tasks. In TCL all data, commands and even programming constructs are represented as strings. This approach provides a high degree of flexibility and allows for powerful string manipulation capabilities.

One of the core features of TCL is it’s command centric nature. TCL commands are used to perform  operations and manipulate data. The language provides a set of built-in commands for common tasks such as file handling, string manipulation, control flow and mathematical operations.

Overall, TCL is valued for it’s simplicity, flexibility and ease of integration making it a versatile scripting language for a range of applications and domains.
links for easy navigation:

## DAY-1

__Create Command (VLSI) and pass csv file from UNIX shell to Tcl script__

The command was created with the following algorithm:
1) The below statement in TCL script is also called as 'shebang' which is written at the beginning of the TCL script. It tells the system about the interpreter that should be used to execute the script.

```
#!/bin/tcsh -f  
```

2) Creating the logo

```
echo "      *******************      ****************       ******             "
echo "      *******************      ****************       ******             "
echo "             *****             ****        ****       ******             "
echo "             *****             ****                   ******             "
echo "             *****             ****                   ******             "
echo "             *****             ****        ****       ******             "
echo "             *****             ****************       ***************    "
echo "             *****             ****************       ***************    "
```

3) Verifying three general scenarios for a user POV
  - user doesnt enter the csv file

![nocsvfile.png](https://drive.google.com/file/d/1FBsPIF43I77XKfuad8YhMnA-MUAKcL5I/view?usp=sharing)


  - user enters the wrong csv file/ file doesnt exist


![wrongcsvfile](https://drive.google.com/file/d/11wNHSQknUHQn9acU9cL2CpNKawDMXBE4/view?usp=sharing)

  - user enters __-help__ as an option

![helpoption](https://drive.google.com/file/d/1cPLggRbV-TrG_RRvHpPe0Z9DwkpTq-a6/view?usp=sharing)

 

