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
Input and output files for the test calculation are available in this [zip archive](energy_v2.10.zip)


# Results

The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18966.52973640239 | -18966.529736 | 0.001 | 0.04023895598948002 |
| -18966.704937232018 | -18966.704937 | 0.001 | 0.023201937437988818 |
| -18967.09136587988 | -18967.091366 | 0.001 | 0.012011878425255418 |
| -18967.678401369227 | -18967.678401 | 0.001 | 0.03692257450893521 |
| -18968.451371401476 | -18968.451371 | 0.001 | 0.04014764272142202 |
| -18969.3926438271 | -18969.392644 | 0.001 | 0.017289858078584075 |
| -18970.482902614112 | -18970.482903 | 0.001 | 0.03858876880258322 |
| -18971.7024737211 | -18971.702474 | 0.001 | 0.027890200726687908 |
| -18973.032646253672 | -18973.032646 | 0.001 | 0.025367262423969805 |
| -18974.456846601744 | -18974.456847 | 0.001 | 0.0398256815969944 |
| -18975.961589782604 | -18975.96159 | 0.001 | 0.02173946995753795 |
| -18977.537144930055 | -18977.537145 | 0.001 | 0.006994378054514527 |
| -18979.177885978428 | -18979.177886 | 0.001 | 0.0021573214326053858 |
| -18980.882316176074 | -18980.882316 | 0.001 | 0.01760745362844318 |
| -18982.652788196647 | -18982.652788 | 0.001 | 0.019664730643853545 |
| -18984.494953740883 | -18984.494954 | 0.001 | 0.025911867851391435 |
| -18986.417000624588 | -18986.417001 | 0.001 | 0.03754139470402151 |
| -18988.42874080281 | -18988.428741 | 0.001 | 0.01971893652807921 |
| -18990.540618046325 | -18990.540618 | 0.001 | 0.004632602212950587 |
| -18992.762704060202 | -18992.762704 | 0.001 | 0.006020127329975367 |
