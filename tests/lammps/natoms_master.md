Number of atoms passed correctly
--------------------------------

PLUMED must receive the number of atoms that are being simulated from the MD code in order to calculate CVs correctly.  
To test this number is passed correctly to PLUMED we run a short trajectory and output the positions of all the atoms 
that are passed to PLUMED using the following command:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<div class="tooltip" style="color:green">DUMPATOMS<div class="right">Dump selected atoms on a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_u_m_p_a_t_o_m_s.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ATOMS<div class="right">the atom indices whose positions you would like to print out<i></i></div></div>=<div class="tooltip">@mdatoms<div class="right">refers to all the MD codes atoms but not PLUMEDs vatoms. <a href="https://www.plumed.org/doc-master/user-doc/html/_group.html">Click here</a> for more information. <i></i></div></div> <div class="tooltip">FILE<div class="right">file on which to output coordinates; extension is automatically detected<i></i></div></div>=plumed.xyz
</pre>
 {% endraw %} 

# Trajectory
Input and output files for the test calculation are available in this [zip archive](basic_master.zip) 


# Results

The table below contains the number of atoms that were in the structure the MD trajectory started from and the number of atomic positions
that were output by the command above.  If the PLUMED interface is working correctly these two numbers should be identical. 


| MD code output | PLUMED output | 
|:-------------|:--------------| 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
|2004 | 2004 | 
