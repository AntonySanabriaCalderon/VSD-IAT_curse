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
