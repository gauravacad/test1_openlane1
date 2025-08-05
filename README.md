# test1_openlane. The tutorial will let you work the first project for combinational design that is Full adder in Verilog
This is to present the demo on openlane tools.

To work with the openlane type in the terminal

cd OpenLane
make mount

To create the design type the following command in the terminal
./flow.tcl -design <your module design_name> config.tcl

To run openlane interactively
You may run the flow interactively by using the -interactive option:

./flow.tcl -interactive

Then type the follwoing

% 
package require openlane
prep -design -tag -config -init_design_config -overwrite

similar to the command line arguments, design is required and the rest is optional

run_synthesis
run_floorplan
run_placement
run_cts
run_routing
run_magic
The above commands can also be written in a file and passed to flow.tcl: ./flow.tcl -interactive -file

If the design is too small. you try appending these to your configuration file (config.tcl):
set ::env(FP_CORE_UTIL) 5
set ::env(PL_TARGET_DENSITY) 0.5
(low utilization)
Updating OpenLane
If you already have the repo locally, then there is no need to re-clone it. You can run the following:


cd OpenLane/
git checkout master
git pull
make
make test # This is to test that the flow and the pdk were properly updated
configuration variables
