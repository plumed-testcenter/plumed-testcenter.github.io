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
| -18192.046875 | -18192.046875 | 0.001 | 0.0 |
| -18160.208984 | -18160.208984 | 0.001 | 0.0 |
| -18141.693359 | -18141.693359 | 0.001 | 0.0 |
| -18118.324219 | -18118.324219 | 0.001 | 0.0 |
| -18096.960938 | -18096.960938 | 0.001 | 0.0 |
| -18084.044922 | -18084.044922 | 0.001 | 0.0 |
| -18082.720703 | -18082.720703 | 0.001 | 0.0 |
| -18091.277344 | -18091.277344 | 0.001 | 0.0 |
| -18104.212891 | -18104.212891 | 0.001 | 0.0 |
| -18115.380859 | -18115.380859 | 0.001 | 0.0 |
| -18121.935547 | -18121.935547 | 0.001 | 0.0 |
| -18126.613281 | -18126.613281 | 0.001 | 0.0 |
| -18135.603516 | -18135.603516 | 0.001 | 0.0 |
| -18152.933594 | -18152.933594 | 0.001 | 0.0 |
| -18175.90625 | -18175.90625 | 0.001 | 0.0 |
| -18195.820312 | -18195.820312 | 0.001 | 0.0 |
| -18203.482422 | -18203.482422 | 0.001 | 0.0 |
| -18195.28125 | -18195.28125 | 0.001 | 0.0 |
