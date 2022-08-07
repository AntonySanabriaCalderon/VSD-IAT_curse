# VSD-IAT_curse
## LAB Day 1

### L2 - Design Preparation Step

1. Go to Desktop/work/tools/openlane_working_dir/openlane
2. Use the “docker” command
3. To open OpenLane in interactive mode type: ./flow.tcl -interactive
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled.png)
    
4. Now we introduce all the packages required typing after the % simbol: package require openlane 0.9
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%201.png)
    
5. Now we need open another terminal and go to the next path: Desktop/work/tools/openlane_working_dir/openlane/designs, in this folder are the design with we go to work.
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%202.png)
    
6. Open picorv32a
7. With the command (less config.tcl) we can check all the configuration information for the design

> For go back to the terminal after use less file press q
> 

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%203.png)

1. Now we are going to configure the design(.tcl)
- Where OpenLane is running, type (prep -design designname), for our case (prep -design picorv32a)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%204.png)

1. To check if all is ok go to: Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a, find a runs file

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%205.png)

---

### L3 - Review files after design prep and run synthesis

1. open “runs” file
2. There should be a file with the date on which the commands were used to create runs.
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%206.png)
    
3. open that file
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%207.png)
    
4. All folders will be empty except "tmp".
5. Go to tmp, let´s open the file "merged.lef”, use: less merged.lef
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%208.png)
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%209.png)
    
6. Open config.tcl. - THis file shows the parameters for simulation.
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2010.png)
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2011.png)
    
7. cmds.log; his file collects all the commands we have type
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2012.png)
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2013.png)
    
8. It´s time to run Synthesis: run_synthesis
    
    This run “biasing synthesis” and “abc”.
    
    Finalmente…
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2014.png)
    

1. When the synthesis is finished one information than we can see as result is the chip area for module.
    
    ![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2015.png)
    

We can see:

Number of cells: 14876

Number of flip-flops : sky130_fd_sc_dfxtp_4 :1613

1. Now

#Flip-flops / #Total cells = X

X, is the Flop Ratio

X * 100 = X%, and X% is the percentage of Flop Ratio 

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2016.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2017.png)

Flop Ratio=

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2018.png)

Percentage of Flop Ratio = 

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2019.png)

1. Back to the “results” folder, here we find the synthetized netlist, the name of this file is “picorv32a.synthesis.v”

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2020.png)

![Untitled](LAB%20Day%201%2001eba55d003146dd83abee58aaca4019/Untitled%2021.png)

1. Let´s see the reports: less yosys_2.stat.rpt

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

## 1. SK1 - Chip Floor planning considerations

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

Seelect an horizontal pin. And type “what” in the tkcon window. The result indicates the layer of the pin. → Metal 3 (como nosotros le indicamos en la config)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2024.png)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2025.png)

Select a vertical pin. And type “what” in the tkcon window. The result indicates the layer of the pin. → Metal 4 (como nosotros le indicamos en la config)

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2026.png)

These are dcapcells.

![Untitled](LAB%20Day%202%20aa7b35b5cb9747048f4ab147cb1527f6/Untitled%2027.png)

These are tapcells. They connects Ground to Substrate, and VDD to —— in CMOS Technology.

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
