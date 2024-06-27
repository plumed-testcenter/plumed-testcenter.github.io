Positions are passed correctly
------------------------------

PLUMED must receive the positions from an MD code in order to calculate CVs correctly.  
To test these positions are passed correctly to PLUMED we run a short trajectory and output the positions of all the atoms 
that are passed to PLUMED using the following command: 

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.9-passing-green.svg" alt="tested on2.9" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<div class="tooltip" style="color:green">DUMPATOMS<div class="right">Dump selected atoms on a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_u_m_p_a_t_o_m_s.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ATOMS<div class="right">the atom indices whose positions you would like to print out<i></i></div></div>=<div class="tooltip">@mdatoms<div class="right">refers to all the MD codes atoms but not PLUMEDs vatoms. <a href="https://www.plumed.org/doc-master/user-doc/html/_group.html">Click here</a> for more information. <i></i></div></div> <div class="tooltip">FILE<div class="right">file on which to output coordinates; extension is automatically detected<i></i></div></div>=plumed.xyz
</pre>
 {% endraw %} 

# Trajectory
Input and output files for the test calculation are available in this [zip archive](basic_master.zip)


# Results

The table below includes some of the results from the calculation.  The columns contain:

1. The positions that were obtained from the MD code, $x_{md}$.
2. The positions that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 0.1310 0.5550 1.6220 | 0.1310 0.5550 1.6220 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 0.0980 0.5970 1.7010 | 0.0980 0.5970 1.7010 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 0.0930 0.6050 1.5500 | 0.0930 0.6050 1.5500 | 0.0010 0.0010 0.0010 | 0.0007 0.0060 0.0000 | 
| 0.1234 0.5648 1.6227 | 0.1234 0.5648 1.6227 | 0.0010 0.0010 0.0010 | 0.4001 0.3994 0.2980 | 
| 1.6130 0.9900 0.9920 | 1.6130 0.9900 0.9920 | 0.0010 0.0010 0.0010 | 0.0119 0.0060 0.0000 | 
| 1.5990 0.9830 1.0860 | 1.5990 0.9830 1.0860 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 1.7000 1.0290 0.9830 | 1.7000 1.0290 0.9830 | 0.0010 0.0010 0.0010 | 0.0119 0.0119 0.0000 | 
| 1.6208 0.9934 1.0011 | 1.6208 0.9934 1.0011 | 0.0010 0.0010 0.0010 | 0.2027 0.3994 0.2027 | 
| 0.3770 0.7530 1.3170 | 0.3770 0.7530 1.3170 | 0.0010 0.0010 0.0010 | 0.0000 0.0060 0.0119 | 
| 0.3350 0.7870 1.3960 | 0.3350 0.7870 1.3960 | 0.0010 0.0010 0.0010 | 0.0030 0.0000 0.0119 | 
| 0.4440 0.6920 1.3490 | 0.4440 0.6920 1.3490 | 0.0010 0.0010 0.0010 | 0.0030 0.0000 0.0000 | 
| 0.3797 0.7501 1.3288 | 0.3797 0.7501 1.3288 | 0.0010 0.0010 0.0010 | 0.2980 0.0000 0.0954 | 
| 0.6670 2.0350 1.4470 | 0.6670 2.0350 1.4470 | 0.0010 0.0010 0.0010 | 0.0000 0.0238 0.0119 | 
| 0.6570 1.9410 1.4320 | 0.6570 1.9410 1.4320 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0119 | 
| 0.6110 2.0520 1.5230 | 0.6110 2.0520 1.5230 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 0.6600 2.0268 1.4535 | 0.6600 2.0268 1.4535 | 0.0010 0.0010 0.0010 | 0.0954 0.3815 0.2980 | 
| 1.8230 1.7170 1.0270 | 1.8230 1.7170 1.0270 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 1.8670 1.7540 1.1040 | 1.8670 1.7540 1.1040 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 1.7370 1.7590 1.0270 | 1.7370 1.7590 1.0270 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 1.8185 1.7254 1.0352 | 1.8185 1.7254 1.0352 | 0.0010 0.0010 0.0010 | 0.0954 0.2980 0.3934 | 
