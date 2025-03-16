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

Input and output files for the test calculation are available inthis [zip archive](energy_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18174.822266 | -18174.822266 | 0.001 | 0.0 |
| -18171.820312 | -18171.820312 | 0.001 | 0.0 |
| -18192.25 | -18192.25 | 0.001 | 0.0 |
| -18160.597656 | -18160.597656 | 0.001 | 0.0 |
| -18142.248047 | -18142.248047 | 0.001 | 0.0 |
| -18119.130859 | -18119.130859 | 0.001 | 0.0 |
| -18097.923828 | -18097.923828 | 0.001 | 0.0 |
| -18085.119141 | -18085.119141 | 0.001 | 0.0 |
| -18083.826172 | -18083.826172 | 0.001 | 0.0 |
| -18092.378906 | -18092.378906 | 0.001 | 0.0 |
| -18105.261719 | -18105.261719 | 0.001 | 0.0 |
| -18116.367188 | -18116.367188 | 0.001 | 0.0 |
| -18122.929688 | -18122.929688 | 0.001 | 0.0 |
| -18127.599609 | -18127.599609 | 0.001 | 0.0 |
| -18136.59375 | -18136.59375 | 0.001 | 0.0 |
| -18153.943359 | -18153.943359 | 0.001 | 0.0 |
| -18176.957031 | -18176.957031 | 0.001 | 0.0 |
| -18196.841797 | -18196.841797 | 0.001 | 0.0 |
| -18204.472656 | -18204.472656 | 0.001 | 0.0 |
| -18196.242188 | -18196.242188 | 0.001 | 0.0 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_master](./energy_master.png)
