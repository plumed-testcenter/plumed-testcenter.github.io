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
| -0.0039 -0.0009 0.0010 | -0.0039 -0.0009 0.0010 | 0.0010 0.0010 0.0010 | 0.0300 0.0300 0.0400 | 
| 0.8477 -0.0013 0.8430 | 0.8477 -0.0013 0.8430 | 0.0010 0.0010 0.0010 | 0.0298 0.0300 0.0060 | 
| 0.8367 0.8409 0.0046 | 0.8367 0.8409 0.0046 | 0.0010 0.0010 0.0010 | 0.0298 0.0358 0.0400 | 
| 0.0060 0.8476 0.8330 | 0.0060 0.8476 0.8330 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0179 | 
| 0.0005 0.0053 1.6733 | 0.0005 0.0053 1.6733 | 0.0010 0.0010 0.0010 | 0.0300 0.0200 0.0477 | 
| 0.8440 0.0041 2.5159 | 0.8440 0.0041 2.5159 | 0.0010 0.0010 0.0010 | 0.0298 0.0400 0.0238 | 
| 0.8413 0.8407 1.6782 | 0.8413 0.8407 1.6782 | 0.0010 0.0010 0.0010 | 0.0298 0.0060 0.0238 | 
| -0.0016 0.8379 2.5225 | -0.0016 0.8379 2.5225 | 0.0010 0.0010 0.0010 | 0.0300 0.0298 0.0238 | 
| -0.0114 0.0014 3.3583 | -0.0114 0.0014 3.3583 | 0.0010 0.0010 0.0010 | 0.0400 0.0200 0.0238 | 
| 0.8322 0.0012 4.2008 | 0.8322 0.0012 4.2008 | 0.0010 0.0010 0.0010 | 0.0119 0.0400 0.0477 | 
| 0.8446 0.8438 3.3586 | 0.8446 0.8438 3.3586 | 0.0010 0.0010 0.0010 | 0.0358 0.0000 0.0238 | 
| -0.0034 0.8430 4.1987 | -0.0034 0.8430 4.1987 | 0.0010 0.0010 0.0010 | 0.0300 0.0417 0.0477 | 
| 0.0058 1.6746 0.0031 | 0.0058 1.6746 0.0031 | 0.0010 0.0010 0.0010 | 0.0000 0.0119 0.0100 | 
| 0.8327 1.6827 0.8370 | 0.8327 1.6827 0.8370 | 0.0010 0.0010 0.0010 | 0.0238 0.0238 0.0417 | 
| 0.8415 2.5197 -0.0046 | 0.8415 2.5197 -0.0046 | 0.0010 0.0010 0.0010 | 0.0060 0.0000 0.0200 | 
| 0.0037 2.5197 0.8356 | 0.0037 2.5197 0.8356 | 0.0010 0.0010 0.0010 | 0.0100 0.0238 0.0298 | 
| -0.0035 1.6794 1.6888 | -0.0035 1.6794 1.6888 | 0.0010 0.0010 0.0010 | 0.0000 0.0000 0.0238 | 
| 0.8280 1.6711 2.5157 | 0.8280 1.6711 2.5157 | 0.0010 0.0010 0.0010 | 0.0000 0.0119 0.0477 | 
| 0.8406 2.5202 1.6915 | 0.8406 2.5202 1.6915 | 0.0010 0.0010 0.0010 | 0.0298 0.0000 0.0238 | 
| 0.0097 2.5279 2.5226 | 0.0097 2.5279 2.5226 | 0.0010 0.0010 0.0010 | 0.0400 0.0238 0.0238 | 


The table below includes some of the results from the calculation.  The columns contain:

1. The positions that were obtained from the MD code, $x_{md}$.
2. The positions that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.
