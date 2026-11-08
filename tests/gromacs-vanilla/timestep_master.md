Timestep is passed correctly
----------------------------

PLUMED must receive the timestep from an MD code in order to correctly print the times at which the CV took particular values in COLVAR files. 
To test that the timestep is passed correctly we run a short trajectory and output the time after each step using the following command:

{% raw %}
<div class="plumedInputContainer">
<div class="plumedpreheader">
<div class="headerInfo" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div class="containerBadge">
<div class="headerBadge"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></div>
<div class="headerBadge"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></div>
</div>
</div>
<pre class="plumedlisting">
<b name="working1.datt1" onclick='showPath("working1.dat","working1.datt1","working1.datt1","black")'>t1</b><span style="display:none;" id="working1.datt1">The TIME action with label <b>t1</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">t1</td><td width="5%"><font color="black">scalar</font></td><td>the time since the start of the trajectory</td></tr></table></span>: <span class="plumedtooltip" style="color:green">TIME<span class="right">retrieve the time of the simulation to be used elsewhere <a href="https://www.plumed.org/doc-master/user-doc/html/TIME" style="color:green">More details</a><i></i></span></span>
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working1.datt1">t1</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=colvar 
</pre></div>

 {% endraw %} 

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](basic_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 0.002 | 0.002 | 0.0001 | 0.0 | 


The table below includes some of the results from the calculation.  The columns contain:

1. The timestep that was obtained from the MD code, $x_{md}$.
2. The timestep that was obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta}$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.
