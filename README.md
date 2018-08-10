<p align="center">
  <span style='font-size: 15pt'><strong>Author:</strong>  <a href="https://www.linkedin.com/in/liang-wei-liu/">Liu Liang Wei</a></span>
 
</p>
<h1>Table of contents</h1>

  * [Description](#desc)
  	* [Features in the urine data](#feature)
  	* [Source and References](#source)
  * [Eliminate-null](#null)
    * [Mathod1: fill null with 0](#zero)
    * [Mathod2: fill the null with the average of the feature](#aver)
    * [Mathod3: directly drop the null](#drop)
  * [Normalization](#nor)
  * [Visualization](#vis)
  	* [Exercises](#exercises)
  * [Machine Learning](#ml)
     * [Linear-Regression](#lr)
     * [Decision-Tree](#tree)
     * [k-nearest neighbors](#knn)

<h2 id="desc">Description</h2>

<h3 id="feature">Features in the urine data</h3>

This data frame contains the following columns: r, gravity, ph,osmo, cond,urea and calc
* r: 腎結石有無出現 | Indicator of the presence of calcium oxalate crystals.
* gravity: 尿液比重 |The specific gravity of the urine.
* ph: The pH reading of the urine.
* osmo: 滲透壓 | The osmolarity of the urine. Osmolarity is proportional to the concentration of molecules in solution. <strong>No.54 has no osmo value</strong>
* cond: The conductivity of the urine. Conductivity is proportional to the concentration of charged ions in solution. <br><strong>No.0 has no cond value</strong>
* urea: 血清脲濃度 | The urea concentration in millimoles per litre.
* calc: 鈣濃度 | The calcium concentration in millimoles per litre.
    
<h3 id="source">Source and References</h3>

The data were obtained from Andrews, D.F. and Herzberg, A.M. (1985) Data: A Collection of Problems from Many Fields for the Student and Research Worker. Springer-Verlag.<br>

<strong>Davison, A.C. and Hinkley, D.V. (1997) Bootstrap Methods and Their Application. Cambridge University Press.</strong>

<h2 id="null">Eliminate-null</h2>

<h3 id="zero">Mathod1: fill null with 0</h3>

<h3 id="aver">Mathod2: fill the null with the average of the feature</h3>

<h3 id="drop">Mathod3: directly drop the null</h3>

<h2 id="desc">Description</h2>
<h2 id="desc">Description</h2>
<h2 id="desc">Description</h2>
