Energy is passed correctly
--------------------------

It is common practise to use the potential energy as a collective energy.  Some MD codes thus pass the potential energy to PLUMED. 
To check that this quantity has been passed correctly we can output the passed energy from PLUMED using the following input.  

{% raw %}
<div class="plumedInputContainer">
<div class="plumedpreheader">
<div class="headerInfo" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div class="containerBadge">
<div class="headerBadge"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></div>
<div class="headerBadge"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></div>
</div>
</div>
<pre class="plumedlisting">
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <span class="plumedtooltip" style="color:green">ENERGY<span class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/ENERGY" style="color:green">More details</a><i></i></span></span> 
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working1.date">e</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=colvar
</pre></div>

 {% endraw %} 

We can then also output the energy from the MD code and check this matches the value output by PLUMED.  We run a short trajectory to test that the energy is passed correctly.

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](energy_v2.10.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18966.5297364024 | -18966.529736 | 0.001 | 0.040240047383122146 |
| -18966.70493723203 | -18966.704937 | 0.001 | 0.023203028831630945 |
| -18967.091365879875 | -18967.091366 | 0.001 | 0.012012606021016836 |
| -18967.678401369227 | -18967.678401 | 0.001 | 0.03692257450893521 |
| -18968.451371401472 | -18968.451371 | 0.001 | 0.04014727892354131 |
| -18969.3926438271 | -18969.392644 | 0.001 | 0.017289858078584075 |
| -18970.482902614105 | -18970.482903 | 0.001 | 0.038589496398344636 |
| -18971.70247372111 | -18971.702474 | 0.001 | 0.02788910933304578 |
| -18973.03264625365 | -18973.032646 | 0.001 | 0.02536507963668555 |
| -18974.456846601748 | -18974.456847 | 0.001 | 0.03982531779911369 |
| -18975.961589782615 | -18975.96159 | 0.001 | 0.02173837856389582 |
| -18977.53714493007 | -18977.537145 | 0.001 | 0.006992922862991691 |
| -18979.177885978435 | -18979.177886 | 0.001 | 0.0021565938368439674 |
| -18980.882316176092 | -18980.882316 | 0.001 | 0.017609272617846727 |
| -18982.65278819662 | -18982.652788 | 0.001 | 0.01966218405868858 |
| -18984.494953740817 | -18984.494954 | 0.001 | 0.0259184162132442 |
| -18986.417000624475 | -18986.417001 | 0.001 | 0.0375526724383235 |
| -18988.428740802647 | -18988.428741 | 0.001 | 0.019735307432711124 |
| -18990.54061804617 | -18990.540618 | 0.001 | 0.004616958904080093 |
| -18992.762704060024 | -18992.762704 | 0.001 | 0.006002301233820617 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_v2.10](./energy_v2.10.png)
