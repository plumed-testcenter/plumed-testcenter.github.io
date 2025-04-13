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
<b name="working1.date" onclick='showPath("working1.dat","working1.date","working1.date","black")'>e</b><span style="display:none;" id="working1.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <span class="plumedtooltip" style="color:green">ENERGY<span class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/ENERGY" style="color:green">More details</a><i></i></span></span>
<b name="working1.datv" onclick='showPath("working1.dat","working1.datv","working1.datv","black")'>v</b><span style="display:none;" id="working1.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <span class="plumedtooltip" style="color:green">VOLUME<span class="right">Calculate the volume the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/VOLUME" style="color:green">More details</a><i></i></span></span>
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working1.date">e</b>,<b name="working1.datv">v</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=energy1
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
<b name="working2.date" onclick='showPath("working2.dat","working2.date","working2.date","black")'>e</b><span style="display:none;" id="working2.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <span class="plumedtooltip" style="color:green">ENERGY<span class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/ENERGY" style="color:green">More details</a><i></i></span></span>
<b name="working2.datv" onclick='showPath("working2.dat","working2.datv","working2.datv","black")'>v</b><span style="display:none;" id="working2.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <span class="plumedtooltip" style="color:green">VOLUME<span class="right">Calculate the volume the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/VOLUME" style="color:green">More details</a><i></i></span></span>
<span style="color:blue" class="comment"># slope is such that </span>
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working2.date">e</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=energy2
<span style="color:blue" class="comment"># slope should be (alpha-1)=0.21</span>
<span style="display:none;" id="working2.dat">The PRINT action with label <b></b> calculates something</span><span class="plumedtooltip" style="color:green">RESTRAINT<span class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/RESTRAINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">AT<span class="right">the position of the restraint<i></i></span></span>=0.0 <span class="plumedtooltip">ARG<span class="right">the values the harmonic restraint acts upon<i></i></span></span>=<b name="working2.date">e</b> <span class="plumedtooltip">SLOPE<span class="right"> specifies that the restraint is linear and what the values of the force constants on each of the variables are<i></i></span></span>=0.21
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

| Original | With PLUMED | Effect of peturbation | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18174.8223 11.6346 | -18174.8223 11.6346 | 0.0000 0.0000 | 0.0000 0.0000 | 
| -18171.8203 11.6346 | -18193.2891 11.6346 | 6.8730 0.0000 | 312.3615 0.0000 | 
| -18193.4629 11.6475 | -18233.1250 11.6321 | 19.2012 0.0054 | 206.5609 284.9140 | 
| -18164.3223 11.6475 | -18284.5898 11.6321 | 8.3496 0.0054 | 1440.3976 284.9140 | 
| -18149.2266 11.6475 | -18322.3672 11.6321 | 2.0742 0.0054 | 8347.2724 284.9140 | 
| -18129.3164 11.6475 | -18343.5312 11.6321 | 6.1309 0.0054 | 3494.0423 284.9140 | 
| -18110.6387 11.6475 | -18348.6152 11.6321 | 12.5918 0.0054 | 1889.9333 284.9140 | 
| -18099.2969 11.6475 | -18344.0957 11.6321 | 14.6309 0.0054 | 1673.1678 284.9140 | 
| -18098.4453 11.6475 | -18337.9531 11.6321 | 11.9824 0.0054 | 1998.8264 284.9140 | 
| -18106.6934 11.6475 | -18335.6133 11.6321 | 6.9980 0.0054 | 3271.1973 284.9140 | 
| -18118.9492 11.6475 | -18338.2207 11.6321 | 3.1680 0.0054 | 6921.5161 284.9140 | 
| -18129.4902 11.6475 | -18343.8203 11.6321 | 2.7930 0.0054 | 7673.9154 284.9140 | 
| -18135.7363 11.6475 | -18350.6445 11.6321 | 4.8906 0.0054 | 4394.2891 284.9140 | 
| -18140.4414 11.6475 | -18359.5410 11.6321 | 5.1504 0.0054 | 4254.0384 284.9140 | 
| -18149.5996 11.6475 | -18373.4102 11.6321 | 0.5820 0.0054 | 38453.3722 284.9140 | 
| -18167.1035 11.6475 | -18393.3828 11.6321 | 11.9238 0.0054 | 1897.7068 284.9140 | 
| -18190.1484 11.6475 | -18415.5527 11.6321 | 22.1875 0.0054 | 1015.9067 284.9140 | 
| -18209.9023 11.6475 | -18431.7910 11.6321 | 22.4961 0.0054 | 986.3431 284.9140 | 
| -18217.3438 11.6475 | -18434.8418 11.6321 | 8.7656 0.0054 | 2481.2611 284.9140 | 
| -18208.9121 11.6475 | -18423.3555 11.6321 | 15.0918 0.0054 | 1420.9266 284.9140 | 


The table below includes some of the results from the calculation.  The columns contain:

1. Time series for the energy and volume that were obtained from the simulation at $T$ K, $x_{md}$.
2. Time series for the energy and volume that were obtained from the simulation at $\alpha T$ K and in which PLUMED applied a restraint on the energy, $x_{pl}$.
3. The absolute value of the difference between the time series of energies and volumes that were obtained from the simulations running at $T$ K and $\alpha T$ K, $\vert x_{md}'-x_{md} \vert$.  No PLUMED restraints were applied in either of these simulations.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \vert x_{md}'-x_{md} \vert}$. 

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![engvir_master](./engvir_master.png)
