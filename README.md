# Detection of 11 sequence using Moore-FSM
In this project I have tried to build a Finite State Machine (FSM) using Xilinx Vivado 2016.3 . This system is implemented on  Zynq - 7000 development board. Using basic TCL commands and scripting implementation is done. It is a work in progress and will try to add constraints and generate bitstream as well.

FSM - Finite State Machines are basically abstract representation of a sequential logic. No. of inputs, number of states and outputs are finite in number. These sequential circuits are either level-sensitive or edge-sensitive. Sequential elements like flip-flops are used in real-world circuits to implement FSMs. A specified sequence of stages, or algorithm, is required for the implementation operation to be carried out. 

In this project sequence of "01011011101" is provided and corresponding to that the output will be "00001001100"
The derivation of logical equations, state diagram and state table is mentioned in the Moore_machine.PDF. Kindly refer to that for the theoritical explanation of this project.

Kindly note that before executing scripts in the Vivado's TCL window please set the working directory to the path where you have extracted the .zip file. You can change directory by the following command cd C:/<dir_name>/<fsm_machine>/. You can also check your current working directory using pwd command in TCL window

Files in this repository
--------------------------

1. fsm_moore.tcl

(To run this script write ***source fsm_moore.tcl*** )

This script allows us to create a project titled as 'moore_11_detector'. It also defines the Zynq-7000 part no.'xc7z010c1g400-1'.As we are trying to create RTL project using set_property as RTL we can create RTL project. After creating a blank RTL project we have to add certain verilog files(moore_11.v) and testbench.v(moore_fsm_tb.v) for simulation purposes. Using the import_files TCL command we can import verilog file present in the directory. add_files performs similar task but it has other functionality as compared to import_files command. Using add_files we can add testbench file to the simulation sources. By default the files are added or imported as a design source only. To overcome that by setting -fileset as sim_1 we can add the file as a simulation source.

2. simulation.tcl

(To run this script write ***source simulation.tcl*** )

Simulation basically allows us to monitor the changes w.r.t the external or internal stimuli offered to it. In our case I have already provided the stimuli in the form of '01011011101'. As we are trying to detect a '11' sequence the output will be '1' for the next clock cycle after the occurence of two ones. 
launch_simulation starts the simulation process and you can monitor the output. This script also synthesizes the design i.e. it transforms RTL specified design into gate-level representation. launch_runs will create a <folder_name> and -jobs specifies number of files provided for synthesis. By default its value is set to 1. wait_on_run blocks execution of further TCL commands until the specified run completes. 

3.Moore_machine.pdf

It has the derivation of the state diagram, equations and final schematic of sequential diagram.



As I mentioned earlier it is a project in progress, I will try to add all the files as soon as possible also it would be great if you will provide your valuable suggestions or feedbacks for the same. If you feel any issues while executing the scripts please feel free to post comments. I will be happy to help
Thankyou !!
