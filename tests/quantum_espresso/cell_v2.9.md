Cell vectors are passed correctly
---------------------------------

PLUMED must receive the cell vectors from the MD code in order to calculate CVs correctly.  
To test these cell vectors are passed correctly to PLUMED we run a short trajectory and output the celll vectors 
that are passed to PLUMED using the following command: 

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_this_input_should_work.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed.stderr"><img src="https://img.shields.io/badge/v2.9-passing-green.svg" alt="tested onv2.9" /></a></td></tr><tr><td style="padding:1px"><a href="this_input_should_work.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="this_input_should_work.datc" onclick='showPath("this_input_should_work.dat","this_input_should_work.datc")'>c</b>: <div class="tooltip" style="color:green">CELL<div class="right">Calculate the components of the simulation cell <a href="https://www.plumed.org/doc-master/user-doc/html/_c_e_l_l.html" style="color:green">More details</a><i></i></div></div> 
<span style="display:none;" id="this_input_should_work.datc">The CELL action with label <b>c</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">c.ax</td><td>the ax component of the cell matrix</td></tr><tr><td width="5%">c.ay</td><td>the ay component of the cell matrix</td></tr><tr><td width="5%">c.az</td><td>the az component of the cell matrix</td></tr><tr><td width="5%">c.bx</td><td>the bx component of the cell matrix</td></tr><tr><td width="5%">c.by</td><td>the by component of the cell matrix</td></tr><tr><td width="5%">c.bz</td><td>the bz component of the cell matrix</td></tr><tr><td width="5%">c.cx</td><td>the cx component of the cell matrix</td></tr><tr><td width="5%">c.cy</td><td>the cy component of the cell matrix</td></tr><tr><td width="5%">c.cz</td><td>the cz component of the cell matrix</td></tr></table></span></pre>
 {% endraw %} 

# Trajectory
Input and output files for the test calculation are available in this [zip archive](basic_v2.9.zip) 


# Results

The table below contains the cell vectors that were output by the above command and the cell vectors 
that were output by the MD code.  If the PLUMED interface is working correctly these two sets of numbers should be identical.

| MD code output | PLUMED output | 
|:-------------|:--------------| 
|[-0.26935122  0.          0.26935122  0.          0.26935122  0.26935122
 -0.26935122  0.26935122  0.        ] | [-0.269351  0.        0.269351  0.        0.269351  0.269351 -0.269351
  0.269351  0.      ] | 
|[-2.69359677e-01 -7.91953245e-12  2.69359677e-01  4.25896867e-07
  2.69360103e-01  2.69360103e-01 -2.69359677e-01  2.69359677e-01
 -1.19261585e-10] | [-0.26936 -0.       0.26936  0.       0.26936  0.26936 -0.26936  0.26936
 -0.     ] | 
|[-2.69380815e-01  1.55443900e-10  2.69380815e-01  1.47972216e-06
  2.69382293e-01  2.69382295e-01 -2.69380820e-01  2.69380819e-01
 -5.35616294e-09] | [-2.69381e-01  0.00000e+00  2.69381e-01  1.00000e-06  2.69382e-01
  2.69382e-01 -2.69381e-01  2.69381e-01 -0.00000e+00] | 
|[-2.69414623e-01  6.64194235e-10  2.69414623e-01  3.13982280e-06
  2.69417758e-01  2.69417763e-01 -2.69414644e-01  2.69414639e-01
 -2.02519049e-08] | [-2.69415e-01  0.00000e+00  2.69415e-01  3.00000e-06  2.69418e-01
  2.69418e-01 -2.69415e-01  2.69415e-01 -0.00000e+00] | 
|[-2.69461082e-01  1.68023834e-09  2.69461083e-01  5.37381023e-06
  2.69466447e-01  2.69466458e-01 -2.69461133e-01  2.69461122e-01
 -4.92777100e-08] | [-2.69461e-01  0.00000e+00  2.69461e-01  5.00000e-06  2.69466e-01
  2.69466e-01 -2.69461e-01  2.69461e-01 -0.00000e+00] | 
|[-2.69520170e-01  3.35614598e-09  2.69520171e-01  8.13940019e-06
  2.69528292e-01  2.69528314e-01 -2.69520270e-01  2.69520249e-01
 -9.66219317e-08] | [-2.69520e-01  0.00000e+00  2.69520e-01  8.00000e-06  2.69528e-01
  2.69528e-01 -2.69520e-01  2.69520e-01 -0.00000e+00] | 
|[-2.69591854e-01  5.83169110e-09  2.69591855e-01  1.13851339e-05
  2.69603210e-01  2.69603246e-01 -2.69592026e-01  2.69591991e-01
 -1.66113049e-07] | [-2.69592e-01  0.00000e+00  2.69592e-01  1.10000e-05  2.69603e-01
  2.69603e-01 -2.69592e-01  2.69592e-01 -0.00000e+00] | 
|[-2.69676095e-01  9.23028471e-09  2.69676097e-01  1.50515282e-05
  2.69691104e-01  2.69691158e-01 -2.69676366e-01  2.69676314e-01
 -2.61128895e-07] | [-2.69676e-01  0.00000e+00  2.69676e-01  1.50000e-05  2.69691e-01
  2.69691e-01 -2.69676e-01  2.69676e-01 -0.00000e+00] | 
|[-2.69772848e-01  1.36570610e-08  2.69772850e-01  1.90721857e-05
  2.69791861e-01  2.69791936e-01 -2.69773246e-01  2.69773173e-01
 -3.84543420e-07] | [-2.69773e-01  0.00000e+00  2.69773e-01  1.90000e-05  2.69792e-01
  2.69792e-01 -2.69773e-01  2.69773e-01 -0.00000e+00] | 
|[-2.69882058e-01  1.91969930e-08  2.69882061e-01  2.33750935e-05
  2.69905355e-01  2.69905455e-01 -2.69882615e-01  2.69882518e-01
 -5.38675993e-07] | [-2.69882e-01  0.00000e+00  2.69882e-01  2.30000e-05  2.69905e-01
  2.69905e-01 -2.69883e-01  2.69883e-01 -1.00000e-06] | 
