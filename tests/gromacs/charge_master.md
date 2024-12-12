Charges are passed correctly
---------------------------

PLUMED must receive the charges from an MD code in order to calculate some CVs correctly.
To test that charges are passed correctly to PLUMED we run a short trajectory and output the charges of all the atoms that 
are passed to PLUMED using the following command: 

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<div class="tooltip" style="color:green">DUMPMASSCHARGE<div class="right">Dump masses and charges on a selected file. <a href="https://www.plumed.org/doc-master/user-doc/html/_d_u_m_p_m_a_s_s_c_h_a_r_g_e.html" style="color:green">More details</a><i></i></div></div> <div class="tooltip">FILE<div class="right">file on which to output charges and masses<i></i></div></div>=mq_plumed
</pre>
 {% endraw %} 

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](basic_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 0.0 | 0.0 | 0.001 | 0.0 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| -1.04844 | -1.048439979553223 | 0.001 | 0.002044677693824326 |
| 0.0 | 0.0 | 0.001 | 0.0 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| -1.04844 | -1.048439979553223 | 0.001 | 0.002044677693824326 |
| 0.0 | 0.0 | 0.001 | 0.0 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| -1.04844 | -1.048439979553223 | 0.001 | 0.002044677693824326 |
| 0.0 | 0.0 | 0.001 | 0.0 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| -1.04844 | -1.048439979553223 | 0.001 | 0.002044677693824326 |
| 0.0 | 0.0 | 0.001 | 0.0 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| 0.52422 | 0.5242199897766113 | 0.001 | 0.0010223388691166235 |
| -1.04844 | -1.048439979553223 | 0.001 | 0.002044677693824326 |


The table below includes some of the results from the calculation.  The columns contain:

1. The charges that were obtained from the MD code, $x_{md}$.
2. The charges that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$.
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![charge_master](./charge_master.png)
