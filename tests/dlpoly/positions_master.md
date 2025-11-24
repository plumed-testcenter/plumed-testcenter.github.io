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
| -0.8033 -0.5290 0.6226 | -0.8033 -0.5290 0.6226 | 0.1000 0.1000 0.1000 | 0.0002 0.0002 0.0004 | 
| 0.7510 -0.2002 -0.4919 | 0.7510 -0.2002 -0.4919 | 0.1000 0.1000 0.1000 | 0.0003 0.0003 0.0004 | 
| -1.0116 0.9967 0.9860 | -1.0116 0.9967 0.9860 | 0.1000 0.1000 0.1000 | 0.0004 0.0001 0.0002 | 
| -0.7555 -0.7734 -0.7414 | -0.7555 -0.7734 -0.7414 | 0.1000 0.1000 0.1000 | 0.0001 0.0003 0.0002 | 
| -0.7263 -0.9806 -0.5037 | -0.7263 -0.9806 -0.5037 | 0.1000 0.1000 0.1000 | 0.0004 0.0002 0.0002 | 
| 0.0425 -0.6642 -0.2219 | 0.0425 -0.6642 -0.2219 | 0.1000 0.1000 0.1000 | 0.0004 0.0002 0.0001 | 
| -0.5235 1.0074 -0.9848 | -0.5235 1.0074 -0.9848 | 0.1000 0.1000 0.1000 | 0.0001 0.0005 0.0004 | 
| -0.1968 -0.7469 -0.7341 | -0.1968 -0.7469 -0.7341 | 0.1000 0.1000 0.1000 | 0.0001 0.0001 0.0004 | 
| 0.0088 -0.7528 0.6822 | 0.0088 -0.7528 0.6822 | 0.1000 0.1000 0.1000 | 0.0003 0.0001 0.0004 | 
| 0.0076 -0.2703 -0.2816 | 0.0076 -0.2703 -0.2816 | 0.1000 0.1000 0.1000 | 0.0000 0.0003 0.0003 | 
| 0.0206 0.9889 -0.9390 | 0.0206 0.9889 -0.9390 | 0.1000 0.1000 0.1000 | 0.0001 0.0002 0.0005 | 
| 0.2967 -0.6868 -0.7619 | 0.2967 -0.6868 -0.7619 | 0.1000 0.1000 0.1000 | 0.0003 0.0002 0.0000 | 
| 0.7150 -0.4035 0.4290 | 0.7150 -0.4035 0.4290 | 0.1000 0.1000 0.1000 | 0.0002 0.0003 0.0000 | 
| 0.7774 -0.7085 -0.5544 | 0.7774 -0.7085 -0.5544 | 0.1000 0.1000 0.1000 | 0.0002 0.0004 0.0004 | 
| 0.4690 0.9921 1.0023 | 0.4690 0.9921 1.0023 | 0.1000 0.1000 0.1000 | 0.0003 0.0001 0.0001 | 
| 0.7345 -0.7948 -0.8309 | 0.7345 -0.7948 -0.8309 | 0.1000 0.1000 0.1000 | 0.0002 0.0002 0.0003 | 
| 0.9562 -0.7797 0.4659 | 0.9562 -0.7797 0.4659 | 0.1000 0.1000 0.1000 | 0.0002 0.0002 0.0005 | 
| -0.9618 -0.1272 -0.2316 | -0.9618 -0.1272 -0.2316 | 0.1000 0.1000 0.1000 | 0.0003 0.0000 0.0004 | 
| 0.9880 -0.4652 -0.9631 | 0.9880 -0.4652 -0.9631 | 0.1000 0.1000 0.1000 | 0.0003 0.0004 0.0004 | 
| -0.7527 -0.2828 -0.7245 | -0.7527 -0.2828 -0.7245 | 0.1000 0.1000 0.1000 | 0.0004 0.0004 0.0005 | 


The table below includes some of the results from the calculation.  The columns contain:

1. The positions that were obtained from the MD code, $x_{md}$.
2. The positions that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.
