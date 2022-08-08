# VSD-IAT_curse
# LAB Day 1

### L2 - Design Preparation Step

Go to: Desktop/work/tools/openlane_working_dir/openlane

:Use the “docker” command

To open OpenLane in interactive mode type: ./flow.tcl -interactive

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled.png)

Now we introduce all the packages required typing after the % simbol: package require openlane 0.9

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%201.png)

Now we need open another terminal and go to the next path: Desktop/work/tools/openlane_working_dir/openlane/designs, in this folder are the design with we go to work.

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%202.png)

Open picorv32a

With the command (less config.tcl) we can check all the configuration information for the design

> For go back to the terminal after use less file press q
> 

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%203.png)

Now we are going to configure the design(.tcl)

- Where OpenLane is running, type (prep -design designname), for our case (prep -design picorv32a)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%204.png)

To check if all is ok go to: Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a, find a runs file

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%205.png)

---

### L3 - Review files after design prep and run synthesis

open “runs” file

There should be a file with the date on which the commands were used to create runs.

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%206.png)

open that file

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%207.png)

All folders will be empty except "tmp".

Go to tmp, let´s open the file "merged.lef”, use: less merged.lef

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%208.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%209.png)

Open config.tcl. - THis file shows the parameters for simulation.

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2010.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2011.png)

cmds.log; his file collects all the commands we have type

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2012.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2013.png)

It´s time to run Synthesis: run_synthesis

This run “biasing synthesis” and “abc”.

Finally

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2014.png)

When the synthesis is finished one information than we can see as result is the chip area for module.

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2015.png)

We can see:

Number of cells: 14876

Number of flip-flops : sky130_fd_sc_dfxtp_4 :1613

Now

#Flip-flops / #Total cells = X

X, is the Flop Ratio

X * 100 = X%, and X% is the percentage of Flop Ratio 

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2016.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2017.png)

Flop Ratio=

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2018.png)

Percentage of Flop Ratio = 

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2019.png)

Back to the “results” folder, here we find the synthetized netlist, the name of this file is “picorv32a.synthesis.v”

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2020.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2021.png)

Let´s see the reports: less yosys_2.stat.rpt

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2022.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2023.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2024.png)

- less yosys_2-opensta.timing.rpt

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2025.png)

- less opensta.rpt
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2026.png)
    
- less opensta_main.timing.rpt
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2027.png)






# LAB Day 2

## SK1 - Chip Floor planning considerations

### L6 - Steps to run floorplan using OpenLANE

The next step is the floorplaning, first go to: Desktop/work/tools/openlane_working_dir/openlane/configuration

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled.png)

Open README file: less README.md

Inside are the variables for syntesis and Floorplaning

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%201.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%202.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%203.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%204.png)

Let´s open: less floorplan.tcl

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%205.png)

In another terminal open config.tcl file, is located in: Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%206.png)

In terminal with Openlane and the synthesis type: run_floorplan

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%207.png)

---

### L7 - Review floorplan files and steps to view floorplan

To analize the results type: Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs

We need see the latest file, open it using: less 4-ioPlacer.log

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%208.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%209.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2010.png)

open config.tcl → This is the configuration that is taken by the flow

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2011.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2012.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2013.png)

Open file … less sky130A_sky130_fd_sc_hd_config.tcl

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2014.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2015.png)

How floorplan looks?

cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/fecha/results/floorplan 

ls -ltr

lless picorv32a.floorplan.def → Open “.def” file

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2016.png)

Here you can see the area of your complete die. (a b) (c d)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2017.png)

area: (660685/1000)[um]*(671405/1000)[um]= 443.587[nm] 

Let´s see the floorplaning

> magic -T /home/**USER**/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
> 

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2018.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2019.png)

---

## L8 - Review floorplan layout in Magic

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2020.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2021.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2022.png)

To select a certain block in layout, move the mouse over it and press S.

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2023.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2024.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2025.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2026.png)

These are dcapcells.

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2027.png)

These are tapcells. They connects Ground to Substrate, and VDD to in CMOS Technology.

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2028.png)

At bottom left corner, there are std cells. Floorplan is not focused on them.

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2029.png)

To quit Magic… File - Quit - Yes

## SK2 - Library Binding and Placement

### SKY_L5 - Congestion aware placement using RePlAce

Placement in OpenLane occurs in two stages:

1. Global Placement 
2. Detail Placement

In the Floorplanning window type: run_placement

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2030.png)

---

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2031.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2032.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2033.png)

---

Let´s see it in magic

Go to: Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/fecha/results/placement

Type: magic -T /home/**USER**/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2034.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2035.png)

Magic opens and you could see the placement of cells.

Zoom in to see the cells.

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2036.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2037.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2038.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2039.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2040.png)




# LAB Day 3

## SK1

### L5 - Lab steps to git clone vsdstdcelldesign

LET´S COPY THE INVERTER

Go to the next path and type the next command to get the git:

- cd Desktop/work/tools/openlane_working_dir/openlane/
- git clone https://github.com/nickson-jose/vsdstdcelldesign.git
- ls -ltr
- cd vsdstdcelldesig
- ls -ltr

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled.png)

We will see these files

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%201.png)

But, we don’t have the tech file in this directory, so we need to copy it.

The tech file for Magic is inside the next folder:

- cd Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/

The tech file is: “sky130A.tech”

For copy the file type:

cp sky130A.tech /home/USER/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesig/

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%202.png)

Now, if we go to the before folder we will see the “sky130A.tech” file.

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%203.png)

Let´s see the inverter in Magic:

- cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
- magic -T sky130A.tech sky130_inv.mag &

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%204.png)

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%205.png)

---

## SK2

### L9 - Lab steps to create std cell layout and extract spice netlist

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%206.png)

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%207.png)

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%208.png)

**Extract to SPICE…**

In terminal **tkcon**:

pwd to see the path

extract all for extrac

The file is… sky130_inv.ext

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%209.png)

In a terminal we go to the path:

- cd /Desktop/work/tools/openlane_working_dir/openlane/vsdstdcell/design

There will be the file sky130_inv.ext

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%2010.png)

Go back to ****tckon terminal and type the next to extract all the parasitic capacitances:

- ext2spice cthresh 0 rthresh 0
- ext2spice

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%2011.png)

Now go to:  

- cd /Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign

There will be the file sky130_inv.spice

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%2012.png)

To see the spice:

- vim sky130_inv.spice

---

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%2013.png)

## SK3

### L1 - Lab steps to create final SPICE deck using Sky130 tech

Go to and open magic:

- cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesig
- magic -T sky130A.tech sky130_inv.mag &

To see the dimensions of the minimum box size type in **tkcon**: box

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%2014.png)

In another terminal go to:

- cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesig/libs/

It should be contain the next 2 files… “pshort.lib” and “nshort.lib”

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%2015.png)

Now we Change multiple parameters in vim file…

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%2016.png)

To run simulation with ngspice go to:

- /openlane/vsdstdcelldesignngspice
- sky130_inv.spice

---

### L2 - Lab steps to characterize inverter using sky130 model files

In ngspice:

- plot y vs time a

![Untitled](LAB%20Day%203%209bc306e433444a808da78037338b58e4/Untitled%2017.png)



# LAB Day 4

---

# From SK1

## L1 - Lab steps to convert grid info to track info

Open sky130_inv.mag

magic -T sky130A.tech sky130_inv.mag &

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled.png)

Go to the next path:

- cd Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd/
- less tracks.info

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%201.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%202.png)

Grid in Magic: 

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%203.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%204.png)

---

## L2 - Lab steps to convert magic layout to std cell LEF

Now, export LEF file using the tkcon terminal…

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%205.png)

In a terminal go to: cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign

There is the LEF file, open it.

- magic -T sky130A.tech sky130_vsdinv.mag &

In this path we can se the file saved: 

cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesig

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%206.png)

type the next command: magic -T sky130A.tech sky130_vsdinv.mag &

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%207.png)

 Go to tkcon terminal and type: lef write

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%208.png)

Now in the terminal type the next command: less sky130_vsdinv.lef

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%209.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2010.png)

---

## L3 - Introduction to timing libs and steps to include new cell in synthesis

Open another terminal, and type:

cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/

Copy de .lef file of the inverter to the next path: /home/USER/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

The command is this:

cp sky130_vsdinv.lef /home/USER/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2011.png)

Go to the path and see the new file copied.

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2012.png)

¡¡¡We need to configure the config.tcl file!!!

open the file with the next command: vim config.tcl

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2013.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2014.png)

Now we need Launch OpenLane

- cd Desktop/work/tools/openlane_working_dir/openlane/
- docker
- ./flow.tcl -interactive
- package require openlane 0.9
- prep -design picorv32a -tag 05-08_21-15 -overwrite
- set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
- add_lefs -src $lefs
- run_synthesis

In the run_cts I have an error, i try to put the next commands after run synthesis to solve it

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2015.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2016.png)

An error, no use LIB_MIN, use LIB_FASTEST

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2017.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2018.png)

Now everything is okey :), let´s continue

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2019.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2020.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2021.png)

---

## L4 - Lab steps to configure synthesis settings to fix slack and include vsdinv

Go to the next path in another terminal:

cd Desktop/work/tools/openlane_working_dir/openlane/configuration
Open README file: less README.md

You should see “SYNTH_STRATEGY” for synthesis.

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2022.png)

**FIXING SLACK VIOLATIONS:**

In the terminal in which we launched OpenLane:

- echo $::env(SYNTH_STRATEGY)
- set ::env(SYNTH_STRATEGY) 1
- echo $::env(SYNTH_BUFFERING)
- echo $::env(SYNTH_SIZING)
- set ::env(SYNTH_SIZING) 1
- echo $::env(SYNTH_DRIVING_CELL)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2023.png)

run_synthesis

The run file already exist so i need use the mv command to rename the file and avoid problems

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2024.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2025.png)

let´s do the synthesis

got an error

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2026.png)

the command to solve is: 

set ::env(SYNTH_STRATEGY) “DELAY 1”

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2027.png)

Now rerun the synthesis

run_synthesis

Now all work´s

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2028.png)

Now…Floorplan & Placement:

- init_floorplan
    
    ![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2029.png)
    

- place_io

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2030.png)

- global_placement_or

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2031.png)

- detailed_placement

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2032.png)

- tap_decap_or

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2033.png)

- detailed_placement

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2034.png)

Let´s see the new placement

Go to the path:

cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/FECHA/results/placement/

Open magic

magic -T /home/gchts2210/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2035.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2036.png)

Let´s find our inverter cell 

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2037.png)

# From SK2

## L3 - Lab steps to configure OpenSTA for post-synth timing analysis

Go to: 

- cd Desktop/work/tools/openlane_working_dir/openlane/
- vim sta.conf
- 

---

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2038.png)

The file is empty, you need put the next code line:

set_cmd_units -time ns -capacitance pF -current mA -voltage V -resistance kOhm -distance um
read_liberty -max /home/gchtd2210/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib
read_liberty -min /home/gchtd2210/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib
read_verilog /home/gchtd2210/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/05-08_21-15/results/synthesis/picorv32a.synthesis.v
link_design picorv32a
read_sdc /home/gchtd2210/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/my_base.sdc
report_checks -path_delay min_max -fields {slew trans net cap input_pin}
report_tns
report_wns

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2039.png)

Go to

cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2040.png)

less my_base.sdc

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2041.png)

vim my_base.sdc

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2042.png)

We should modify “mybase.sdc” file as it’s shown below:

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2043.png)

In a new terminal, we could type:

cd Desktop/work/tools/openlane_working_dir/openlane/

sta sta.conf

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2044.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2045.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2046.png)

After placement  type this command in the openlane window: run_cts

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2047.png)

After type the command have the same error

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2048.png)

Now have another error, show something with an floorplan file, the other error is with placement file

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2049.png)

![Untitled](LAB%20Day%204%2015b742d48402428fac4236e8c097df95/Untitled%2050.png)
