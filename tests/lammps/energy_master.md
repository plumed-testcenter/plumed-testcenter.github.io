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
Input and output files for the test calculation are available in this [zip archive](energy_master.zip) 


# Results

The table below contains the energies that were output by PLUMED and the energies that were ouptut by the Md code.  If the PLUMED interface is 
working correctly these two sets of numbers should be identical.

| MD code output | PLUMED output | 
|:-------------|:--------------| 
|-26662.023624585858 | -26662.023625 | 
|-26699.694316037025 | -26699.694316 | 
|-26795.89324066926 | -26795.893241 | 
|-26925.828047228137 | -26925.828047 | 
|-27057.832624910396 | -27057.832625 | 
|-27170.98837148412 | -27170.988371 | 
|-27259.046918251956 | -27259.046918 | 
|-27323.4575557306 | -27323.457556 | 
|-27365.051310102397 | -27365.05131 | 
|-27382.69906765475 | -27382.699068 | 
|-27380.911054201246 | -27380.911054 | 
|-27370.000776643898 | -27370.000777 | 
|-27360.086697842016 | -27360.086698 | 
|-27352.08230991905 | -27352.08231 | 
|-27338.358833256963 | -27338.358833 | 
|-27314.710333444375 | -27314.710333 | 
|-27289.258721116556 | -27289.258721 | 
|-27275.53297989376 | -27275.53298 | 
|-27274.554116047933 | -27274.554116 | 
|-27277.17294066409 | -27277.172941 | 
