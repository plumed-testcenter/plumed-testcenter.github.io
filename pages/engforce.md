Check force on energy
---------------------

It is common practise to use the potential energy as a collective energy. Some MD codes thus pass the potential energy to PLUMED and
PLUMED can then apply forces on this collective variable.  We test that any forces that PLUMED applies on the potential energy are 
correctly passed back to the MD code by doing the following test.  We first run a short simulation at $T$ K with a timestep of $\tau$ ps.
During the course of this simulation we monitor the potential energy using the following PLUMED input:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.date" onclick='showPath("this_input_should_work.dat","this_input_should_work.date")'>e</b>: <div class="tooltip" style="color:green">ENERGY<div class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></div></div>
<span style="display:none;" id="this_input_should_work.date">The ENERGY action with label <b>e</b> calculates a scalar quantity</span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.date">e</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=energy1
</pre>
 {% endraw %} 

We then run a second simulation (starting from identical conditions) at a temperature of $T\alpha^2$ and with a timestep of $\tau/\alpha$.
The thermostat and barostat relaxation times are similarly divided by $\alpha$.  In the tests that are run on this website we set $\alpha=1.1$.

For this second MD run the following PLUMED input file is used:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.date" onclick='showPath("this_input_should_work.dat","this_input_should_work.date")'>e</b>: <div class="tooltip" style="color:green">ENERGY<div class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></div></div>
<span style="color:blue"># slope is such that </span>
<span style="display:none;" id="this_input_should_work.date">The ENERGY action with label <b>e</b> calculates a scalar quantity</span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.date">e</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=energy2
<span style="color:blue"># slope should be (alpha-1)=0.1</span>
<div class="tooltip" style="color:green">RESTRAINT<div class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/_r_e_s_t_r_a_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">AT<div class="right">the position of the restraint<i></i></div></div>=0.0 <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.date">e</b> <div class="tooltip">SLOPE<div class="right"> specifies that the restraint is linear and what the values of the force constants on each of the variables are<i></i></div></div>=0.1
</pre>
 {% endraw %} 

When forces are passed correctly the time series of the energies from these two calculations should be identical. An NPT version of this calculation 
is performed as well as an NVT calculation if the virial is passed to PLUMED.

# Trajectories

# Results

The table below contains the PLUMED outputs from the two calculations described above.
If the PLUMED interface is working correctly these two sets of numbers should be identical.
