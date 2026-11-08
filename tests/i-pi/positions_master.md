Positions are passed correctly
------------------------------

PLUMED must receive the positions from an MD code in order to calculate CVs correctly.  
To test these positions are passed correctly to PLUMED we run a short trajectory and output the positions of all the atoms 
that are passed to PLUMED using the following command: 

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
<span class="plumedtooltip" style="color:green">DUMPATOMS<span class="right">Dump selected atoms on a file. <a href="https://www.plumed.org/doc-master/user-doc/html/DUMPATOMS" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ATOMS<span class="right">the atom indices whose positions you would like to print out<i></i></span></span>=<span class="plumedtooltip">@mdatoms<span class="right">refers to all the MD codes atoms but not PLUMEDs vatoms. <a href="https://www.plumed.org/doc-master/user-doc/html/specifying_atoms">Click here</a> for more information. <i></i></span></span> <span class="plumedtooltip">FILE<span class="right">file on which to output coordinates; extension is automatically detected<i></i></span></span>=plumed.xyz
</pre></div>

 {% endraw %} 

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](basic_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 0.2140 0.2847 0.2704 | 0.2140 0.2847 0.2704 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| -0.0365 0.3711 0.4730 | -0.0365 0.3711 0.4730 | 0.0010 0.0010 0.0010 | 0.0302 0.0000 0.0000 | 
| -0.1738 0.1497 -0.1158 | -0.1738 0.1497 -0.1158 | 0.0010 0.0010 0.0010 | 0.0000 0.0015 0.0000 | 
| -0.1217 -0.1865 0.0202 | -0.1217 -0.1865 0.0202 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0101 | 
| -0.2651 -0.4901 0.5564 | -0.2651 -0.4901 0.5564 | 0.0010 0.0010 0.0010 | 0.0030 0.0030 0.0000 | 
| -0.4733 -0.4491 0.8607 | -0.4733 -0.4491 0.8607 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 0.2531 0.3479 -0.0373 | 0.2531 0.3479 -0.0373 | 0.0010 0.0010 0.0010 | 0.0030 0.0000 0.0101 | 
| 0.8986 0.0902 0.7634 | 0.8986 0.0902 0.7634 | 0.0010 0.0010 0.0010 | 0.0060 0.0097 0.0000 | 
| -0.3242 -0.0259 0.6101 | -0.3242 -0.0259 0.6101 | 0.0010 0.0010 0.0010 | 0.0030 0.0300 0.0000 | 
| -0.4032 0.1957 1.4358 | -0.4032 0.1957 1.4358 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.1907 | 
| -0.0570 0.3496 1.8918 | -0.0570 0.3496 1.8918 | 0.0010 0.0010 0.0010 | 0.0101 0.0000 0.1073 | 
| 0.2147 0.6595 1.6085 | 0.2147 0.6595 1.6085 | 0.0010 0.0010 0.0010 | 0.0000 0.0060 0.3099 | 
| -0.3639 0.0943 0.2945 | -0.3639 0.0943 0.2945 | 0.0010 0.0010 0.0010 | 0.0000 0.0402 0.0000 | 
| 0.5568 0.8450 0.1085 | 0.5568 0.8450 0.1085 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0000 | 
| 0.7377 1.3563 0.6784 | 0.7377 1.3563 0.6784 | 0.0010 0.0010 0.0010 | 0.0060 0.1073 0.0000 | 
| 0.7683 0.7698 0.6266 | 0.7683 0.7698 0.6266 | 0.0010 0.0010 0.0010 | 0.0000 0.0060 0.0060 | 
| 0.7533 0.4442 1.2598 | 0.7533 0.4442 1.2598 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.5007 | 
| -0.1769 0.8971 1.2285 | -0.1769 0.8971 1.2286 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.3099 | 
| 0.3582 1.3107 0.9772 | 0.3582 1.3107 0.9772 | 0.0010 0.0010 0.0010 | 0.0000 0.2980 0.0060 | 
| 0.5294 0.1529 0.3884 | 0.5294 0.1529 0.3884 | 0.0010 0.0010 0.0010 | 0.0000 0.0015 0.0000 | 


The table below includes some of the results from the calculation.  The columns contain:

1. The positions that were obtained from the MD code, $x_{md}$.
2. The positions that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.
