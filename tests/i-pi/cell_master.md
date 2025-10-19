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
| $\begin{array}{ccc} 1.7845 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7845 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7845 \end{array}$ | $\begin{array}{ccc} 1.7845 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7845 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7845 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7842 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7842 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7842 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0000 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0002 \\\\ 0.0000 & 0.0000 & -0.0007 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178516.9000 & 4.6000 & 1.7000 \\\\ 0.0000 & 178504.3000 & 23.6000 \\\\ 0.0000 & 0.0000 & 178491.3000 \end{array}$ | 
| $\begin{array}{ccc} 1.7838 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7838 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7838 \end{array}$ | $\begin{array}{ccc} 1.7838 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7838 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7838 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7833 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7833 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7833 \end{array}$ | $\begin{array}{ccc} 1.7833 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7833 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7833 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7827 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7827 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7827 \end{array}$ | $\begin{array}{ccc} -0.0009 & -0.0000 & -0.0000 \\\\ 0.0000 & -0.0008 & 0.0003 \\\\ 0.0000 & 0.0000 & -0.0007 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178357.8000 & 4.9000 & 3.4000 \\\\ 0.0000 & 178344.5000 & 25.9000 \\\\ 0.0000 & 0.0000 & 178331.1000 \end{array}$ | 
| $\begin{array}{ccc} 1.7819 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7819 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7819 \end{array}$ | $\begin{array}{ccc} 1.7819 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7819 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7819 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
| $\begin{array}{ccc} 1.7810 & 0.0000 & 0.0000 \\\\ 0.0000 & 1.7810 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7810 \end{array}$ | $\begin{array}{ccc} 0.0000 & 17980934422139408491489351888706406573830713796555735139096899476155297353634210290187998704387760317102995317096683747396882178425893580517277356897502869217715427941742677397244074910750953362952213309994291833088915831758205204707479247230504346713124562279225543468889019008603167922619551045386240.0000 & 0.0000 \\\\ 0.0000 & 1.7810 & 0.0000 \\\\ 0.0000 & 0.0000 & 1.7810 \end{array}$ | $\begin{array}{ccc} 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \\\\ 0.0010 & 0.0010 & 0.0010 \end{array}$ | $\begin{array}{ccc} 178098.3000 & 1798093442213940852118210551719077877178242575961294952379790318289008591205986277700870174656671484805291622095593375597398309506846686638875451508054354639088273298519529328487843665280583212583977554156554904291385209314019870283824005340944185631344551392010754807047353567431151357388449753051785330688.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \\\\ 0.0000 & 0.0000 & 0.0000 \end{array}$ | 
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
