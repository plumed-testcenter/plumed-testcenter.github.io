Cell vectors are passed correctly
---------------------------------

PLUMED must receive the cell vectors from the MD code in order to calculate CVs correctly.  
To test that cell vectors are passed correctly to PLUMED we run a short trajectory and output the cell vectors 
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
<b name="working1.datc" onclick='showPath("working1.dat","working1.datc","working1.datc","black")'>c</b><span style="display:none;" id="working1.datc">The CELL action with label <b>c</b> calculates the following quantities:<table  align="center" frame="void" width="95%" cellpadding="5%"><tr><td width="5%"><b> Quantity </b>  </td><td width="5%"><b> Type </b>  </td><td><b> Description </b> </td></tr><tr><td width="5%">c.ax</td><td width="5%"><font color="black">scalar</font></td><td>the ax component of the cell matrix</td></tr><tr><td width="5%">c.ay</td><td width="5%"><font color="black">scalar</font></td><td>the ay component of the cell matrix</td></tr><tr><td width="5%">c.az</td><td width="5%"><font color="black">scalar</font></td><td>the az component of the cell matrix</td></tr><tr><td width="5%">c.bx</td><td width="5%"><font color="black">scalar</font></td><td>the bx component of the cell matrix</td></tr><tr><td width="5%">c.by</td><td width="5%"><font color="black">scalar</font></td><td>the by component of the cell matrix</td></tr><tr><td width="5%">c.bz</td><td width="5%"><font color="black">scalar</font></td><td>the bz component of the cell matrix</td></tr><tr><td width="5%">c.cx</td><td width="5%"><font color="black">scalar</font></td><td>the cx component of the cell matrix</td></tr><tr><td width="5%">c.cy</td><td width="5%"><font color="black">scalar</font></td><td>the cy component of the cell matrix</td></tr><tr><td width="5%">c.cz</td><td width="5%"><font color="black">scalar</font></td><td>the cz component of the cell matrix</td></tr></table></span>: <span class="plumedtooltip" style="color:green">CELL<span class="right">Get the components of the simulation cell <a href="https://www.plumed.org/doc-master/user-doc/html/CELL" style="color:green">More details</a><i></i></span></span> 
</pre></div>

 {% endraw %} 

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](basic_master.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| $\begin{array}{ccc} 1.7846 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7846 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7846 \end{array}$ | $\begin{array}{ccc} 1.7846 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7846 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7846 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7845 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7845 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7845 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0000 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0002 \\\\ 0.0000 & 0.0000 & -0.0007 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178543.7000 & 4.6000 & 1.1000 \\\\ 0.0000 & 178531.4000 & 23.0000 \\\\ 0.0000 & 0.0000 & 178518.5000 \end{array}$ | 
| $\begin{array}{ccc} 1.7842 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7842 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7842 \end{array}$ | $\begin{array}{ccc} 1.7842 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7842 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7842 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7838 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7838 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7838 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0000 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0002 \\\\ 0.0000 & 0.0000 & -0.0007 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178476.8000 & 4.7000 & 2.2000 \\\\ 0.0000 & 178463.9000 & 24.4000 \\\\ 0.0000 & 0.0000 & 178450.9000 \end{array}$ | 
| $\begin{array}{ccc} 1.7833 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7833 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7833 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0000 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0003 \\\\ 0.0000 & 0.0000 & -0.0007 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178423.5000 & 4.8000 & 2.8000 \\\\ 0.0000 & 178410.3000 & 25.1000 \\\\ 0.0000 & 0.0000 & 178397.1000 \end{array}$ | 
| $\begin{array}{ccc} 1.7827 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7827 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7827 \end{array}$ | $\begin{array}{ccc} 1.7827 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7827 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7827 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7819 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7819 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7819 \end{array}$ | $\begin{array}{ccc} 1.7819 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7819 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7819 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7810 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7810 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7810 \end{array}$ | $\begin{array}{ccc} 0.0000 & -150825092096502678452166841087772145307500067531805973226065299346271954109028544461826042455117573066559581802557570722337185419360205607096874238445502658137565912192124281910192099463762076866444607798528232492877009457689206598216055783424.0000 & 0.0000 \\\\ 0.0000 & 1.7810 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7810 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178098.3000 & 15082509209650265629391301396388436483646957546200631982822434215826319258828095095524921285414277450621979173354558317704598997153731995456011413616228749118614157163854776875285862822868261434971887585925941303856184030127691090065848081416454144.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
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
![cell_master](./cell_master.png)
