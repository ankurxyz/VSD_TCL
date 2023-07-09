# TCL Workshop: From Introduction to Advanced Scripting
--------------------------------------------------------------------------------------------------------
_Author: Ankur Sharma_

_Acknowledgements: TCL Workshop by [Mr. Kunal Ghosh](https://github.com/kunalg123) , [VLSI System Design](https://www.vlsisystemdesign.com/)_

## Introduction
TCL is a dynamic scripting language that is used for scripting, automation and rapid prototyping tasks. In TCL all data, commands and even programming constructs are represented as strings. This approach provides a high degree of flexibility and allows for powerful string manipulation capabilities.

One of the core features of TCL is it’s command centric nature. TCL commands are used to perform  operations and manipulate data. The language provides a set of built-in commands for common tasks such as file handling, string manipulation, control flow and mathematical operations.

Overall, TCL is valued for it’s simplicity, flexibility and ease of integration making it a versatile scripting language for a range of applications and domains.

## DAY-1

__Creating a TCL Script(vsdsynth) and passing .csv file from UNIX shell(Bash) to TCL script__

To check the default shell installed in your linux system use command
'''
echo $SHELL
'''
There can be multiple shell installed on the system but at any one point in time only one shell can interact between the application and the OS.

The below statement in TCL script is also called as 'shebang' which is written at the beginning of the TCL script. It tells the OS about the interpreter that should be used to execute the script.
Since in this case TCL shell is used to execute the script so the path to TCL shell program is being provided.

```
#!/bin/tcsh -f  
```
_ Making Machines do some Art work!_

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

Here our TCL script takes one argument as .csv file. Now there can be two cases under which the script will not work

Case1: User doesn't give any argument as a csv file to the TCL script.

![nocsvfile](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day1/no_csv_file.png)

Case2: User gives csv file as an argument but a wrong one or the path to csv file is incorrect. 

![wrongcsvfile](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day1/wrong_csv_file.png)

In such cases the user can exercise the -help option for this particualr script to pass correct argument to the script. 

![helpoption](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day1/help_option.png)

 
## DAY-2
__Extracting data from openMSP430_design_details.csv file__

Here is how the csv file looks like:

![csv file](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day2/csv_file.png)  

To operate on this data contained in csv file, we need to create variables/pointers in our TCL script that can point to this information contained in csv file. A good way is to use a 2-D array in the TCL script for mapping data contained in csv file. 
 
![creating variables](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day2/creating_variables.png)

Now there maybe cases when the path given to the files required for generating final results is incorrect or the files are missing in the given directory. In such case the script must catch the error and print the error on console as shown below

![filesmissing](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day2/files_missing.png)

Hence by identifying such errors one can give correct path to files and continue with further execution of the script

![locating files and directories](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day2/locating_files_directories.png)


## DAY-3
__Mapping openMSP430_design_constraints.csv file to format[1] compatible with Yosys(open source EDA tool) for Synthesis__

SDC is a widely used industry standard by which constraints are defined for a digital design. Now let's extract clock information from the csv file, process that information for creating clock SDC constraints. Then add those clock SDC constraints to the script and run it. 

![clock constraints](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/writing_clk_constraints.png) 

Here is how the clock SDC constraints look like

![clock constraints 2](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/clk_sdc_constraints.png)

Next we can do the same thing for Input signals as well. The only difference in processing of input signals is that the input signal can be a bus or just a 1 bit signal in the netlist directory of *.v files. The SDC constraints of a bus signal from single bit signal are differentiated by asterisk(*).   
So all the input signals from openMSP430_design_constraints.csv file need to be looked into the netlist directory of *.v files to check whether the signal is a input vector of length 1 or greater than 1.

![Input constraints1](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/working_on_input_constraints.png)

Here is a print of some formatting done of the input signals that are retrieved from *.v files in the Netlist directory.

![INput constraints 2](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/formatting%20data%20for%20IO%20Constraints.png)

If the input signal grepped from *.v file with ; as the delimiter and in subsequent processing " " as the delimiter we come to know that if count i.e. length of list is 3 then the it's a bus else it's a 1 bit signal.

![INput constraints 3](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/differentiating%20buses%20from%20one%20bit%20signals.png)  

To map Output signal constraints to SDC we need to follow the same steps as we did for input constraints. 

![Output constraints 1](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/working%20on%20output%20constraints.png)

Here is a snapshot of output and load SDC constraints. Load is used to map the capacitance present at the output.  

![Output Constraints 2](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%203/output_constraints.png)

## DAY-4
__- Feeding RTL Netlist and standard cell library to Yosys EDA tool for Synthesis__

Before feeding RTL netlist to EDA tool for synthesis, it's best to validate the RTL netlist. So we do a hierarchy check. We start first by retrieving the netlist in a variable called as data as shown below 

![RTL Netlist](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/1_RTL%20Netlist%20for%20Yosys%20tool.png) 

For each RTL Netlist we do a syntax check by appending the command(specific to Yosys) corresponding to that operation in the openMSP430.hier.ys file and at the end of file we append the command corresponding to hierarchy check in the openMSP430.hier.ys file.

![Reading RTL Netlist](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/2_Reading%20RTL%20Netlist.png)

We give this openMSP430.hier.ys file as an input to Yosys tool to check for syntax/hierarchy and report back if there is any error. If there is an error during the execution err flag is set to 1. 

![Checking hierarchy using flag](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/3_checking_hierarchy%20using%20flag.png)

On checking the openMSP430.hierarchy_check.log it was clear tha it's a syntax error.

![Syntax Error](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/4_syntax_error.png)

So we resolved it and now the err flag is set to 0.

![Resolving syntax error](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/5_resolving%20syntax%20error.png)  

At another time i had this error where the hierarchy check test failed!

![Hierarchy check test failed](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/6_hierarchy_check_test_failed.png)

So again looked into the log file and found that it's a module instantiation error.

![Checking log file](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/7_checking_log_file.png)

There was no module defined by the name of omsp_clock_module_1. Rather the module that is defined was omsp_clock_module.

![Name Error](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/8_Name_error.png)  

So i changed the parent module name to omsp_clock_module.

![Correcting name error](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/9_correcting_error.png)

And then the Hierarchy check also Passed! :)

![Hierarchy check test passed](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%204/10_hierarchy_check_test_passed.png)

## DAY-5
__- Converting Yosys tool's synthesized gate level output netlist to a format compatible with Opentimer(Open Source EDA Tool) for generating the Timing Report__

We feed the standard cell library and RTL Netlist referenced through the openMSP430.ys file to Yosys EDA tool for creating gate level synthesized netlist in the file openMSP430.synth.v

![Synthesizing Netlist](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/1_Synthesizing_netlist.png) 

Now we need to format the openMSP430.synth.v file to a format that is compatible with the opentimer EDA tool. So from the openMSP430.synth.v we remove all the lines containing an asterisk(*) symbol and replace backslash(\) symbol with a null character("") to generate openMSP430.final.synth.v file 

![Formatting synthesized netlist for opentimer](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/2_formatting_synthesized_netlist_for_opentimer.png)

Here is an example of how the formatting is done for openMSP430.synth.v file by removing the asterisk symbol from it 

![formatting - removing asterisk](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/3_formatting_removing_asterisk.png)

The below snapshot shows how the formatting is done for openMSP430.synth.v file by replacing "\" character with a "" character

![formatting replacing backslash with null](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/4_formatting_replacing_back_slash_with_null.png)

Proc is just like a function. We can define it in a file and then just source that proc to our main script and call that proc just like any other function by passing the required options and arguments. Here is an example of one of the proc used to define the number of threads.  

![Multi CPU Usage Proc](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/5_multi_cpu_usage_proc.png)  

We have used 5 procs in our script:
reopenStdout.proc for redirecting the output generated by puts command from console to .conf file
set_num_threads.proc for setting number of threads/cores used to execute the further script
read_lib.proc for reading the standard cell libraries
read_verilog.proc for reading the final synthesized RTL Netlist in openMSP43.final.synth.v file
read_sdc.proc for reading the sdc constraints
 
Below snapshot shows the execution of procs.
![Executing Procs](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/6_executing_procs.png)

The output commands generated on execution of these procs are added into the openMSP430.conf file. These commands are compatible with the opentimer EDA tool for timing analysis. 

![Proc Output in conf file](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/7_proc_output_in_conf_file.png)

Here is an example of how the SDC constraints need to be formatted for opentimer inference. This is done by making use of the read_sdc.proc. Using this proc we read the sdc file, remove the square brackets and define clock by it's name, period and % duty cycle only and then dump the final result as a command compatible with opentimer into openMSP430.timing file.   

![Formatting create clock constraints for opentimer](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/8_formatting_create_clock_constraints_for_opentimer.png) 

Below image shows the formatting done for clock latency constraints 

![Formatting clock latency constraints](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/9_formatting_clock_latency_constraints.png)

Here we do the formatting for clock transition constraints

![Formatting clock transition constraints](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/10_formatting_clock_transition_constraints.png)

Then input delay constraints.....

![Formatting input delay constraints](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/11_formatting_input_delay_constraints.png)

Not to forget the formatting for output delay and load constraints...

![Formatting output delay and load constraints](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/12_formatting_output_delay_load_constraints.png)
  
And finally the formatting need to be done for bus signals.

![Formatting constraints with bus signals](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/13_formatting_bussed_io_constraints.png) 

We then enable the prelayout timing variable to not take into account wire load parasitics as the routing has not been done. So essentially the load parasitic value is set to zero. 

![Opentimer tool specific commands added](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/14_timing_info_added.png)

This is how the final openMSP430.conf file looks like. Here the .spef file contain design specification.
And then we timing related commands appended to openMSP430.conf file. These commands are specific to opentimer EDA tool only. 

![Final .conf file](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/15_final_conf_file.png)

We give the openMSP430.conf file and openMSP430.timing file as input to opentimer EDA tool and get the timing results as shown below.
Runtime is calculated by using the 'time' command of opentimer. 
Instance count is calculated by grepping the string "Num of gates" from the file openMSP430.results
WNS setup is calculated by grepping the first occurence of string "Setup" from the file openMSP430.results and retrieving the slack value corresponding that line.
FEP Setup is calculated by counting the number of occurence of string "Setup" in the file openMSP430.results 
The method used for calculating setup violations is the same that is used for calculating hold violations and output violations as well. Only the Keyword Hold need to be used in place of Setup for calculating Hold violations and keyword RAT need to be used in place of Setup for calculating output violations. 

![Opentimer Output](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/16_opentimer_output.png)

Report formatting is an Art. Don't underestimate that!

![Formatting Timing Report](https://github.com/ankurxyz/VSD_TCL/blob/main/images/day%205/17_timing_report_formatting.png)  

