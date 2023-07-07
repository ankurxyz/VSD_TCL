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



## DAY-3
__Converting inputs to format[1] and feeding it to yosys for synthesis__

  __- Working on Clock Constraints__

![clock constraints](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/writing_clk_constraints.png) 

  __- Clock SDC Constraints__

![clock constraints 2](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/clk_sdc_constraints.png)

  __- Working On Input Constraints__

![INput constraints1](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/working_on_input_constraints.png)

  __-Formatting data for Input Constraints__

![INput constraints 2](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/formatting%20data%20for%20IO%20Constraints.png)

  __- Differentiating Buses from single bit signals__

![INput constraints 3](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/differentiating%20buses%20from%20one%20bit%20signals.png)  

  __- Working on Output constraints__

![Output constraints 1](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/working%20on%20output%20constraints.png)

  __- Output Constraints__

![Output Constraints 2](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/output_constraints.png)

## DAY-4
__- Feeding RTL Netlist, SDC's and standard cell library to Yosys EDA tool for synthesis__

  __- RTL Netlist__

![RTL Netlist](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/1_RTL%20Netlist%20for%20Yosys%20tool.png) 

  __- Reading RTL Netlist__

![Reading RTL Netlist](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/2_Reading%20RTL%20Netlist.png)

  __- Checking hierarchy using flag__

![Checking hierarchy using flag](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/3_checking_hierarchy%20using%20flag.png)

  __-syntax error__

![Syntax Error](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/4_syntax_error.png)

  __- Resolving syntax error__

![Resolving syntax error](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/5_resolving%20syntax%20error.png)  

  __- Hierarchy check test failed__

![Hierarchy check test failed](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/6_hierarchy_check_test_failed.png)

  __- Checking log file__

![Checking log file](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/7_checking_log_file.png)

  __- Name Error__

![Name Error](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/8_Name_error.png)  

  __- Correcting name error__

![Correcting name error](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/9_correcting_error.png)

  __- Hierarchy check test passed__

![Hierarchy check test passed](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/10_hierarchy_check_test_passed.png)
