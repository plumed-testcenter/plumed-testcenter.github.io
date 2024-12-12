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
| -18966.529736402383 | -18966.529736 | 0.001 | 0.0402382283937186 |
| -18966.70493723203 | -18966.704937 | 0.001 | 0.023203028831630945 |
| -18967.091365879875 | -18967.091366 | 0.001 | 0.012012606021016836 |
| -18967.678401369216 | -18967.678401 | 0.001 | 0.036921483115293086 |
| -18968.451371401472 | -18968.451371 | 0.001 | 0.04014727892354131 |
| -18969.39264382711 | -18969.392644 | 0.001 | 0.017289130482822657 |
| -18970.482902614112 | -18970.482903 | 0.001 | 0.03858876880258322 |
| -18971.702473721114 | -18971.702474 | 0.001 | 0.02788874553516507 |
| -18973.03264625367 | -18973.032646 | 0.001 | 0.025366898626089096 |
| -18974.456846601726 | -18974.456847 | 0.001 | 0.039827500586397946 |
| -18975.961589782557 | -18975.96159 | 0.001 | 0.02174419932998717 |
| -18977.537144930036 | -18977.537145 | 0.001 | 0.006996197043918073 |
| -18979.177885978374 | -18979.177886 | 0.001 | 0.0021627784008160233 |
| -18980.882316176034 | -18980.882316 | 0.001 | 0.01760345185175538 |
| -18982.65278819657 | -18982.652788 | 0.001 | 0.019657090888358653 |
| -18984.494953740745 | -18984.494954 | 0.001 | 0.025925692170858383 |
| -18986.41700062439 | -18986.417001 | 0.001 | 0.03756103978957981 |
| -18988.42874080259 | -18988.428741 | 0.001 | 0.01974112819880247 |
| -18990.540618046078 | -18990.540618 | 0.001 | 0.004607863957062364 |
| -18992.76270405992 | -18992.762704 | 0.001 | 0.00599211489316076 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.
### Graphical representation (_beta_)
A visualization of the table above:  
![energy_master](./energy_master.png)
