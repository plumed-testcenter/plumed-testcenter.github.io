Check force on energy
---------------------

It is common practise to use the potential energy as a collective energy. Some MD codes thus pass the potential energy to PLUMED and
PLUMED can then apply forces on this collective variable.  We test that any forces that PLUMED applies on the potential energy are 
correctly passed back to the MD code by doing the following test.  We first run a short simulation at $T$ K with a timestep of $\tau$ ps.
During the course of this simulation we monitor the potential energy using the following PLUMED input:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <span class="plumedtooltip" style="color:green">ENERGY<span class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></span></span>
<b name="working1.datv" onclick='showPath("working1.dat","working1.datv","working1.datv","black")'>v</b><span style="display:none;" id="working1.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <span class="plumedtooltip" style="color:green">VOLUME<span class="right">Calculate the volume of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_v_o_l_u_m_e.html" style="color:green">More details</a><i></i></span></span>
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working1.date">e</b>,<b name="working1.datv">v</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=energy1
</pre>
 {% endraw %} 

We then run a second simulation (starting from identical conditions) at a temperature of $T\alpha$ and with a timestep of $\tau/\sqrt(\alpha)$.
The thermostat and barostat relaxation times are similarly divided by $\sqrt(\alpha)$.  In the tests that are run on this website we set $\sqrt(\alpha)=1.1$.
The PLUMED file above is used when this test is run but a different time series of energy values is recorded as the MD parameters in this second simulation are 
different.

If PLUMED is working correctly we should be able to recapture the time series of energy values for the first simulation by running an MD simulation with the modified 
parameters that were used in the second simulation and the following PLUMED input file:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working2.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working2.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working2.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working2.date" onclick='showPath("working2.dat","working2.date","working2.date","black")'>e</b><span style="display:none;" id="working2.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <span class="plumedtooltip" style="color:green">ENERGY<span class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></span></span>
<b name="working2.datv" onclick='showPath("working2.dat","working2.datv","working2.datv","black")'>v</b><span style="display:none;" id="working2.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <span class="plumedtooltip" style="color:green">VOLUME<span class="right">Calculate the volume of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_v_o_l_u_m_e.html" style="color:green">More details</a><i></i></span></span>
<span style="color:blue" class="comment"># slope is such that </span>
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working2.date">e</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=energy2
<span style="color:blue" class="comment"># slope should be (alpha-1)=0.21</span>
<span style="display:none;" id="working2.dat">The PRINT action with label <b></b> calculates something</span><span class="plumedtooltip" style="color:green">RESTRAINT<span class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/_r_e_s_t_r_a_i_n_t.html" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">AT<span class="right">the position of the restraint<i></i></span></span>=0.0 <span class="plumedtooltip">ARG<span class="right">the values the harmonic restraint acts upon<i></i></span></span>=<b name="working2.date">e</b> <span class="plumedtooltip">SLOPE<span class="right"> specifies that the restraint is linear and what the values of the force constants on each of the variables are<i></i></span></span>=0.21
</pre>
 {% endraw %} 

In other words, when forces are passed correctly the time series for the energies and volumes from the first and third of these calculations should be identical.  

To determine if PLUMED passes this test we calculate the difference between the time series that were observed in the first and third simulations described above.
We then divide this by the difference between the first and second time series.

An NPT version of this calculation is performed as well as an NVT calculation if the virial is passed to PLUMED.

# Trajectories

 1. Input and output files for the unpeturbed calculation are available in this [zip archive](engforces1_v2.10.zip)

 2. Input and output files for the peturbed calculation are available in this [zip archive](engforces3_v2.10.zip)

 3. Input and output files for the peturbed calculation in which a PLUMED restraint is used to undo the effect of the changed MD parameters are available in this [zip archive](engforces2_v2.10.zip)


# Results

| Original | With PLUMED | Effect of peturbation | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18966.5297 0.0391 | -18966.5297 0.0391 | 0.0000 0.0000 | 0.0000 0.0000 | 
| -18966.5513 0.0391 | -18966.5300 0.0391 | 0.0000 0.0000 | 49467.4418 0.0000 | 
| -18966.6373 0.0391 | -18966.5963 0.0391 | 0.0113 0.0000 | 362.6858 0.0000 | 
| -18966.7789 0.0391 | -18966.7237 0.0391 | 0.0315 0.0000 | 175.1634 0.0000 | 
| -18966.9627 0.0391 | -18966.8979 0.0391 | 0.0573 0.0000 | 113.1224 0.0000 | 
| -18967.1740 0.0391 | -18967.1044 0.0391 | 0.0848 0.0000 | 82.1394 0.0000 | 
| -18967.3977 0.0391 | -18967.3278 0.0391 | 0.1102 0.0000 | 63.4315 0.0000 | 
| -18967.6194 0.0391 | -18967.5534 0.0391 | 0.1300 0.0000 | 50.7596 0.0000 | 
| -18967.8262 0.0391 | -18967.7675 0.0391 | 0.1415 0.0000 | 41.4355 0.0000 | 
| -18968.0076 0.0391 | -18967.9589 0.0391 | 0.1429 0.0000 | 34.0690 0.0000 | 
| -18968.1559 0.0391 | -18968.1188 0.0391 | 0.1333 0.0000 | 27.7847 0.0000 | 
| -18968.2664 0.0391 | -18968.2417 0.0391 | 0.1132 0.0000 | 21.8198 0.0000 | 
| -18968.3374 0.0391 | -18968.3248 0.0391 | 0.0839 0.0000 | 14.9662 0.0000 | 
| -18968.3700 0.0391 | -18968.3687 0.0391 | 0.0475 0.0000 | 2.8990 0.0000 | 
| -18968.3678 0.0391 | -18968.3760 0.0391 | 0.0067 0.0000 | 121.8592 0.0000 | 
| -18968.3361 0.0391 | -18968.3518 0.0391 | 0.0353 0.0000 | 44.5570 0.0000 | 
| -18968.2816 0.0391 | -18968.3026 0.0391 | 0.0756 0.0000 | 27.7426 0.0000 | 
| -18968.2118 0.0391 | -18968.2356 0.0391 | 0.1111 0.0000 | 21.4292 0.0000 | 
| -18968.1342 0.0391 | -18968.1585 0.0391 | 0.1394 0.0000 | 17.4678 0.0000 | 
| -18968.0561 0.0391 | -18968.0789 0.0391 | 0.1586 0.0000 | 14.3948 0.0000 | 


The table below includes some of the results from the calculation.  The columns contain:

1. Time series for the energy and volume that were obtained from the simulation at $T$ K, $x_{md}$.
2. Time series for the energy and volume that were obtained from the simulation at $\alpha T$ K and in which PLUMED applied a restraint on the energy, $x_{pl}$.
3. The absolute value of the difference between the time series of energies and volumes that were obtained from the simulations running at $T$ K and $\alpha T$ K, $\vert x_{md}'-x_{md} \vert$.  No PLUMED restraints were applied in either of these simulations.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \vert x_{md}'-x_{md} \vert}$. 

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![engforces_v2.10](./engforces_v2.10.png)
