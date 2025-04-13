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
| -18194.296875 | 0.0 | 0.001 | 1819429687.5 |
| -18167.244141 | 0.0 | 0.001 | 1816724414.1 |
| -18154.830078 | 0.0 | 0.001 | 1815483007.7999997 |
| -18137.515625 | 0.0 | 0.001 | 1813751562.5 |
| -18120.894531 | 0.0 | 0.001 | 1812089453.1000004 |
| -18110.751953 | 0.0 | 0.001 | 1811075195.2999997 |
| -18110.255859 | 0.0 | 0.001 | 1811025585.9 |
| -18118.246094 | 0.0 | 0.001 | 1811824609.3999996 |
| -18129.976562 | 0.0 | 0.001 | 1812997656.1999998 |
| -18140.060547 | 0.0 | 0.001 | 1814006054.7000003 |
| -18146.078125 | 0.0 | 0.001 | 1814607812.5 |
| -18150.757812 | 0.0 | 0.001 | 1815075781.1999998 |
| -18160.099609 | 0.0 | 0.001 | 1816009960.9 |
| -18177.707031 | 0.0 | 0.001 | 1817770703.1 |
| -18200.806641 | 0.0 | 0.001 | 1820080664.1 |
| -18220.464844 | 0.0 | 0.001 | 1822046484.3999996 |
| -18227.691406 | 0.0 | 0.001 | 1822769140.6 |
| -18219.130859 | 0.0 | 0.001 | 1821913085.9 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_v2.10](./energy_v2.10.png)
