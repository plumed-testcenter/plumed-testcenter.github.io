Positions are passed correctly
------------------------------

PLUMED must receive the positions from an MD code in order to calculate CVs correctly.  
To test these positions are passed correctly to PLUMED we run a short trajectory and output the positions of all the atoms 
that are passed to PLUMED using the following command: 

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<div class="tooltip" style="color:green">DUMPATOMS<div class="right">Dump selected atoms on a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_u_m_p_a_t_o_m_s.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ATOMS<div class="right">the atom indices whose positions you would like to print out<i></i></div></div>=<div class="tooltip">@mdatoms<div class="right">refers to all the MD codes atoms but not PLUMEDs vatoms. <a href="https://www.plumed.org/doc-master/user-doc/html/_group.html">Click here</a> for more information. <i></i></div></div> <div class="tooltip">FILE<div class="right">file on which to output coordinates; extension is automatically detected<i></i></div></div>=plumed.xyz
</pre>
 {% endraw %} 

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](basic_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| -0.0663 -0.0663 -0.0663 | -0.0663 -0.0663 -0.0663 | 0.0010 0.0010 0.0010 | 0.0398 0.0398 0.0398 | 
| 0.0663 0.0663 0.0663 | 0.0663 0.0663 0.0663 | 0.0010 0.0010 0.0010 | 0.0398 0.0398 0.0398 | 
| -0.0663 -0.0663 -0.0663 | -0.0663 -0.0663 -0.0663 | 0.0010 0.0010 0.0010 | 0.0471 0.0408 0.0115 | 
| 0.0663 0.0663 0.0663 | 0.0663 0.0663 0.0663 | 0.0010 0.0010 0.0010 | 0.0471 0.0408 0.0115 | 
| -0.0663 -0.0663 -0.0663 | -0.0663 -0.0663 -0.0663 | 0.0010 0.0010 0.0010 | 0.0220 0.0192 0.0063 | 
| 0.0663 0.0663 0.0663 | 0.0663 0.0663 0.0663 | 0.0010 0.0010 0.0010 | 0.0220 0.0192 0.0063 | 
| -0.0664 -0.0664 -0.0664 | -0.0664 -0.0664 -0.0664 | 0.0010 0.0010 0.0010 | 0.0309 0.0023 0.0032 | 
| 0.0664 0.0664 0.0664 | 0.0664 0.0664 0.0664 | 0.0010 0.0010 0.0010 | 0.0309 0.0023 0.0032 | 
| -0.0665 -0.0664 -0.0665 | -0.0665 -0.0664 -0.0665 | 0.0010 0.0010 0.0010 | 0.0060 0.0137 0.0184 | 
| 0.0665 0.0664 0.0665 | 0.0665 0.0664 0.0665 | 0.0010 0.0010 0.0010 | 0.0060 0.0137 0.0184 | 
| -0.0666 -0.0665 -0.0666 | -0.0666 -0.0665 -0.0666 | 0.0010 0.0010 0.0010 | 0.0180 0.0096 0.0084 | 
| 0.0666 0.0665 0.0666 | 0.0666 0.0665 0.0666 | 0.0010 0.0010 0.0010 | 0.0180 0.0096 0.0084 | 
| -0.0667 -0.0667 -0.0667 | -0.0667 -0.0667 -0.0667 | 0.0010 0.0010 0.0010 | 0.0269 0.0210 0.0448 | 
| 0.0667 0.0667 0.0667 | 0.0667 0.0667 0.0667 | 0.0010 0.0010 0.0010 | 0.0269 0.0210 0.0448 | 
| -0.0669 -0.0668 -0.0669 | -0.0669 -0.0668 -0.0669 | 0.0010 0.0010 0.0010 | 0.0205 0.0005 0.0224 | 
| 0.0669 0.0668 0.0669 | 0.0669 0.0668 0.0669 | 0.0010 0.0010 0.0010 | 0.0205 0.0005 0.0224 | 
| -0.0670 -0.0669 -0.0670 | -0.0670 -0.0669 -0.0670 | 0.0010 0.0010 0.0010 | 0.0217 0.0494 0.0316 | 
| 0.0670 0.0669 0.0670 | 0.0670 0.0669 0.0670 | 0.0010 0.0010 0.0010 | 0.0217 0.0494 0.0316 | 
| -0.0672 -0.0671 -0.0672 | -0.0672 -0.0671 -0.0672 | 0.0010 0.0010 0.0010 | 0.0349 0.0126 0.0184 | 
| 0.0672 0.0671 0.0672 | 0.0672 0.0671 0.0672 | 0.0010 0.0010 0.0010 | 0.0349 0.0126 0.0184 | 


The table below includes some of the results from the calculation.  The columns contain:

1. The positions that were obtained from the MD code, $x_{md}$.
2. The positions that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.