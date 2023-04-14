Positions are passed correctly
------------------------------

PLUMED must receive the positions from an MD code in order to calculate CVs correctly.  
To test these positions are passed correctly to PLUMED we run a short trajectory and output the positions of all the atoms 
that are passed to PLUMED using the following command: 

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<div class="tooltip" style="color:green">DUMPATOMS<div class="right">Dump selected atoms on a file. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_u_m_p_a_t_o_m_s.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">ATOMS<div class="right">the atom indices whose positions you would like to print out<i></i></div></div>=<div class="tooltip">@mdatoms<div class="right">refers to all the MD codes atoms but not PLUMEDs vatoms. <a href="https://www.plumed.org/doc-master/user-doc/html/_group.html">Click here</a> for more information. <i></i></div></div> <div class="tooltip">PRECISION<div class="right">The number of digits in trajectory file<i></i></div></div>=4 <div class="tooltip">FILE<div class="right">file on which to output coordinates; extension is automatically detected<i></i></div></div>=plumed.xyz
</pre>
 {% endraw %} 

# Trajectory
Input and output files for the test calculation are available in this [zip archive](basic_master.zip) 


# Results

The table below contains some of the positions that were output by the above command and the positions of the corresponding atoms 
that were output by the MD code.  If the PLUMED interface is working correctly these two sets of numbers should be identical.

| MD code output | PLUMED output | 
|:-------------|:--------------| 
|[4.39999   5.8526797 3.67855  ] | [4.3991 5.853  3.6789] | 
|[4.5104    5.8235    3.5866902] | [4.5112 5.8228 3.5861] | 
|[4.3815203 5.9549303 3.744    ] | [4.3808 5.9561 3.7429] | 
|[4.5717096 5.7348    3.61343  ] | [4.5739 5.7356 3.6147] | 
|[4.57226   5.91366   3.5670102] | [4.5737 5.9129 3.5684] | 
|[4.46662   5.8095403 3.48554  ] | [4.4635 5.8058 3.4872] | 
|[4.32819   5.74743   3.6919498] | [4.3272 5.7473 3.6927] | 
|[4.20716 5.74549 3.76242] | [4.2067 5.7456 3.7641] | 
|[4.21998   5.75779   3.9121602] | [4.2201 5.7596 3.9125] | 
|[4.1886396 5.8622503 3.9703999] | [4.1888 5.861  3.9708] | 
|[4.12505   5.6153    3.7418098] | [4.1262 5.6139 3.7419] | 
|[4.08851   5.59464   3.5974603] | [4.0887 5.5946 3.5974] | 
|[4.14831   5.49637   3.5112202] | [4.1492 5.4964 3.5104] | 
|[3.9740002 5.6610003 3.5464401] | [3.9734 5.6613 3.5464] | 
|[4.10211   5.47571   3.3807597] | [4.1033 5.4759 3.38  ] | 
|[3.92618   5.6391897 3.4120202] | [3.927  5.6395 3.4121] | 
|[3.99233 5.54609 3.32713] | [3.9918 5.5455 3.3278] | 
|[3.9481602 5.5229197 3.19187  ] | [3.9477 5.5228 3.1918] | 
|[4.36063 5.66169 3.65274] | [4.3585 5.6591 3.6584] | 
|[4.14962 5.83114 3.73054] | [4.1505 5.8317 3.7309] | 
