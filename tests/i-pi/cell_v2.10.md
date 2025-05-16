Cell vectors are passed correctly
---------------------------------

PLUMED must receive the cell vectors from the MD code in order to calculate CVs correctly.  
To test that cell vectors are passed correctly to PLUMED we run a short trajectory and output the cell vectors 
that are passed to PLUMED using the following command: 

{% raw %}
<div style="width: 100%; float:left">
<div style="width: 90%; float:left" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div style="width: 10%; float:left"><table><tr><td style="padding:1px"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></td></tr><tr><td style="padding:1px"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></td></tr></table></div></div>
<pre style="width=97%;">
<b name="working1.datc" onclick='showPath("working1.dat","working1.datc","working1.datc","black")'>c</b><span style="display:none;" id="working1.datc">The CELL action with label <b>c</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">c.ax</td><td width="5%"><font color="black">scalar</font></td><td>the ax component of the cell matrix</td></tr><tr><td width="5%">c.ay</td><td width="5%"><font color="black">scalar</font></td><td>the ay component of the cell matrix</td></tr><tr><td width="5%">c.az</td><td width="5%"><font color="black">scalar</font></td><td>the az component of the cell matrix</td></tr><tr><td width="5%">c.bx</td><td width="5%"><font color="black">scalar</font></td><td>the bx component of the cell matrix</td></tr><tr><td width="5%">c.by</td><td width="5%"><font color="black">scalar</font></td><td>the by component of the cell matrix</td></tr><tr><td width="5%">c.bz</td><td width="5%"><font color="black">scalar</font></td><td>the bz component of the cell matrix</td></tr><tr><td width="5%">c.cx</td><td width="5%"><font color="black">scalar</font></td><td>the cx component of the cell matrix</td></tr><tr><td width="5%">c.cy</td><td width="5%"><font color="black">scalar</font></td><td>the cy component of the cell matrix</td></tr><tr><td width="5%">c.cz</td><td width="5%"><font color="black">scalar</font></td><td>the cz component of the cell matrix</td></tr></table></span>: <span class="plumedtooltip" style="color:green">CELL<span class="right">Get the components of the simulation cell <a href="https://www.plumed.org/doc-master/user-doc/html/CELL" style="color:green">More details</a><i></i></span></span> 
</pre>
 {% endraw %} 

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](basic_v2.10.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| $\begin{array}{ccc} 1.7846 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7846 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7846 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0000 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0002 \\\\ 0.0000 & 0.0000 & -0.0007 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178556.1000 & 4.5000 & 0.5000 \\\\ 0.0000 & 178544.1000 & 22.3000 \\\\ 0.0000 & 0.0000 & 178531.2000 \end{array}$ | 
| $\begin{array}{ccc} 1.7845 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7845 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7845 \end{array}$ | $\begin{array}{ccc} 1.7845 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7845 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7845 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7842 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7842 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7842 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0000 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0002 \\\\ 0.0000 & 0.0000 & -0.0007 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178516.9000 & 4.6000 & 1.7000 \\\\ 0.0000 & 178504.3000 & 23.6000 \\\\ 0.0000 & 0.0000 & 178491.3000 \end{array}$ | 
| $\begin{array}{ccc} 1.7838 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7838 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7838 \end{array}$ | $\begin{array}{ccc} 1.7838 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7838 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7838 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7833 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7833 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7833 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0000 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0003 \\\\ 0.0000 & 0.0000 & -0.0007 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178423.5000 & 4.8000 & 2.8000 \\\\ 0.0000 & 178410.3000 & 25.1000 \\\\ 0.0000 & 0.0000 & 178397.1000 \end{array}$ | 
| $\begin{array}{ccc} 1.7827 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7827 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7827 \end{array}$ | $\begin{array}{ccc} 1.7827 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7827 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7827 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7819 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7819 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7819 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0001 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0003 \\\\ 0.0000 & 0.0000 & -0.0006 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178277.7000 & 5.0000 & 4.0000 \\\\ 0.0000 & 178264.3000 & 26.7000 \\\\ 0.0000 & 0.0000 & 178250.6000 \end{array}$ | 
| $\begin{array}{ccc} 1.7810 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7810 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7810 \end{array}$ | $\begin{array}{ccc} 1.7810 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7810 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7810 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7800 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7800 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7800 \end{array}$ | $\begin{array}{ccc} 1.7800 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7800 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7800 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7788 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7788 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7788 \end{array}$ | $\begin{array}{ccc} 1.7788 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7788 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7788 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 


The table below includes some of the results from the calculation.  The columns contain:

1. The values for the cell vectors that were obtained from the MD code, $x_{md}$.
2. The values for the cell vectors that were obtained from PLUMED, $x_{pl}$.
3. The tolerances that were used when comparing these quantities, $\delta$. 
4. The values of $100\frac{\vert x_{md} - x_{pl}\vert }{ \delta }$.

If the PLUMED interface is working correctly the first two sets of numbers should be identical and the final column should be filled with zeros.

### Graphical representation (_beta_)
A visualization of the table above:  
![cell_v2.10](./cell_v2.10.png)
