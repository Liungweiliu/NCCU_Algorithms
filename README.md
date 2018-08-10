<p align="center">
  <span style='font-size: 15pt'><strong>Author:</strong>  <a href="https://www.linkedin.com/in/liang-wei-liu/">Liu Liang Wei</a></span>
 
</p>
<h1>Table of contents</h1>

  * [Description](#desc)
  	* [Features in the urine data](#feature)
  	* [Source and References](#source)
  * [Eliminate-null](#null)
    * [Method1: fill null with 0](#zero)
    * [Method2: fill the null with the average of the feature](#aver)
    * [Method3: directly drop the null](#drop)
    * [Comparision](#comp)
  * [Normalization](#nor)
  * [Visualization](#vis)
  	* [Interaction of all features](#interaction)
    * [Two features scatter](#scatter)
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
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/raw%20description.JPG" alt="Get started with Python for Research" title="Get started with Python for Research" />

<h3 id="zero">Method1: fill null with 0</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Method1%20fill%20null%20with%200.JPG" alt="Method1: fill null with 0" title="Method1: fill null with 0" />

<h3 id="aver">Method2: fill the null with the average of the feature</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Method2%20fill%20the%20null%20with%20the%20average%20of%20the%20feature.JPG" alt="Method2: fill the null with the average of the feature" title="Method2: fill the null with the average of the feature" />

<h3 id="drop">Method3: directly drop the null</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Method3%20directly%20drop%20the%20null.JPG" alt="Method3: directly drop the null" title="Method3: directly drop the null" />

<h3 id="comp">Three methods comparison</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Methods%20comparison.PNG" alt="Comparision" title="Three methods comparison" />

<h2 id="nor">Normalization</h2>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Normalization.PNG" alt="Normalization" title="Normalization" />

<h2 id="vis">Visualization</h2>
<h3 id="interaction">Interaction of all features</h3>
Correlation of calcium oxalate crystals with distribution of other features
<h3 id="calc">Correlation of calcium oxalate crystals with distribution of other features</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Correlation%20of%20calcium%20oxalate%20crystals%20with%20distribution%20of%20each%20feature.svg" alt="calc" title="Correlation of calcium oxalate crystals with distribution of other features"/>

<h3 id="grav">Correlation of Gravity with distribution of other features</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Correlation%20of%20Gravity%20with%20distribution%20of%20other%20features.svg" alt="calc" title="Correlation of calcium oxalate crystals with distribution of other features"/>
  
<h3 id="scatter">Two features scatter</h3>

<h3 id="gu">Gravity and Urea scatter</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Gravity%20and%20Urea%20scatter.svg" alt="gu" title="Gravity and Urea scatter"/>

<h3 id="uc">Urea and Calcium scatter</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Calcium%20and%20Urea%20scatter.svg" alt="uc" title="Urea and Calcium scatter"/>

<h3 id="oc">Osmo and calc scatter</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Calcium%20and%20Urea%20scatter.svg" alt="oc" title="Osmo and calc scatter"/>

<h3 id="upH">Urea and pH scatter</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Calcium%20and%20Urea%20scatter.svg" alt="upH" title="Urea and pH scatter"/>

<h2 id="ml">Machine Learning</h2>

<h3 id="lr">Linear-Regression</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Linear%20regression%20between%20gravity%20and%20urine.svg" alt="lr" title="Linear-Regression"/>

<h3 id="tree">Decision-Tree</h3>

<h3 id="knn">k-nearest neighbors</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/knn.svg" alt="knn" title="k-nearest neighbors"/>
