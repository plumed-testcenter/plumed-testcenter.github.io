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
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <div class="tooltip" style="color:green">ENERGY<div class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></div></div>
<b name="working1.datv" onclick='showPath("working1.dat","working1.datv","working1.datv","black")'>v</b><span style="display:none;" id="working1.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <div class="tooltip" style="color:green">VOLUME<div class="right">Calculate the volume of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_v_o_l_u_m_e.html" style="color:green">More details</a><i></i></div></div>
<div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the labels of the values that you would like to print to the file<i></i></div></div>=<b name="working1.date">e</b>,<b name="working1.datv">v</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=energy1
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
<b name="working2.date" onclick='showPath("working2.dat","working2.date","working2.date","black")'>e</b><span style="display:none;" id="working2.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <div class="tooltip" style="color:green">ENERGY<div class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_e_n_e_r_g_y.html" style="color:green">More details</a><i></i></div></div>
<b name="working2.datv" onclick='showPath("working2.dat","working2.datv","working2.datv","black")'>v</b><span style="display:none;" id="working2.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <div class="tooltip" style="color:green">VOLUME<div class="right">Calculate the volume of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_v_o_l_u_m_e.html" style="color:green">More details</a><i></i></div></div>
<span style="color:blue" class="comment"># slope is such that </span>
<div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the labels of the values that you would like to print to the file<i></i></div></div>=<b name="working2.date">e</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=energy2
<span style="color:blue" class="comment"># slope should be (alpha-1)=0.21</span>
<span style="display:none;" id="working2.dat">The PRINT action with label <b></b> calculates something</span><div class="tooltip" style="color:green">RESTRAINT<div class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/_r_e_s_t_r_a_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">AT<div class="right">the position of the restraint<i></i></div></div>=0.0 <div class="tooltip">ARG<div class="right">the values the harmonic restraint acts upon<i></i></div></div>=<b name="working2.date">e</b> <div class="tooltip">SLOPE<div class="right"> specifies that the restraint is linear and what the values of the force constants on each of the variables are<i></i></div></div>=0.21
</pre>
 {% endraw %} 

In other words, when forces are passed correctly the time series for the energies and volumes from the first and third of these calculations should be identical.  

To determine if PLUMED passes this test we calculate the difference between the time series that were observed in the first and third simulations described above.
We then divide this by the difference between the first and second time series.

An NPT version of this calculation is performed as well as an NVT calculation if the virial is passed to PLUMED.

# Trajectories
1. Input and output files for the unpeturbed calculation are available in this [zip archive](engvir1_master.zip)
2. Input and output files for the peturbed calculation are available in this [zip archive](engvir3_master.zip)

3. Input and output files for the peturbed calculation in which a PLUMED restraint is used to undo the effect of the changed MD parameters are available in this [zip archive](engvir2_master.zip)


# Results

The table below includes some of the results from the calculation.  The columns contain:

1. Time series for the energy and volume that were obtained from the simulation at $T$ K, $x_{md}$.
2. Time series for the energy and volume that were obtained from the simulation at $\alpha T$ K and in which PLUMED applied a restraint on the energy, $x_{pl}$.
3. The absolute value of the difference between the time series of energies and volumes that were obtained from the simulations running at $T$ K and $\alpha T$ K, $\vert x_{md}'-x_{md} \vert$.  No PLUMED restraints were applied in either of these simulations.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \vert x_{md}'-x_{md} \vert}$. 

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

| Original result | Result with PLUMED | Effect of peturbation | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18174.8262 11.6346 | -18174.8262 11.6346 | 0.0000 0.0000 | 0.0000 0.0000 | 
| -18171.8164 11.6346 | -18193.2852 11.6346 | 6.8633 0.0000 | 312.8059 0.0000 | 
| -18193.5371 11.6475 | -18236.7227 11.6321 | 21.6113 0.0054 | 199.8283 284.9140 | 
| -18164.5840 11.6475 | -18296.4609 11.6321 | 15.8789 0.0054 | 830.5166 284.9140 | 
| -18149.7246 11.6475 | -18345.1484 11.6321 | 16.4082 0.0054 | 1191.0130 284.9140 | 
| -18130.0332 11.6475 | -18377.2207 11.6321 | 15.2949 0.0054 | 1616.1410 284.9140 | 
| -18111.5430 11.6475 | -18390.9375 11.6321 | 14.9922 0.0054 | 1863.6008 284.9140 | 
| -18100.2949 11.6475 | -18391.4609 11.6321 | 17.2910 0.0054 | 1683.9150 284.9140 | 
| -18099.4668 11.6475 | -18386.7637 11.6321 | 22.1504 0.0054 | 1297.0285 284.9140 | 
| -18107.6953 11.6475 | -18383.2363 11.6321 | 27.5000 0.0054 | 1001.9673 284.9140 | 
| -18119.9062 11.6475 | -18383.5156 11.6321 | 30.4492 0.0054 | 865.7344 284.9140 | 
| -18130.4043 11.6475 | -18387.0371 11.6321 | 29.4395 0.0054 | 871.7309 284.9140 | 
| -18136.6445 11.6475 | -18392.8242 11.6321 | 26.1465 0.0054 | 979.7864 284.9140 | 
| -18141.3320 11.6475 | -18401.8340 11.6321 | 25.1699 0.0054 | 1034.9732 284.9140 | 
| -18150.4980 11.6475 | -18416.4160 11.6321 | 30.8398 0.0054 | 862.2546 284.9140 | 
| -18168.0293 11.6475 | -18437.0605 11.6321 | 42.5234 0.0054 | 632.6658 284.9140 | 
| -18191.0703 11.6475 | -18459.3730 11.6321 | 53.1973 0.0054 | 504.3544 284.9140 | 
| -18210.8359 11.6475 | -18475.1094 11.6321 | 53.7617 0.0054 | 491.5643 284.9140 | 
| -18218.2480 11.6475 | -18477.2988 11.6321 | 39.9277 0.0054 | 648.7991 284.9140 | 
| -18209.7969 11.6475 | -18465.1777 11.6321 | 15.7441 0.0054 | 1622.0692 284.9140 | 
