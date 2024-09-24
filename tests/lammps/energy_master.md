Energy is passed correctly
--------------------------

It is common practise to use the potential energy as a collective energy.  Some MD codes thus pass the potential energy to PLUMED. 
To check that this quantity has been passed correctly we can output the passed energy from PLUMED using the following input.  

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.9-passing-green.svg" alt="tested on2.9" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the value calculated by this action</td></tr></table></span>: <div class="tooltip" style="color:green">ENERGY<div class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></div></div> 
<div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="working1.date">e</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=colvar
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
| -26662.023362171738 | -26662.023362 | 0.005 | 0.00343476131092757 |
| -26632.845062414224 | -26632.845062 | 0.005 | 0.00828447809908539 |
| -26571.84180244003 | -26571.841802 | 0.005 | 0.008800634532235563 |
| -26484.64847577198 | -26484.648476 | 0.005 | 0.004560351953841746 |
| -26378.638440109673 | -26378.63844 | 0.005 | 0.0021934829419478774 |
| -26263.101040691552 | -26263.101041 | 0.005 | 0.0061689934227615595 |
| -26147.526075363567 | -26147.526075 | 0.005 | 0.0072713010013103485 |
| -26041.40562157617 | -26041.405622 | 0.005 | 0.008476563380099833 |
| -25953.472634716538 | -25953.472635 | 0.005 | 0.0056692078942433 |
| -25889.941958807263 | -25889.941959 | 0.005 | 0.003854729584418237 |
| -25854.79540522634 | -25854.795405 | 0.005 | 0.00452680978924036 |
| -25849.53260679386 | -25849.532607 | 0.005 | 0.0041228486225008965 |
| -25872.534978896565 | -25872.534979 | 0.005 | 0.0020687002688646317 |
| -25918.898382744654 | -25918.898383 | 0.005 | 0.005106921889819205 |
| -25982.626643123334 | -25982.626643 | 0.005 | 0.002466695150360465 |
| -26055.603510713423 | -26055.603511 | 0.005 | 0.005731562850996852 |
| -26129.23866948293 | -26129.238669 | 0.005 | 0.009658615454100072 |
| -26195.46794711287 | -26195.467947 | 0.005 | 0.002257365849800408 |
| -26247.43420422737 | -26247.434204 | 0.005 | 0.004547400749288499 |
| -26279.650845124073 | -26279.650845 | 0.005 | 0.0024814653443172574 |
