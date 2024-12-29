Energy is passed correctly
--------------------------

It is common practise to use the potential energy as a collective energy.  Some MD codes thus pass the potential energy to PLUMED. 
To check that this quantity has been passed correctly we can output the passed energy from PLUMED using the following input.  

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <div class="tooltip" style="color:green">ENERGY<div class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></div></div> 
<div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the labels of the values that you would like to print to the file<i></i></div></div>=<b name="working1.date">e</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=colvar
</pre>
 {% endraw %} 

We can then also output the energy from the MD code and check this matches the value output by PLUMED.  We run a short trajectory to test that the energy is passed correctly.

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](energy_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18174.685547 | 0.0 | 0.001 | 1817468554.7000003 |
| -18171.685547 | 0.0 | 0.001 | 1817168554.7000003 |
| -18193.777344 | 0.0 | 0.001 | 1819377734.3999996 |
| -18165.640625 | 0.0 | 0.001 | 1816564062.5 |
| -18151.828125 | 0.0 | 0.001 | 1815182812.5 |
| -18133.140625 | 0.0 | 0.001 | 1813314062.5 |
| -18115.445312 | 0.0 | 0.001 | 1811544531.1999998 |
| -18104.65625 | 0.0 | 0.001 | 1810465625.0 |
| -18103.955078 | 0.0 | 0.001 | 1810395507.7999997 |
| -18112.083984 | 0.0 | 0.001 | 1811208398.4 |
| -18124.117188 | 0.0 | 0.001 | 1812411718.8000002 |
| -18134.398438 | 0.0 | 0.001 | 1813439843.8000002 |
| -18140.566406 | 0.0 | 0.001 | 1814056640.6000004 |
| -18145.257812 | 0.0 | 0.001 | 1814525781.1999998 |
| -18154.466797 | 0.0 | 0.001 | 1815446679.7000003 |
| -18172.064453 | 0.0 | 0.001 | 1817206445.2999997 |
| -18195.150391 | 0.0 | 0.001 | 1819515039.1 |
| -18214.839844 | 0.0 | 0.001 | 1821483984.3999996 |
| -18222.154297 | 0.0 | 0.001 | 1822215429.7000003 |
| -18213.6875 | 0.0 | 0.001 | 1821368750.0 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_master](./energy_master.png)
