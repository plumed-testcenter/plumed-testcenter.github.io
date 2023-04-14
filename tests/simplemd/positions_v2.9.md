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
Input and output files for the test calculation are available in this [zip archive](basic_v2.9.zip) 


# Results

The table below contains some of the positions that were output by the above command and the positions of the corresponding atoms 
that were output by the MD code.  If the PLUMED interface is working correctly these two sets of numbers should be identical.

| MD code output | PLUMED output | 
|:-------------|:--------------| 
|[-0.0076574 -0.0010929  0.0023979] | [-0.0077 -0.0011  0.0024] | 
|[ 0.8557258 -0.0025043  0.8457699] | [ 0.8557 -0.0025  0.8458] | 
|[0.8342526 0.8414696 0.0095137] | [0.8343 0.8415 0.0095] | 
|[0.0112641 0.85465   0.826328 ] | [0.0113 0.8546 0.8263] | 
|[1.3384999e-03 1.0581000e-02 1.6663154e+00] | [1.3000e-03 1.0600e-02 1.6663e+00] | 
|[0.8470251 0.008509  2.512583 ] | [0.847  0.0085 2.5126] | 
|[0.8432896 0.841699  1.6767421] | [0.8433 0.8417 1.6767] | 
|[-0.0028364  0.8351368  2.524965 ] | [-0.0028  0.8351  2.525 ] | 
|[-2.2737101e-02  3.2897000e-03  3.3570628e+00] | [-2.2700e-02  3.3000e-03  3.3571e+00] | 
|[8.242667e-01 3.906100e-03 4.202367e+00] | [8.2430e-01 3.9000e-03 4.2024e+00] | 
|[0.8485212 0.8478189 3.3577125] | [0.8485 0.8478 3.3577] | 
|[-0.0075146  0.8469977  4.1987953] | [-0.0075  0.847   4.1988] | 
|[0.0101511 1.6700466 0.005583 ] | [0.0102 1.67   0.0056] | 
|[0.8249403 1.6854086 0.8336605] | [0.8249 1.6854 0.8337] | 
|[ 0.8441532  2.520705  -0.0094557] | [ 0.8442  2.5207 -0.0095] | 
|[0.0071295 2.519402  0.8321947] | [0.0071 2.5194 0.8322] | 
|[-0.0068901  1.67869    1.6982747] | [-0.0069  1.6787  1.6983] | 
|[0.8159643 1.6637313 2.5119433] | [0.816  1.6637 2.5119] | 
|[0.8409213 2.5214894 1.7020907] | [0.8409 2.5215 1.7021] | 
|[0.0190094 2.5364895 2.5262122] | [0.019  2.5365 2.5262] | 
