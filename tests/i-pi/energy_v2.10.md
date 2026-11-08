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
| -114.50886 | -114.50886 | 0.001 | 0.0 |
| -114.556875 | -114.556875 | 0.001 | 0.0 |
| -114.628905 | -114.628905 | 0.001 | 0.0 |
| -114.702657 | -114.702657 | 0.001 | 0.0 |
| -114.803005 | -114.803005 | 0.001 | 0.0 |
| -114.908589 | -114.908589 | 0.001 | 0.0 |
| -115.033166 | -115.033165 | 0.001 | 0.09999999974752427 |
| -115.162033 | -115.162033 | 0.001 | 0.0 |
| -115.319446 | -115.319446 | 0.001 | 0.0 |
| -115.480075 | -115.480075 | 0.001 | 0.0 |
| -115.651447 | -115.651447 | 0.001 | 0.0 |
| -115.816718 | -115.816718 | 0.001 | 0.0 |
| -116.003928 | -116.003928 | 0.001 | 0.0 |
| -116.19971000000001 | -116.19971 | 0.001 | 1.4210854715202004e-09 |
| -116.39500699999999 | -116.395007 | 0.001 | 1.4210854715202004e-09 |
| -116.597252 | -116.597252 | 0.001 | 0.0 |
| -116.80978599999999 | -116.809786 | 0.001 | 1.4210854715202004e-09 |
| -117.031194 | -117.031194 | 0.001 | 0.0 |
| -117.235882 | -117.235882 | 0.001 | 0.0 |
| -117.450351 | -117.450351 | 0.001 | 0.0 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_v2.10](./energy_v2.10.png)
