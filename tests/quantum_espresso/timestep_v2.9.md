Timestep is passed correctly
----------------------------

PLUMED must receive the timestep from an MD code in order to correctly print the times at which the CV took particular values in COLVAR files. 
To test that the timestep is passed correctly we run a short trajectory and output the time after each sstep using the following command:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.datt1" onclick='showPath("this_input_should_work.dat","this_input_should_work.datt1")'>t1</b>: <div class="tooltip" style="color:green">TIME<div class="right">retrieve the time of the simulation to be used elsewhere <a href="https://www.plumed.org/doc-master/user-doc/html/_t_i_m_e.html" style="color:green">More details</a><i></i></div></div>
<span style="display:none;" id="this_input_should_work.datt1">The TIME action with label <b>t1</b> calculates a scalar quantity</span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.datt1">t1</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=colvar 
</pre>
 {% endraw %} 

# Trajectory
Input and output files for the test calculation are available in this [zip archive](basic_v2.9.zip) 


# Results

The table below contains times at which each trajectory step should have ended based on the input timestep and the times 
that were output by the command above.  If the PLUMED interface is working correctly these two sets of numbers should be identical.

| PLUMED output | MD code output | 
|:-------------|:--------------| 
| 0.0009675600000000001 | 0.000968 | 
