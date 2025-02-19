Energy is passed correctly
--------------------------

It is common practise to use the potential energy as a collective energy.  Some MD codes thus pass the potential energy to PLUMED. 
To check that this quantity has been passed correctly we can output the passed energy from PLUMED using the following input.  

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <span class="plumedtooltip" style="color:green">ENERGY<span class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></span></span> 
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working1.date">e</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=colvar
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
| -18194.783203 | 0.0 | 0.001 | 1819478320.2999997 |
| -18168.839844 | 0.0 | 0.001 | 1816883984.3999996 |
| -18157.791016 | 0.0 | 0.001 | 1815779101.6 |
| -18141.878906 | 0.0 | 0.001 | 1814187890.6000004 |
| -18126.310547 | 0.0 | 0.001 | 1812631054.7000003 |
| -18116.824219 | 0.0 | 0.001 | 1811682421.8999996 |
| -18116.494141 | 0.0 | 0.001 | 1811649414.1 |
| -18124.365234 | 0.0 | 0.001 | 1812436523.4 |
| -18135.826172 | 0.0 | 0.001 | 1813582617.2000003 |
| -18145.632812 | 0.0 | 0.001 | 1814563281.1999998 |
| -18151.517578 | 0.0 | 0.001 | 1815151757.7999997 |
| -18156.220703 | 0.0 | 0.001 | 1815622070.2999997 |
| -18165.623047 | 0.0 | 0.001 | 1816562304.7000003 |
| -18183.328125 | 0.0 | 0.001 | 1818332812.5 |
| -18206.433594 | 0.0 | 0.001 | 1820643359.3999996 |
| -18226.019531 | 0.0 | 0.001 | 1822601953.1 |
| -18233.197266 | 0.0 | 0.001 | 1823319726.6 |
| -18224.535156 | 0.0 | 0.001 | 1822453515.6 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_v2.10](./energy_v2.10.png)
