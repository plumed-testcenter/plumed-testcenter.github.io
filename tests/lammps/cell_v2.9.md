Cell vectors are passed correctly
---------------------------------

PLUMED must receive the cell vectors from the MD code in order to calculate CVs correctly.  
To test these cell vectors are passed correctly to PLUMED we run a short trajectory and output the celll vectors 
that are passed to PLUMED using the following command: 

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.datc" onclick='showPath("this_input_should_work.dat","this_input_should_work.datc")'>c</b>: <div class="tooltip" style="color:green">CELL<div class="right">Calculate the components of the simulation cell <a href="https://www.plumed.org/doc-master/user-doc/html/_c_e_l_l.html" style="color:green">More details</a><i></i></div></div> 
<span style="display:none;" id="this_input_should_work.datc">The CELL action with label <b>c</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">c.ax</td><td>the ax component of the cell matrix</td></tr><tr><td width="5%">c.ay</td><td>the ay component of the cell matrix</td></tr><tr><td width="5%">c.az</td><td>the az component of the cell matrix</td></tr><tr><td width="5%">c.bx</td><td>the bx component of the cell matrix</td></tr><tr><td width="5%">c.by</td><td>the by component of the cell matrix</td></tr><tr><td width="5%">c.bz</td><td>the bz component of the cell matrix</td></tr><tr><td width="5%">c.cx</td><td>the cx component of the cell matrix</td></tr><tr><td width="5%">c.cy</td><td>the cy component of the cell matrix</td></tr><tr><td width="5%">c.cz</td><td>the cz component of the cell matrix</td></tr></table></span></pre>
 {% endraw %} 

# Trajectory
Input and output files for the test calculation are available in this [zip archive](basic_v2.9.zip) 


# Results
Calculations were not sucessful and no data was generated for comparison

The table below contains the cell vectors that were output by the above command and the cell vectors 
that were output by the MD code.  If the PLUMED interface is working correctly these two sets of numbers should be identical.
