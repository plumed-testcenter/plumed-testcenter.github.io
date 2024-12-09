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
| -18174.685547 | 0.0 | 0.001 | 1817468554.7000003 |
| -18171.685547 | 0.0 | 0.001 | 1817168554.7000003 |
| -18194.324219 | 0.0 | 0.001 | 1819432421.8999996 |
| -18167.296875 | 0.0 | 0.001 | 1816729687.5 |
| -18154.951172 | 0.0 | 0.001 | 1815495117.2000003 |
| -18137.728516 | 0.0 | 0.001 | 1813772851.6 |
| -18121.160156 | 0.0 | 0.001 | 1812116015.6000004 |
| -18111.029297 | 0.0 | 0.001 | 1811102929.7000003 |
| -18110.556641 | 0.0 | 0.001 | 1811055664.1 |
| -18118.552734 | 0.0 | 0.001 | 1811855273.4 |
| -18130.287109 | 0.0 | 0.001 | 1813028710.9 |
| -18140.324219 | 0.0 | 0.001 | 1814032421.8999996 |
| -18146.326172 | 0.0 | 0.001 | 1814632617.2000003 |
| -18151.011719 | 0.0 | 0.001 | 1815101171.8999996 |
| -18160.330078 | 0.0 | 0.001 | 1816033007.7999997 |
| -18177.974609 | 0.0 | 0.001 | 1817797460.9 |
| -18201.056641 | 0.0 | 0.001 | 1820105664.1 |
| -18220.707031 | 0.0 | 0.001 | 1822070703.1 |
| -18227.966797 | 0.0 | 0.001 | 1822796679.7000003 |
| -18219.357422 | 0.0 | 0.001 | 1821935742.2000003 |
