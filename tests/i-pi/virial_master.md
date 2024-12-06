Check virial contribution
-------------------------

If you are running simulations at constant pressure then the virial forces cause the cell parameters 
to change with time.  Any CVs calculated by PLUMED contribute to these virial forces and PLUMED must,
therefore, have a mechanism to pass virial forces back to the MD code. 

To debug this mechanism we run a constant pressure simulation at 1 bar using the MD code.  During this simulation
we use the following PLUMED input to monitor the cell volume:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.datv" onclick='showPath("working1.dat","working1.datv","working1.datv","black")'>v</b><span style="display:none;" id="working1.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <div class="tooltip" style="color:green">VOLUME<div class="right">Calculate the volume of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_v_o_l_u_m_e.html" style="color:green">More details</a><i></i></div></div>
<div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the labels of the values that you would like to print to the file<i></i></div></div>=<b name="working1.datv">v</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=volume
</pre>
 {% endraw %} 

We then run a second constant pressure MD simulation at a pressure of 1001 bar and the input above.

If the virial has been implemented correctly within PLUMED the following PLUMED restraint will apply a negative pressure of 1000bar, which should compensate the fact that the
second calculation was run at higher pressure.  We thus run a third MD calculation with the following input file:

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working2.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working2.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working2.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working2.datv" onclick='showPath("working2.dat","working2.datv","working2.datv","black")'>v</b><span style="display:none;" id="working2.datv">The VOLUME action with label <b>v</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">v</td><td width="5%"><font color="black">scalar</font></td><td>the volume of simulation box</td></tr></table></span>: <div class="tooltip" style="color:green">VOLUME<div class="right">Calculate the volume of the simulation box. <a href="https://www.plumed.org/doc-master/user-doc/html/_v_o_l_u_m_e.html" style="color:green">More details</a><i></i></div></div> 
<span style="color:blue" class="comment"># slope should be just 10 times the Avogadro constant:</span>
<div class="tooltip" style="color:green">RESTRAINT<div class="right">Adds harmonic and/or linear restraints on one or more variables. <a href="https://www.plumed.org/doc-master/user-doc/html/_r_e_s_t_r_a_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">AT<div class="right">the position of the restraint<i></i></div></div>=0.0 <div class="tooltip">ARG<div class="right">the values the harmonic restraint acts upon<i></i></div></div>=<b name="working2.datv">v</b> <div class="tooltip">SLOPE<div class="right"> specifies that the restraint is linear and what the values of the force constants on each of the variables are<i></i></div></div>=-60.2214129
<span style="display:none;" id="working2.dat">The RESTRAINT action with label <b></b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">.bias</td><td>the instantaneous value of the bias potential</td></tr><tr><td width="5%">.force2</td><td>the instantaneous value of the squared force due to this bias potential</td></tr></table></span><div class="tooltip" style="color:green">PRINT<div class="right">Print quantities to a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_p_r_i_n_t.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ARG<div class="right">the labels of the values that you would like to print to the file<i></i></div></div>=<b name="working2.datv">v</b> <div class="tooltip">FILE<div class="right">the name of the file on which to output these quantities<i></i></div></div>=volume2
</pre>
 {% endraw %} 

The time series for the volumes that are output by the files `volume` and `volume2` above should thus be close to identical. 

# Trajectories
1. Input and output files for the unpeturbed calculation are available in this [zip archive](virial1_master.zip)
2. Input and output files for the peturbed calculation are available in this [zip archive](virial3_master.zip)

3. Input and output files for the peturbed calculation in which a PLUMED restraint is used to undo the effect of the changed MD parameters are available in this [zip archive](virial2_master.zip)


# Results

The table below includes some of the results from the calculation.  The columns contain:

1. The time series for the volume that was obtained from the simulation in that was performed at 1 bar, $x_{md}$.
2. The time series for the volume that was obtained from the simulation that was performed at 1001 bar and in which PLUMED applied a restraint on the volume, $x_{pl}$.
3. The absolute value of the difference between the time series of volumes that were obtained from the simulations running at 1001 bar and 1 bar, $\vert x_{md}'-x_{md}\vert$.  No PLUMED restraints were applied in either of these simulations.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \vert x_{md}'-x_{md} \vert }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

| Original result | Result with PLUMED | Effect of peturbation | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 5.683947 | 5.681868 | 0.002079000000000164 | 100.0 |
| 5.682743 | 5.676523 | 0.008287000000000155 | 75.05731869192441 |
| 5.680166 | 5.665717 | 0.01855999999999991 | 77.85021551724141 |
| 5.676354 | 5.649664 | 0.03280499999999975 | 81.35954884926238 |
| 5.671285 | 5.630494 | 0.05089599999999983 | 80.14578748821243 |
| 5.665068 | 5.606382 | 0.07268199999999947 | 80.74351283674119 |
| 5.657502 | 5.579288 | 0.09797999999999973 | 79.8264952031029 |
| 5.649101 | 5.549844 | 0.12658799999999992 | 78.40948589123752 |
| 5.639401 | 5.517723 | 0.15826800000000052 | 76.88098668081973 |
| 5.628792 | 5.481508 | 0.19277299999999986 | 76.40281574701855 |
| 5.617623 | 5.443668 | 0.2298429999999998 | 75.68427143745969 |
| 5.605162 | 5.403656 | 0.26915699999999987 | 74.86559888838123 |
| 5.59127 | 5.361516 | 0.3103869999999995 | 74.0217857062313 |
| 5.575997 | 5.317483 | 0.35319400000000023 | 73.19320260253565 |
| 5.559915 | 5.27229 | 0.39726399999999984 | 72.40147609650015 |
| 5.543135 | 5.226231 | 0.4422510000000006 | 71.65704543347547 |
| 5.525593 | 5.177699 | 0.48778699999999997 | 71.32088391039535 |
| 5.507604 | 5.128961 | 0.5335339999999995 | 70.96886046624952 |
| 5.488983 | 5.080047 | 0.5791060000000003 | 70.61505147589551 |
| 5.469354 | 5.03081 | 0.6240860000000001 | 70.2698025592627 |
