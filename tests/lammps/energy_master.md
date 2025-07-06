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

Input and output files for the test calculation are available inthis [zip archive](energy_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -26662.023202712553 | -26662.023203 | 0.005 | 0.00574895238969475 |
| -26632.84468076611 | -26632.844681 | 0.005 | 0.004677785909734666 |
| -26571.841077989804 | -26571.841078 | 0.005 | 0.00020394509192556143 |
| -26484.64806516556 | -26484.648065 | 0.005 | 0.0033111427910625935 |
| -26378.637898879817 | -26378.637899 | 0.005 | 0.0024036853574216366 |
| -26263.100683835386 | -26263.100684 | 0.005 | 0.0032922980608418584 |
| -26147.525538904225 | -26147.525539 | 0.005 | 0.0019154686015099287 |
| -26041.405136887217 | -26041.405137 | 0.005 | 0.0022556923795491457 |
| -25953.472415946602 | -25953.472416 | 0.005 | 0.0010679650586098433 |
| -25889.941702902524 | -25889.941703 | 0.005 | 0.0019495200831443071 |
| -25854.794730091377 | -25854.79473 | 0.005 | 0.001827502273954451 |
| -25849.531907310018 | -25849.531907 | 0.005 | 0.00620035280007869 |
| -25872.535179280665 | -25872.535179 | 0.005 | 0.005613328539766371 |
| -25918.898258596586 | -25918.898259 | 0.005 | 0.008068309398368001 |
| -25982.626303386172 | -25982.626303 | 0.005 | 0.007723429007455707 |
| -26055.603608318946 | -26055.603608 | 0.005 | 0.006378904799930751 |
| -26129.238020653902 | -26129.238021 | 0.005 | 0.006921982276253402 |
| -26195.467198839367 | -26195.467199 | 0.005 | 0.00321262632496655 |
| -26247.434077086193 | -26247.434077 | 0.005 | 0.0017238198779523373 |
| -26279.650245710513 | -26279.650246 | 0.005 | 0.005789770511910319 |


The table below includes some of the results from the calculation.  The columns contain:

1. The energies that were obtained from the MD code, $x_{md}$.
2. The energies that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![energy_master](./energy_master.png)
