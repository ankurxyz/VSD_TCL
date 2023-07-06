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

![nocsvfile](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day1/no_csv_file.png)

  - user enters the wrong csv file/ file doesnt exist

![wrongcsvfile](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day1/wrong_csv_file.png)

  - user enters __-help__ as an option

![helpoption](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day1/help_option.png)

 
## DAY-2
__Converting inputs to format[1] and feeding it to yosys for synthesis__

  __- CSV File__

![csv file](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day2/csv_file.png)  

  __- Create Variables__

![creating variables](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day2/creating_variables.png)

  __- Checking if the directories exist or not ( done to prevent the script from breaking )__

![locating files and directories](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day2/locating_files_directories.png)

Displays an error when the required file is not in the needed directory

![filesmissing](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day2/files_missing.png)


