Checking PLUMED can add a restraint
-----------------------------------

To check that the forces are being correctly passed from PLUMED to the MD code we test that the result from a PLUMED
calculation where the following plumed input is used produces results that are equivalent to the result that is obtained
when the restraint is applied within the MD code.

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.datdd" onclick='showPath("this_input_should_work.dat","this_input_should_work.datdd")'>dd</b>: <div class="tooltip" style="color:green">DISTANCE<div class="right">Calculate the distance between a pair of atoms. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_i_s_t_a_n_c_e.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ATOMS<div class="right">the pair of atom that we are calculating the distance between<i></i></div></div>=1,2 
<span style="display:none;" id="this_input_should_work.datdd">The DISTANCE action with label <b>dd</b> calculates a scalar quantity</span><div class="tooltip" style="color:green">RESTRAINT<div class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/_r_e_s_t_r_a_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.datdd">dd</b> <div class="tooltip">KAPPA<div class="right"> specifies that the restraint is harmonic and what the values of the force constants on each of the variables are<i></i></div></div>=2000 <div class="tooltip">AT<div class="right">the position of the restraint<i></i></div></div>=0.6
<span style="display:none;" id="this_input_should_work.dat">The RESTRAINT action with label <b></b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">.bias</td><td>the instantaneous value of the bias potential</td></tr><tr><td width="5%">.force2</td><td>the instantaneous value of the squared force due to this bias potential</td></tr></table></span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.datdd">dd</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=plumed_restraint <div class="tooltip">FMT<div class="right">the format that should be used to output real numbers<i></i></div></div>=%8.4f
</pre>
 {% endraw %} 

To check that the two ways of applying the restraint are equivalent we use the following PLUMED input for the calculation
where the MD code applies the restraint:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.datdd" onclick='showPath("this_input_should_work.dat","this_input_should_work.datdd")'>dd</b>: <div class="tooltip" style="color:green">DISTANCE<div class="right">Calculate the distance between a pair of atoms. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_i_s_t_a_n_c_e.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ATOMS<div class="right">the pair of atom that we are calculating the distance between<i></i></div></div>=1,2 
<span style="display:none;" id="this_input_should_work.datdd">The DISTANCE action with label <b>dd</b> calculates a scalar quantity</span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.datdd">dd</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=mdcode_restraint <div class="tooltip">FMT<div class="right">the format that should be used to output real numbers<i></i></div></div>=%8.4f
</pre>
 {% endraw %} 

# Trajectories
1. Input and output files for the first calculation described above are available in this [zip archive](forces1_master.zip) 
2. Input and output files for the second calculation described above are available in this [zip archive](forces2_master.zip) 


# Results

The table below contains the PLUMED outputs from the two calculations described above.  
If the PLUMED interface is working correctly these two sets of numbers should be identical.

| First result | Second result | 
|:-------------|:--------------| 
|1.1976 | 1.1976 | 
|1.2069 | 1.2069 | 
|1.2143 | 1.2143 | 
|1.2203 | 1.2203 | 
|1.2254 | 1.2254 | 
|1.2275 | 1.2275 | 
|1.2263 | 1.2263 | 
|1.2215 | 1.2215 | 
|1.214 | 1.214 | 
|1.2042 | 1.2042 | 
|1.1942 | 1.1942 | 
|1.1836 | 1.1836 | 
|1.1746 | 1.1746 | 
|1.1678 | 1.1678 | 
|1.1649 | 1.1649 | 
|1.1652 | 1.1652 | 
|1.1686 | 1.1686 | 
|1.1762 | 1.1762 | 
|1.186 | 1.186 | 
|1.1976 | 1.1976 | 
