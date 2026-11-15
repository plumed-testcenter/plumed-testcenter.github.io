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
| 0.0072 0.0026 -0.0010 | 0.0072 0.0026 -0.0010 | 0.0010 0.0010 0.0010 | 0.0100 0.0100 0.0200 | 
| 0.8356 0.0057 0.8278 | 0.8356 0.0057 0.8278 | 0.0010 0.0010 0.0010 | 0.0417 0.0200 0.0358 | 
| 0.8414 0.8356 -0.0095 | 0.8414 0.8356 -0.0095 | 0.0010 0.0010 0.0010 | 0.0060 0.0358 0.0400 | 
| -0.0003 0.8353 0.8424 | -0.0003 0.8353 0.8424 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0119 | 
| -0.0031 0.0007 1.6798 | -0.0031 0.0007 1.6798 | 0.0010 0.0010 0.0010 | 0.0100 0.0100 0.0238 | 
| 0.8298 0.0052 2.5125 | 0.8298 0.0052 2.5125 | 0.0010 0.0010 0.0010 | 0.0417 0.0200 0.0238 | 
| 0.8435 0.8406 1.6770 | 0.8435 0.8406 1.6770 | 0.0010 0.0010 0.0010 | 0.0417 0.0298 0.0358 | 
| -0.0034 0.8372 2.5221 | -0.0034 0.8372 2.5221 | 0.0010 0.0010 0.0010 | 0.0400 0.0179 0.0000 | 
| -0.0027 -0.0072 3.3624 | -0.0027 -0.0072 3.3624 | 0.0010 0.0010 0.0010 | 0.0000 0.0100 0.0477 | 
| 0.8412 0.0023 4.2017 | 0.8412 0.0023 4.2017 | 0.0010 0.0010 0.0010 | 0.0417 0.0400 0.0477 | 
| 0.8460 0.8461 3.3635 | 0.8460 0.8461 3.3635 | 0.0010 0.0010 0.0010 | 0.0179 0.0536 0.0238 | 
| 0.0030 0.8505 4.1903 | 0.0030 0.8505 4.1903 | 0.0010 0.0010 0.0010 | 0.0400 0.0298 0.0477 | 
| -0.0038 1.6700 -0.0011 | -0.0038 1.6700 -0.0011 | 0.0010 0.0010 0.0010 | 0.0200 0.0358 0.0400 | 
| 0.8408 1.6771 0.8396 | 0.8408 1.6771 0.8396 | 0.0010 0.0010 0.0010 | 0.0119 0.0119 0.0119 | 
| 0.8424 2.5265 -0.0090 | 0.8424 2.5265 -0.0090 | 0.0010 0.0010 0.0010 | 0.0238 0.0477 0.0100 | 
| 0.0093 2.5196 0.8378 | 0.0093 2.5196 0.8378 | 0.0010 0.0010 0.0010 | 0.0199 0.0000 0.0179 | 
| 0.0031 1.6739 1.6721 | 0.0031 1.6739 1.6721 | 0.0010 0.0010 0.0010 | 0.0200 0.0238 0.0358 | 
| 0.8343 1.6824 2.5273 | 0.8343 1.6824 2.5273 | 0.0010 0.0010 0.0010 | 0.0298 0.0119 0.0477 | 
| 0.8464 2.5251 1.6906 | 0.8464 2.5251 1.6906 | 0.0010 0.0010 0.0010 | 0.0179 0.0000 0.0000 | 
| 0.0032 2.5284 2.5140 | 0.0032 2.5284 2.5140 | 0.0010 0.0010 0.0010 | 0.0200 0.0000 0.0000 | 


The table below includes some of the results from the calculation.  The columns contain:

1. The positions that were obtained from the MD code, $x_{md}$.
2. The positions that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.
