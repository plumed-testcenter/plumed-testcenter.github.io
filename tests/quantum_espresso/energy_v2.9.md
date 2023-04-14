Energy is passed correctly
--------------------------

It is common practise to use the potential energy as a collective energy.  Some MD codes thus pass the potential energy to PLUMED. 
To check that this quantity has been passed correctly we can output the passed energy from PLUMED using the following input.  

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.date" onclick='showPath("this_input_should_work.dat","this_input_should_work.date")'>e</b>: <div class="tooltip" style="color:green">ENERGY<div class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></div></div> 
<span style="display:none;" id="this_input_should_work.date">The ENERGY action with label <b>e</b> calculates a scalar quantity</span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.date">e</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=colvar
</pre>
 {% endraw %} 

We can then also output the energy from the MD code and check this matches the value output by PLUMED.  We ran a short trajectory to 
test that the energy is passed correctly.

# Trajectory
Input and output files for the test calculation are available in this [zip archive](energy_v2.9.zip) 


# Results

The table below contains the energies that were output by PLUMED and the energies that were ouptut by the Md code.  If the PLUMED interface is 
working correctly these two sets of numbers should be identical.

| MD code output | PLUMED output | 
|:-------------|:--------------| 
|-18966.529736402397 | -18966.529736 | 
|-18966.70491471821 | -18966.704915 | 
|-18967.091287189345 | -18967.091287 | 
|-18967.67823311154 | -18967.678233 | 
|-18968.451080602114 | -18968.451081 | 
|-18969.392198068334 | -18969.392198 | 
|-18970.482270162465 | -18970.48227 | 
|-18971.701623639743 | -18971.701624 | 
|-18973.031548508297 | -18973.031549 | 
|-18974.45547216064 | -18974.455472 | 
|-18975.959910714773 | -18975.959911 | 
|-18977.53513450709 | -18977.535135 | 
|-18979.175518779724 | -18979.175519 | 
|-18980.879568200227 | -18980.879568 | 
|-18982.64963697443 | -18982.649637 | 
|-18984.491378453822 | -18984.491378 | 
|-18986.41298221817 | -18986.412982 | 
|-18988.42426209191 | -18988.424262 | 
|-18990.535663806255 | -18990.535664 | 
|-18992.757261098217 | -18992.757261 | 
