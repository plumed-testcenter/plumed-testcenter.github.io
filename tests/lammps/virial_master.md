Check virial contribution
-------------------------

If you are running simulations at constant pressure then the virial forces cause the cell parameters 
to change with time.  Any CVs calculated by PLUMED contribute to these virial forces and PLUMED must,
therefore, have a mechanism to pass virial forces back to the MD code. 

To debug this mechanism we run a constant pressure simulation at 1 bar using the MD code.  During this simulation
we use the following PLUMED input to monitor the cell volume:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.datv" onclick='showPath("this_input_should_work.dat","this_input_should_work.datv")'>v</b>: <div class="tooltip" style="color:green">VOLUME<div class="right">Calculate the volume of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_v_o_l_u_m_e.html" style="color:green">More details</a><i></i></div></div>
<span style="display:none;" id="this_input_should_work.datv">The VOLUME action with label <b>v</b> calculates a scalar quantity</span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.datv">v</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=volume
</pre>
 {% endraw %} 

We then run a second constant pressure MD simulation at a pressure of 1001 bar and with the following PLUMED restraint 
applied:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.datv" onclick='showPath("this_input_should_work.dat","this_input_should_work.datv")'>v</b>: <div class="tooltip" style="color:green">VOLUME<div class="right">Calculate the volume of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_v_o_l_u_m_e.html" style="color:green">More details</a><i></i></div></div> 
<span style="color:blue"># slope should be just 10 times the Avogadro constant:</span>
<span style="display:none;" id="this_input_should_work.datv">The VOLUME action with label <b>v</b> calculates a scalar quantity</span><div class="tooltip" style="color:green">RESTRAINT<div class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/_r_e_s_t_r_a_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">AT<div class="right">the position of the restraint<i></i></div></div>=0.0 <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.datv">v</b> <div class="tooltip">SLOPE<div class="right"> specifies that the restraint is linear and what the values of the force constants on each of the variables are<i></i></div></div>=-60.2214129
<span style="display:none;" id="this_input_should_work.dat">The RESTRAINT action with label <b></b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">.bias</td><td>the instantaneous value of the bias potential</td></tr><tr><td width="5%">.force2</td><td>the instantaneous value of the squared force due to this bias potential</td></tr></table></span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the input for this action is the scalar output from one or more other actions<i></i></div></div>=<b name="this_input_should_work.datv">v</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=volume2
</pre>
 {% endraw %} 

The PLUMED restraint in this second calculation applies a negative pressure of 1000bar, which should compensate the fact that the 
second calculation was run at higher pressure.  The time series for the volumes that are output by the files `volume` and `volume2`
above should thus be close to identicial. 

# Trajectories
1. Input and output files for the first calculation described above are available in this [zip archive](virial1_master.zip) 
2. Input and output files for the second calculation described above are available in this [zip archive](virial2_master.zip) 


# Results

The table below contains the PLUMED outputs from the two calculations described above.
If the PLUMED interface is working correctly these two sets of numbers should be identical.

| First result | Second result | 
|:-------------|:--------------| 
|20.5064 | 20.5064 | 
|20.50651 | 20.50651 | 
|20.50609 | 20.50609 | 
|20.50513 | 20.50513 | 
|20.5036 | 20.5036 | 
|20.50144 | 20.50144 | 
|20.49858 | 20.49858 | 
|20.49496 | 20.49495 | 
|20.4905 | 20.4905 | 
|20.48517 | 20.48517 | 
|20.47895 | 20.47895 | 
|20.47182 | 20.47182 | 
|20.46376 | 20.46376 | 
|20.45478 | 20.45478 | 
|20.44485 | 20.44485 | 
|20.43399 | 20.43398 | 
|20.42219 | 20.42218 | 
|20.40948 | 20.40948 | 
|20.39593 | 20.39592 | 
|20.38159 | 20.38159 | 
