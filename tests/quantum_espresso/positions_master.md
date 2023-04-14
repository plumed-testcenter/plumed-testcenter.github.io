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
|[-0.0662604 -0.0662604 -0.0662604] | [-0.0663 -0.0663 -0.0663] | 
|[0.0662604 0.0662604 0.0662604] | [0.0663 0.0663 0.0663] | 
|[-0.06628953 -0.0662734  -0.06629011] | [-0.0663 -0.0663 -0.0663] | 
|[0.06628953 0.0662734  0.06629011] | [0.0663 0.0663 0.0663] | 
|[-0.06634078 -0.06630881 -0.06634194] | [-0.0663 -0.0663 -0.0663] | 
|[0.06634078 0.06630881 0.06634194] | [0.0663 0.0663 0.0663] | 
|[-0.06641331 -0.06636602 -0.06641503] | [-0.0664 -0.0664 -0.0664] | 
|[0.06641331 0.06636602 0.06641503] | [0.0664 0.0664 0.0664] | 
|[-0.06650594 -0.06644414 -0.06650819] | [-0.0665 -0.0664 -0.0665] | 
|[0.06650594 0.06644414 0.06650819] | [0.0665 0.0664 0.0665] | 
|[-0.06661718 -0.0665419  -0.06661992] | [-0.0666 -0.0665 -0.0666] | 
|[0.06661718 0.0665419  0.06661992] | [0.0666 0.0665 0.0666] | 
|[-0.06674527 -0.06665779 -0.06674845] | [-0.0667 -0.0667 -0.0667] | 
|[0.06674527 0.06665779 0.06674845] | [0.0667 0.0667 0.0667] | 
|[-0.0668882  -0.06678999 -0.06689177] | [-0.0669 -0.0668 -0.0669] | 
|[0.0668882  0.06678999 0.06689177] | [0.0669 0.0668 0.0669] | 
|[-0.06704378 -0.06693651 -0.06704768] | [-0.067  -0.0669 -0.067 ] | 
|[0.06704378 0.06693651 0.06704768] | [0.067  0.0669 0.067 ] | 
|[-0.06720965 -0.06709512 -0.06721381] | [-0.0672 -0.0671 -0.0672] | 
|[0.06720965 0.06709512 0.06721381] | [0.0672 0.0671 0.0672] | 
