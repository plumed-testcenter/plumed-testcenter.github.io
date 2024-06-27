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
| -26662.023624585858 | -26662.023625 | 0.005 | 0.00828287738841027 |
| -26699.917469979402 | -26699.91747 | 0.005 | 0.0004119647201150656 |
| -26796.52675940842 | -26796.526759 | 0.005 | 0.008168426575139165 |
| -26926.835460591774 | -26926.835461 | 0.005 | 0.008164497558027506 |
| -27059.024968245438 | -27059.024968 | 0.005 | 0.004908724804408848 |
| -27172.354569161704 | -27172.354569 | 0.005 | 0.003234090399928391 |
| -27260.43127840873 | -27260.431278 | 0.005 | 0.00817461113911122 |
| -27324.740523523782 | -27324.740524 | 0.005 | 0.009524374036118388 |
| -27366.086067459924 | -27366.086067 | 0.005 | 0.009198483894579113 |
| -27383.369707684946 | -27383.369708 | 0.005 | 0.006301052053458989 |
| -27380.907315660006 | -27380.907316 | 0.005 | 0.006799891707487404 |
| -27369.372707118553 | -27369.372707 | 0.005 | 0.002371089067310095 |
| -27358.74308979043 | -27358.74309 | 0.005 | 0.004191388143226504 |
| -27349.669820521023 | -27349.669821 | 0.005 | 0.009579525794833899 |
| -27334.89254522113 | -27334.892545 | 0.005 | 0.004422618076205254 |
| -27310.22381311449 | -27310.223813 | 0.005 | 0.002289816620759666 |
| -27283.815222861474 | -27283.815223 | 0.005 | 0.002770539140328765 |
| -27268.23766107641 | -27268.237661 | 0.005 | 0.0015282421372830868 |
| -27266.536671138427 | -27266.536671 | 0.005 | 0.0027685018721967936 |
| -27268.05989535067 | -27268.059895 | 0.005 | 0.007013441063463688 |
