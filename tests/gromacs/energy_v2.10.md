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
| -18174.822266 | -18174.822266 | 0.001 | 0.0 |
| -18171.820312 | -18171.820312 | 0.001 | 0.0 |
| -18194.267578 | -18194.267578 | 0.001 | 0.0 |
| -18166.804688 | -18166.804688 | 0.001 | 0.0 |
| -18153.917969 | -18153.917969 | 0.001 | 0.0 |
| -18136.134766 | -18136.134766 | 0.001 | 0.0 |
| -18119.140625 | -18119.140625 | 0.001 | 0.0 |
| -18108.785156 | -18108.785156 | 0.001 | 0.0 |
| -18108.222656 | -18108.222656 | 0.001 | 0.0 |
| -18116.259766 | -18116.259766 | 0.001 | 0.0 |
| -18128.107422 | -18128.107422 | 0.001 | 0.0 |
| -18138.246094 | -18138.246094 | 0.001 | 0.0 |
| -18144.300781 | -18144.300781 | 0.001 | 0.0 |
| -18149.003906 | -18149.003906 | 0.001 | 0.0 |
| -18158.289062 | -18158.289062 | 0.001 | 0.0 |
| -18175.90625 | -18175.90625 | 0.001 | 0.0 |
| -18198.978516 | -18198.978516 | 0.001 | 0.0 |
| -18218.652344 | -18218.652344 | 0.001 | 0.0 |
| -18225.929688 | -18225.929688 | 0.001 | 0.0 |
| -18217.378906 | -18217.378906 | 0.001 | 0.0 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_v2.10](./energy_v2.10.png)
