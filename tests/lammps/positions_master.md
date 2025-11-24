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
| 4.4000 5.8527 3.6786 | 4.4000 5.8527 3.6786 | 0.0050 0.0050 0.0050 | 0.0572 0.0381 0.0000 | 
| 4.5104 5.8235 3.5867 | 4.5104 5.8235 3.5867 | 0.0050 0.0050 0.0050 | 0.0954 0.0191 0.0572 | 
| 4.3815 5.9549 3.7440 | 4.3815 5.9549 3.7440 | 0.0050 0.0050 0.0050 | 0.0286 0.0477 0.1001 | 
| 4.5717 5.7348 3.6134 | 4.5717 5.7348 3.6134 | 0.0050 0.0050 0.0050 | 0.0858 0.0572 0.0811 | 
| 4.5723 5.9137 3.5670 | 4.5723 5.9137 3.5670 | 0.0050 0.0050 0.0050 | 0.0191 0.0572 0.0620 | 
| 4.4666 5.8095 3.4855 | 4.4666 5.8095 3.4855 | 0.0050 0.0050 0.0050 | 0.0763 0.0286 0.0381 | 
| 4.3282 5.7474 3.6919 | 4.3282 5.7474 3.6920 | 0.0050 0.0050 0.0050 | 0.0668 0.0572 0.0620 | 
| 4.2072 5.7455 3.7624 | 4.2072 5.7455 3.7624 | 0.0050 0.0050 0.0050 | 0.0572 0.0858 0.0381 | 
| 4.2200 5.7578 3.9122 | 4.2200 5.7578 3.9122 | 0.0050 0.0050 0.0050 | 0.1049 0.0191 0.0572 | 
| 4.1886 5.8623 3.9704 | 4.1886 5.8623 3.9704 | 0.0050 0.0050 0.0050 | 0.0286 0.0095 0.0381 | 
| 4.1251 5.6153 3.7418 | 4.1251 5.6153 3.7418 | 0.0050 0.0050 0.0050 | 0.0381 0.0763 0.0238 | 
| 4.0885 5.5946 3.5975 | 4.0885 5.5946 3.5975 | 0.0050 0.0050 0.0050 | 0.0191 0.0381 0.0048 | 
| 4.1483 5.4964 3.5112 | 4.1483 5.4964 3.5112 | 0.0050 0.0050 0.0050 | 0.0954 0.0477 0.0572 | 
| 3.9740 5.6610 3.5464 | 3.9740 5.6610 3.5464 | 0.0050 0.0050 0.0050 | 0.0572 0.0858 0.0572 | 
| 4.1021 5.4757 3.3808 | 4.1021 5.4757 3.3808 | 0.0050 0.0050 0.0050 | 0.0191 0.0954 0.0858 | 
| 3.9262 5.6392 3.4120 | 3.9262 5.6392 3.4120 | 0.0050 0.0050 0.0050 | 0.0000 0.0858 0.0763 | 
| 3.9923 5.5461 3.3271 | 3.9923 5.5461 3.3271 | 0.0050 0.0050 0.0050 | 0.0000 0.0381 0.1001 | 
| 3.9482 5.5229 3.1919 | 3.9482 5.5229 3.1919 | 0.0050 0.0050 0.0050 | 0.0763 0.0095 0.1001 | 
| 4.3606 5.6617 3.6527 | 4.3606 5.6617 3.6527 | 0.0050 0.0050 0.0050 | 0.0572 0.0572 0.0811 | 
| 4.1496 5.8312 3.7305 | 4.1496 5.8311 3.7305 | 0.0050 0.0050 0.0050 | 0.0191 0.1049 0.0572 | 


The table below includes some of the results from the calculation.  The columns contain:

1. The positions that were obtained from the MD code, $x_{md}$.
2. The positions that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.
