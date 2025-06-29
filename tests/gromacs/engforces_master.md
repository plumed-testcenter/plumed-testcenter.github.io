Check force on energy
---------------------

It is common practise to use the potential energy as a collective energy. Some MD codes thus pass the potential energy to PLUMED and
PLUMED can then apply forces on this collective variable.  We test that any forces that PLUMED applies on the potential energy are 
correctly passed back to the MD code by doing the following test.  We first run a short simulation at $T$ K with a timestep of $\tau$ ps.
During the course of this simulation we monitor the potential energy using the following PLUMED input:

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
<b name="working1.datv" onclick='showPath("working1.dat","working1.datv","working1.datv","black")'>v</b><span style="display:none;" id="working1.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <span class="plumedtooltip" style="color:green">VOLUME<span class="right">Calculate the volume the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/VOLUME" style="color:green">More details</a><i></i></span></span>
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working1.date">e</b>,<b name="working1.datv">v</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=energy1
</pre></div>

 {% endraw %} 

We then run a second simulation (starting from identical conditions) at a temperature of $T\alpha$ and with a timestep of $\tau/\sqrt(\alpha)$.
The thermostat and barostat relaxation times are similarly divided by $\sqrt(\alpha)$.  In the tests that are run on this website we set $\sqrt(\alpha)=1.1$.
The PLUMED file above is used when this test is run but a different time series of energy values is recorded as the MD parameters in this second simulation are 
different.

If PLUMED is working correctly we should be able to recapture the time series of energy values for the first simulation by running an MD simulation with the modified 
parameters that were used in the second simulation and the following PLUMED input file:

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
<b name="working2.date" onclick='showPath("working2.dat","working2.date","working2.date","black")'>e</b><span style="display:none;" id="working2.date">The ENERGY action with label <b>e</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">e</td><td width="5%"><font color="black">scalar</font></td><td>the internal energy</td></tr></table></span>: <span class="plumedtooltip" style="color:green">ENERGY<span class="right">Calculate the total potential energy of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/ENERGY" style="color:green">More details</a><i></i></span></span>
<b name="working2.datv" onclick='showPath("working2.dat","working2.datv","working2.datv","black")'>v</b><span style="display:none;" id="working2.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <span class="plumedtooltip" style="color:green">VOLUME<span class="right">Calculate the volume the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/VOLUME" style="color:green">More details</a><i></i></span></span>
<span style="color:blue" class="comment"># slope is such that </span>
<span class="plumedtooltip" style="color:green">PRINT<span class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/PRINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ARG<span class="right">the labels of the values that you would like to print to the file<i></i></span></span>=<b name="working2.date">e</b> <span class="plumedtooltip">FILE<span class="right">the name of the file on which to output these quantities<i></i></span></span>=energy2
<span style="color:blue" class="comment"># slope should be (alpha-1)=0.21</span>
<span style="display:none;" id="working2.dat">The PRINT action with label <b></b> calculates something</span><span class="plumedtooltip" style="color:green">RESTRAINT<span class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/RESTRAINT" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">AT<span class="right">the position of the restraint<i></i></span></span>=0.0 <span class="plumedtooltip">ARG<span class="right">the values the harmonic restraint acts upon<i></i></span></span>=<b name="working2.date">e</b> <span class="plumedtooltip">SLOPE<span class="right"> specifies that the restraint is linear and what the values of the force constants on each of the variables are<i></i></span></span>=0.21
</pre></div>

 {% endraw %} 

In other words, when forces are passed correctly the time series for the energies and volumes from the first and third of these calculations should be identical.  

To determine if PLUMED passes this test we calculate the difference between the time series that were observed in the first and third simulations described above.
We then divide this by the difference between the first and second time series.

An NPT version of this calculation is performed as well as an NVT calculation if the virial is passed to PLUMED.

# Trajectories

 1. Input and output files for the unpeturbed calculation are available in this [zip archive](engforces1_master.zip)

 2. Input and output files for the peturbed calculation are available in this [zip archive](engforces3_master.zip)

 3. Input and output files for the peturbed calculation in which a PLUMED restraint is used to undo the effect of the changed MD parameters are available in this [zip archive](engforces2_master.zip)


# Results

| Original | With PLUMED | Effect of peturbation | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -18174.8223 11.6346 | -18174.8223 11.6346 | 0.0000 0.0000 | 0.0000 0.0000 | 
| -18171.8203 11.6346 | -18193.2852 11.6346 | 6.8730 0.0000 | 312.3047 0.0000 | 
| -18172.4551 11.6346 | -18237.1426 11.6346 | 14.8965 0.0000 | 434.2468 0.0000 | 
| -18166.1309 11.6346 | -18284.3086 11.6346 | 23.0117 0.0000 | 513.5546 0.0000 | 
| -18152.2344 11.6346 | -18321.9707 11.6346 | 29.7812 0.0000 | 569.9436 0.0000 | 
| -18133.7539 11.6346 | -18342.9297 11.6346 | 35.3047 0.0000 | 592.4873 0.0000 | 
| -18116.4453 11.6346 | -18347.8340 11.6346 | 40.8008 0.0000 | 567.1182 0.0000 | 
| -18106.2266 11.6346 | -18343.1582 11.6346 | 47.2402 0.0000 | 501.5463 0.0000 | 
| -18106.0996 11.6346 | -18336.9004 11.6346 | 54.2812 0.0000 | 425.1943 0.0000 | 
| -18114.6914 11.6346 | -18334.5020 11.6346 | 60.0352 0.0000 | 366.1364 0.0000 | 
| -18127.0195 11.6346 | -18337.0723 11.6346 | 62.2207 0.0000 | 337.5930 0.0000 | 
| -18137.4707 11.6346 | -18342.6875 11.6346 | 59.9336 0.0000 | 342.4070 0.0000 | 
| -18143.6621 11.6346 | -18349.4941 11.6346 | 55.5742 0.0000 | 370.3732 0.0000 | 
| -18148.3750 11.6346 | -18358.4102 11.6346 | 54.0723 0.0000 | 388.4342 0.0000 | 
| -18157.7051 11.6346 | -18372.2285 11.6346 | 59.8340 0.0000 | 358.5311 0.0000 | 
| -18175.4277 11.6346 | -18392.1836 11.6346 | 71.9121 0.0000 | 301.4177 0.0000 | 
| -18198.6035 11.6346 | -18414.3438 11.6346 | 82.9668 0.0000 | 260.0320 0.0000 | 
| -18218.3438 11.6346 | -18430.5879 11.6346 | 83.5879 0.0000 | 253.9173 0.0000 | 
| -18225.5859 11.6346 | -18433.6758 11.6346 | 69.4902 0.0000 | 299.4519 0.0000 | 
| -18216.9082 11.6346 | -18422.2285 11.6346 | 44.8164 0.0000 | 458.1365 0.0000 | 


The table below includes some of the results from the calculation.  The columns contain:

1. Time series for the energy and volume that were obtained from the simulation at $T$ K, $x_{md}$.
2. Time series for the energy and volume that were obtained from the simulation at $\alpha T$ K and in which PLUMED applied a restraint on the energy, $x_{pl}$.
3. The absolute value of the difference between the time series of energies and volumes that were obtained from the simulations running at $T$ K and $\alpha T$ K, $\vert x_{md}'-x_{md} \vert$.  No PLUMED restraints were applied in either of these simulations.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \vert x_{md}'-x_{md} \vert}$. 

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![engforces_master](./engforces_master.png)
