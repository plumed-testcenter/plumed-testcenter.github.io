Checking PLUMED can add a restraint
-----------------------------------

To check that the forces are being correctly passed from PLUMED to the MD code we test that the result from a PLUMED
calculation where the following plumed input is used produces results that are equivalent to the result that is obtained
when the restraint is applied within the MD code.

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.9-passing-green.svg" alt="tested on2.9" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.datdd" onclick='showPath("working1.dat","working1.datdd","working1.datdd","black")'>dd</b><span style="display:none;" id="working1.datdd">The DISTANCE action with label <b>dd</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">dd</td><td width="5%"><font color="black">scalar</font></td><td>the DISTANCE between this pair of atoms</td></tr></table></span>: <div class="tooltip" style="color:green">DISTANCE<div class="right">Calculate the distance between a pair of atoms. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_i_s_t_a_n_c_e.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ATOMS<div class="right">the pair of atom that we are calculating the distance between<i></i></div></div>=1,2 
<div class="tooltip" style="color:green">RESTRAINT<div class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/_r_e_s_t_r_a_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the arguments on which the bias is acting<i></i></div></div>=<b name="working1.datdd">dd</b> <div class="tooltip">KAPPA<div class="right"> specifies that the restraint is harmonic and what the values of the force constants on each of the variables are<i></i></div></div>=2000 <div class="tooltip">AT<div class="right">the position of the restraint<i></i></div></div>=0.6
<span style="display:none;" id="working1.dat">The RESTRAINT action with label <b></b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">.bias</td><td>the instantaneous value of the bias potential</td></tr><tr><td width="5%">.force2</td><td>the instantaneous value of the squared force due to this bias potential</td></tr></table></span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="working1.datdd">dd</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=plumed_restraint
</pre>
 {% endraw %} 

To check that the two ways of applying the restraint are equivalent we use the following PLUMED input for the calculation
where the MD code applies the restraint:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working2.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working2.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.9-passing-green.svg" alt="tested on2.9" /></a></td></tr><tr><td style="padding:1px"><a href="working2.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working2.datdd" onclick='showPath("working2.dat","working2.datdd","working2.datdd","black")'>dd</b><span style="display:none;" id="working2.datdd">The DISTANCE action with label <b>dd</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">dd</td><td width="5%"><font color="black">scalar</font></td><td>the DISTANCE between this pair of atoms</td></tr></table></span>: <div class="tooltip" style="color:green">DISTANCE<div class="right">Calculate the distance between a pair of atoms. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_i_s_t_a_n_c_e.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ATOMS<div class="right">the pair of atom that we are calculating the distance between<i></i></div></div>=1,2 
<div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="working2.datdd">dd</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=mdcode_restraint
</pre>
 {% endraw %} 

# Trajectories
1. Input and output files for the calculation where the restraint is applied by the MD code available in this [zip archive](forces1_master.zip)
2. Input and output files for the calculation where the restraint is applied by PLUMED are available in this [zip archive](forces2_master.zip)


# Results

The table below includes some of the results from the calculation.  The columns contain:

1. The time series of distance values that were obtained when the restraint was applied by the MD code, $x_{md}$.
2. The time series of distance values that were obtained when the restraint was applied by PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta}$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

| Original result | Result with PLUMED | Effect of peturbation | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 0.146553 | 0.146553 | 0.005 | 0.0 |
| 0.146878 | 0.146878 | 0.005 | 0.0 |
| 0.147201 | 0.147201 | 0.005 | 0.0 |
| 0.147521 | 0.147521 | 0.005 | 0.0 |
| 0.147836 | 0.147836 | 0.005 | 0.0 |
| 0.148145 | 0.148145 | 0.005 | 0.0 |
| 0.148447 | 0.148448 | 0.005 | 0.020000000000020002 |
| 0.148741 | 0.148742 | 0.005 | 0.020000000000020002 |
| 0.149026 | 0.149028 | 0.005 | 0.040000000000040004 |
| 0.149301 | 0.149304 | 0.005 | 0.060000000000060005 |
| 0.149565 | 0.149569 | 0.005 | 0.08000000000008001 |
| 0.149817 | 0.149822 | 0.005 | 0.10000000000010001 |
| 0.150057 | 0.150062 | 0.005 | 0.10000000000010001 |
| 0.150282 | 0.15029 | 0.005 | 0.16000000000016001 |
| 0.150494 | 0.150503 | 0.005 | 0.18000000000018002 |
| 0.150691 | 0.150702 | 0.005 | 0.22000000000022002 |
| 0.150873 | 0.150887 | 0.005 | 0.2799999999997249 |
| 0.15104 | 0.151055 | 0.005 | 0.2999999999997449 |
| 0.15119 | 0.151208 | 0.005 | 0.36000000000036003 |
| 0.151325 | 0.151346 | 0.005 | 0.42000000000042004 |
