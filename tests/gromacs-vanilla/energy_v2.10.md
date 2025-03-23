Energy is passed correctly
--------------------------

It is common practise to use the potential energy as a collective energy.  Some MD codes thus pass the potential energy to PLUMED. 
To check that this quantity has been passed correctly we can output the passed energy from PLUMED using the following input.  

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <span class="plumedtooltip" style="color:green">ENERGY<span class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/ENERGY" style="color:green">More details</a><i></i></span></span> 
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working1.date">e</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=colvar
</pre>
 {% endraw %} 

We can then also output the energy from the MD code and check this matches the value output by PLUMED.  We run a short trajectory to test that the energy is passed correctly.

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](energy_v2.10.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18174.695312 | 0.0 | 0.001 | 1817469531.1999998 |
| -18171.693359 | 0.0 | 0.001 | 1817169335.9 |
| -18191.626953 | 0.0 | 0.001 | 1819162695.2999997 |
| -18158.90625 | 0.0 | 0.001 | 1815890625.0 |
| -18139.267578 | 0.0 | 0.001 | 1813926757.7999997 |
| -18114.779297 | 0.0 | 0.001 | 1811477929.7000003 |
| -18092.566406 | 0.0 | 0.001 | 1809256640.6000004 |
| -18079.119141 | 0.0 | 0.001 | 1807911914.1 |
| -18077.640625 | 0.0 | 0.001 | 1807764062.5 |
| -18086.302734 | 0.0 | 0.001 | 1808630273.4 |
| -18099.460938 | 0.0 | 0.001 | 1809946093.8000002 |
| -18110.822266 | 0.0 | 0.001 | 1811082226.6 |
| -18117.464844 | 0.0 | 0.001 | 1811746484.3999996 |
| -18122.169922 | 0.0 | 0.001 | 1812216992.2000003 |
| -18131.076172 | 0.0 | 0.001 | 1813107617.2000003 |
| -18148.337891 | 0.0 | 0.001 | 1814833789.1 |
| -18171.34375 | 0.0 | 0.001 | 1817134375.0 |
| -18191.302734 | 0.0 | 0.001 | 1819130273.4 |
| -18199.003906 | 0.0 | 0.001 | 1819900390.6 |
| -18190.873047 | 0.0 | 0.001 | 1819087304.7000003 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_v2.10](./energy_v2.10.png)
