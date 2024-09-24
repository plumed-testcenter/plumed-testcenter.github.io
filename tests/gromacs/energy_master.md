Energy is passed correctly
--------------------------

It is common practise to use the potential energy as a collective energy.  Some MD codes thus pass the potential energy to PLUMED. 
To check that this quantity has been passed correctly we can output the passed energy from PLUMED using the following input.  

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.9-passing-green.svg" alt="tested on2.9" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the value calculated by this action</td></tr></table></span>: <div class="tooltip" style="color:green">ENERGY<div class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></div></div> 
<div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="working1.date">e</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=colvar
</pre>
 {% endraw %} 

We can then also output the energy from the MD code and check this matches the value output by PLUMED.  We run a short trajectory to test that the energy is passed correctly.

# Trajectory
Input and output files for the test calculation are available in this [zip archive](energy_master.zip)


# Results

The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18174.685547 | -18174.685547 | 0.001 | 0.0 |
| -18171.685547 | -18171.685547 | 0.001 | 0.0 |
| -18195.621094 | -18195.621094 | 0.001 | 0.0 |
| -18171.392578 | -18171.392578 | 0.001 | 0.0 |
| -18162.59375 | -18162.59375 | 0.001 | 0.0 |
| -18148.865234 | -18148.865234 | 0.001 | 0.0 |
| -18135.007812 | -18135.007812 | 0.001 | 0.0 |
| -18126.544922 | -18126.544922 | 0.001 | 0.0 |
| -18126.539062 | -18126.539062 | 0.001 | 0.0 |
| -18134.189453 | -18134.189453 | 0.001 | 0.0 |
| -18145.203125 | -18145.203125 | 0.001 | 0.0 |
| -18154.601562 | -18154.601562 | 0.001 | 0.0 |
| -18160.289062 | -18160.289062 | 0.001 | 0.0 |
| -18164.990234 | -18164.990234 | 0.001 | 0.0 |
| -18174.554688 | -18174.554688 | 0.001 | 0.0 |
| -18192.367188 | -18192.367188 | 0.001 | 0.0 |
| -18215.488281 | -18215.488281 | 0.001 | 0.0 |
| -18235.001953 | -18235.001953 | 0.001 | 0.0 |
| -18242.037109 | -18242.037109 | 0.001 | 0.0 |
| -18233.199219 | -18233.199219 | 0.001 | 0.0 |
