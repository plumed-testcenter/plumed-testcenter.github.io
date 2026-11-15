Checking PLUMED can add a restraint
-----------------------------------

To check that the forces are being correctly passed from PLUMED to the MD code we test that the result from a PLUMED
calculation where the following plumed input is used produces results that are equivalent to the result that is obtained
when the restraint is applied within the MD code.

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
<b name="working1.datdd" onclick='showPath("working1.dat","working1.datdd","working1.datdd","black")'>dd</b><span style="display:none;" id="working1.datdd">The DISTANCE action with label <b>dd</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">dd</td><td width="5%"><font color="black">scalar</font></td><td>the DISTANCE between this pair of atoms</td></tr></table></span>: <span class="plumedtooltip" style="color:green">DISTANCE<span class="right">Calculate the distance/s between pairs of atoms. <a href="https://www.plumed.org/doc-master/user-doc/html/DISTANCE" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ATOMS<span class="right">the pair of atom that we are calculating the distance between<i></i></span></span>=1,2 
<span class="plumedtooltip" style="color:green">RESTRAINT<span class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/RESTRAINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the values the harmonic restraint acts upon<i></i></span></span>=<b name="working1.datdd">dd</b> <span class="plumedtooltip">KAPPA<span class="right"> specifies that the restraint is harmonic and what the values of the force constants on each of the variables are<i></i></span></span>=2000 <span class="plumedtooltip">AT<span class="right">the position of the restraint<i></i></span></span>=0.6
<span style="display:none;" id="working1.dat">The RESTRAINT action with label <b></b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">.bias</td><td>the instantaneous value of the bias potential</td></tr><tr><td width="5%">.force2</td><td>the instantaneous value of the squared force due to this bias potential</td></tr></table></span><span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working1.datdd">dd</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=plumed_restraint
</pre></div>

 {% endraw %} 

To check that the two ways of applying the restraint are equivalent we use the following PLUMED input for the calculation
where the MD code applies the restraint:

{% raw %}
<div class="plumedInputContainer">
<div class="plumedpreheader">
<div class="headerInfo" id="value_details_working2.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div class="containerBadge">
<div class="headerBadge"><a href="working2.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></div>
<div class="headerBadge"><a href="working2.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></div>
</div>
</div>
<pre class="plumedlisting">
<b name="working2.datdd" onclick='showPath("working2.dat","working2.datdd","working2.datdd","black")'>dd</b><span style="display:none;" id="working2.datdd">The DISTANCE action with label <b>dd</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">dd</td><td width="5%"><font color="black">scalar</font></td><td>the DISTANCE between this pair of atoms</td></tr></table></span>: <span class="plumedtooltip" style="color:green">DISTANCE<span class="right">Calculate the distance/s between pairs of atoms. <a href="https://www.plumed.org/doc-master/user-doc/html/DISTANCE" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ATOMS<span class="right">the pair of atom that we are calculating the distance between<i></i></span></span>=1,2 
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working2.datdd">dd</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=mdcode_restraint
</pre></div>

 {% endraw %} 

# Trajectories

 1. Input and output files for the calculation where the restraint is applied by the MD code available in this [zip archive](forces1_master.zip)

 2. Input and output files for the calculation where the restraint is applied by PLUMED are available in this [zip archive](forces2_master.zip

# Results

| Original | With PLUMED | Effect of peturbation | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 0.095362 | 0.095362 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |
| 0.09572 | 0.09572 | 0.001 | 0.0 |


The table below includes some of the results from the calculation.  The columns contain:

1. The time series of distance values that were obtained when the restraint was applied by the MD code, $x_{md}$.
2. The time series of distance values that were obtained when the restraint was applied by PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta}$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![forces_master](./forces_master.png)
