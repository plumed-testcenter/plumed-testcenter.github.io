Masses are passed correctly
---------------------------

PLUMED must receive the masses from an MD code in order to calculate many CVs correctly.
To test that masses are passed correctly to PLUMED we run a short trajectory and output the masses of all the atoms that 
are passed to PLUMED using the following command: 

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
<span class="plumedtooltip" style="color:green">DUMPMASSCHARGE<span class="right">Dump masses and charges on a selected file. <a href="https://www.plumed.org/doc-master/user-doc/html/DUMPMASSCHARGE" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">FILE<span class="right">file on which to output charges and masses<i></i></span></span>=mq_plumed
</pre></div>

 {% endraw %} 

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](basic_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 12.011 | 12.011 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 15.999 | 15.999 | 0.01 | 0.0 |
| 1.008 | 1.008 | 0.01 | 0.0 |
| 1.008 | 1.008 | 0.01 | 0.0 |
| 1.008 | 1.008 | 0.01 | 0.0 |
| 14.007 | 14.007 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 15.999 | 15.999 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 12.011 | 12.011 | 0.01 | 0.0 |
| 15.999 | 15.999 | 0.01 | 0.0 |
| 1.008 | 1.008 | 0.01 | 0.0 |
| 1.008 | 1.008 | 0.01 | 0.0 |


The table below includes some of the results from the calculation.  The columns contain:

1. The masses that were obtained from the MD code, $x_{md}$.
2. The masses that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{\delta}$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.


### Graphical representation (_beta_)
A visualization of the table above:  
![mass_master](./mass_master.png)
