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
| -18174.695312 | 0.0 | 0.001 | 1817469531.1999998 |
| -18171.693359 | 0.0 | 0.001 | 1817169335.9 |
| -18192.085938 | 0.0 | 0.001 | 1819208593.8000002 |
| -18160.384766 | 0.0 | 0.001 | 1816038476.6 |
| -18142.001953 | 0.0 | 0.001 | 1814200195.2999997 |
| -18118.791016 | 0.0 | 0.001 | 1811879101.6 |
| -18097.570312 | 0.0 | 0.001 | 1809757031.1999998 |
| -18084.710938 | 0.0 | 0.001 | 1808471093.8000002 |
| -18083.382812 | 0.0 | 0.001 | 1808338281.1999998 |
| -18091.949219 | 0.0 | 0.001 | 1809194921.8999996 |
| -18104.884766 | 0.0 | 0.001 | 1810488476.6 |
| -18115.994141 | 0.0 | 0.001 | 1811599414.1 |
| -18122.509766 | 0.0 | 0.001 | 1812250976.6 |
| -18127.234375 | 0.0 | 0.001 | 1812723437.5 |
| -18136.210938 | 0.0 | 0.001 | 1813621093.8000002 |
| -18153.552734 | 0.0 | 0.001 | 1815355273.4 |
| -18176.552734 | 0.0 | 0.001 | 1817655273.4 |
| -18196.439453 | 0.0 | 0.001 | 1819643945.2999997 |
| -18204.080078 | 0.0 | 0.001 | 1820408007.7999997 |
| -18195.865234 | 0.0 | 0.001 | 1819586523.4 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_master](./energy_master.png)
