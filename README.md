<p align="center">
  <span style='font-size: 15pt'><strong>Author:</strong>  <a href="https://www.linkedin.com/in/liang-wei-liu/">Liu Liang Wei</a></span>
</p>
<h1 id="intro">Introduction</h1>
<p align="center">This repository based on the NCCU Algorithms course final project in 2018 spring.<br> </p>

  The following analysis implemented **pandas** on solving dataframe, **numpy** for array, **matplotlib** for vistualization, **sklearn** in machine learning analysis. These packages are friendly for beginning **Python** users and supported by huge social groups. It's worth learning these useful packages.<br><br>
Generally, clinical urine tests contain **6** target parameters, which are **Color**, **Smell**, **Ions and trace metals**, **Proteins and enzymes**, **Blood cells** and **Drugs**. Each sort of urine testing parameter has their significant influence on the kidney-related disease. In the dataset, it provides urine test data for **Calcium oxalate crystals**, the most common type of kidney stones.<br><br>
  The task of this data analysis is to find out useful information between the features and understand the meaning in the real case. Once we can use these feature for supporting medical treatment, healthcare professional can release the pressure and decrease their works. What’s more, patients can have a better quality of medical treatment. As the result, **it’s meaningful to mining and analysis the relation between these features and the presence of calcium oxalate crystals**.<br> 

<h1>Table of contents</h1>

  * [Description](#desc)
  	* [Features in the urine data](#feature)
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
  * [Summary](#sum)
  * [Source and References](#source)

<h2 id="desc">Description</h2>

<h3 id="feature">Features in the urine data</h3>

This data frame contains the following columns: r, gravity, ph,osmo, cond,urea and calc
* r: 腎結石有無出現 | Indicator of the presence of calcium oxalate crystals.
* gravity: 尿液比重 |The specific gravity of the urine.
* ph: The pH reading of the urine.
* osmo: 滲透壓 | The osmolarity of the urine. Osmolarity is proportional to the concentration of molecules in solution. <br><strong>No.54 has no osmo value</strong>
* cond: The conductivity of the urine. Conductivity is proportional to the concentration of charged ions in solution. <br><strong>No.0 has no cond value</strong>
* urea: 血清脲濃度 | The urea concentration in millimoles per litre.
* calc: 鈣濃度 | The calcium concentration in millimoles per litre.

<h2 id="null">Eliminate-null</h2>
Two missing values occur at the column of the conductivity of the urine of No.0 sample and the column of osmolarity of the urine of No.54 sample.<br>

<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/raw%20description.JPG" alt="Get started with Python for Research" title="Get started with Python for Research" /><br>

There are **three** common methods, **replacing with zero**, **replacing with average** and **removing them**, for eliminating the negative influence of missing.<br>

<h3 id="zero">Method1: fill null with 0</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Method1%20fill%20null%20with%200.JPG" alt="Method1: fill null with 0" title="Method1: fill null with 0" />

<h3 id="aver">Method2: fill the null with the average of the feature</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Method2%20fill%20the%20null%20with%20the%20average%20of%20the%20feature.JPG" alt="Method2: fill the null with the average of the feature" title="Method2: fill the null with the average of the feature" />

<h3 id="drop">Method3: directly drop the null</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Method3%20directly%20drop%20the%20null.JPG" alt="Method3: directly drop the null" title="Method3: directly drop the null" />

<h3 id="comp">Three methods comparison</h3>

The comparison indicates that both of **replacing average method** and **dropping missing value** are rather **stable in mean and standard deviation**. These two methods can represent the similar distribution of original data. As the result, the following analysis will be based on the drop missing value method.<br>

<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Methods%20comparison.PNG" alt="Comparision" title="Three methods comparison" />

<h2 id="nor">Normalization</h2>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/image/Normalization.PNG" alt="Normalization" title="Normalization" />

<h2 id="vis">Visualization</h2>
<h2 id="interaction">Interaction of all features</h2>

<h3 id="calc">Correlation of calcium oxalate crystals with distribution of other features</h3>

In order to understand the insight of each column, I draw the distribution of the relationship of the presence of calcium oxalate crystals and each feature of urine test with matplotlib package. **It’s clear that most sample without calcium oxalate crystals has apparently low calcium concentration per liter in the 2-3 scatter**.<br>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Correlation%20of%20calcium%20oxalate%20crystals%20with%20distribution%20of%20each%20feature.svg" alt="calc" title="Correlation of calcium oxalate crystals with distribution of other features"/>

<h3 id="grav">Correlation of Gravity with distribution of other features</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Correlation%20of%20Gravity%20with%20distribution%20of%20other%20features.svg" alt="calc" title="Correlation of calcium oxalate crystals with distribution of other features"/>
  
<h2 id="scatter">Two features scatter</h2>

<h3 id="gu">Gravity and Urea scatter</h3>

**The specific gravity of the urine fluctuates along with the value of urea concentration**, in the scatter of specific gravity of the urine and the urea concentration. Besides, people who are both low in gravity and in urea concentration have less sample with calcium oxalate crystals. Also, this scatters below seems that it can be converted to a linear function.<br>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Gravity%20and%20Urea%20scatter.svg" alt="gu" title="Gravity and Urea scatter"/>

<h3 id="uc">Urea and Calcium scatter</h3>

From the scatter of urea concentration per liter and calcium concentration per liter, most sample without calcium oxalate crystals has apparently low calcium concentration per liter. What’s more, the sample with calcium oxalate crystals has rather higher urea concentration. We can assume that **higher calcium concentration and higher urea concentration** are **warning of calcium oxalate crystals**.<br>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Calcium%20and%20Urea%20scatter.svg" alt="uc" title="Urea and Calcium scatter"/>

<h3 id="oc">Osmo and calc scatter</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Calcium%20and%20Urea%20scatter.svg" alt="oc" title="Osmo and calc scatter"/>

<h3 id="upH">Urea and pH scatter</h3>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Calcium%20and%20Urea%20scatter.svg" alt="upH" title="Urea and pH scatter"/>

<h2 id="ml">Machine Learning</h2>

<h3 id="lr">Linear-Regression</h3>
It looks interesting that this two feature have the linear tendency. In order to check the relation between these two features, I implement linear regression on gravity and urea concentration through the scikit-learn application.<br>
<img src="https://github.com/Liungweiliu/NCCU_Algorithms/blob/master/svg/Linear%20regression%20between%20gravity%20and%20urine.svg" alt="lr" title="Linear-Regression"/>

<strong>Examine the effectivity of linear regression model</strong><br>

Though the image looks like a linear tendency, it’s not as simple as what I expect. This linear regression does not effectively represent these two features because of the high **mean square error** and low **r square score**, 5475.17294581 and 0.678114364866. After normalizing features, scores even become worse, 85623.0185121 and -4.09492049532. As the definition of MSE, the lower the score is, the better efficiency it’s. The r square is right on the contrary. It’s obvious that the linear regression is not proper to represent these two features, the value of gravity concentration and of urine concentration.

<strong>Possible reasons for this fail</strong><br>
The lack of data and the limitation of linear regression may be the main reason. It needs more training data for judging whether the distribution is not in linear. We can ensure merely that this urine testing data is not suitable for linear regression.
<h3 id="tree">Decision-Tree</h3>

Decision Trees are a **non-parametric supervised learning method** used for **classification and regression**. Through **scikit-learn**, we can predict the value of a target variable inferred from multiple features. In this case, training data contains **6 features**, **the gravity of the urine, the pH reading of the urine, the osmolarity of the urine, the conductivity of the urine, the urea concentration and the calcium concentration**. What’s more important, the **target variable is the presence of calcium oxalate crystals**, a common type of kidney stone.

<strong>Cross-validation and normalization</strong>
I divide the training and testing feature and target variable in cross-validation. It can decrease the negative effect of overfitting in the calculation. Out of my expectation, the accuracy is pretty low. I have changed the portion of training and testing data for 10 times in this and following examines. The average accuracy is approximately around 0.588. I have sought a solution from the scikit-learn tutorial and authorized examples. **Normalization** will help to eliminate some disadvantages, such as **overfitting** and **keeping weight stable**.

<strong>Predicting result</strong>
After normalizing all these 6 features, the accuracy has increased to 0.625. In the investigation of the maximum depth of decision tree, the result progresses as the depth increases. However, the classifier will be overfitting when the depth is more than 5. The accuracy becomes stable at around 0.825 under the maximum 5 depths.

<h2 id="sum">Summary</h2>

In this project, I learned how to use **scikit-learn** application and draw visualize plot through **matplotlib**. Also, I try three methods to solve the missing value. It may be a tiny part of data cleaning. Nevertheless, I take it seriously. Owing to time limitation, I have to implement the linear regression and decision tree classifier in a simple and uncompleted procedure. I still want to ensure the beginning data cleaning is solved under a serious research processing. The fancy algorithm is popping every day. A cleaned enough data can be implemented for each algorithm in a short time. According to this reason, I compare means and standard deviations of these solved data.<br>

The above **decision tree classifier** has not been tested with enough big size data. Therefore, I can not ensure this model is a useful classifier. There’re several directions that may help analysis this urine testing data if we can get sufficient data. Follow the rule that FDA and medical profession are using. Then, changing the feature into ranking from 0 to 5. It may properly represent the relation within the feature. Besides, asking more domain medical knowledge from medical school professors. It’s important to understand adequately useful domain knowledge when doing data science research.

<h2 id="source">Source and References</h2>

1. <a href="http://vincentarelbundock.github.io/Rdatasets/doc/boot/urine.html">The data were obtained from Andrews, D.F. and Herzberg, A.M. (1985) Data: A Collection of Problems from Many Fields for the Student and Research Worker. Springer-Verlag.<br>Davison, A.C. and Hinkley, D.V. (1997) Bootstrap Methods and Their Application. Cambridge University Press.</a></span>
2. <a href="https://en.wikipedia.org/wiki/Kidney_stone_disease">Wikipedia, Kidney stone disease (June 24 2018)</a></span>
3. <a href="https://zh.wikipedia.org/wiki/%E8%85%8E%E7%B5%90%E7%9F%B3">Wikipedia, 腎結石 (June 24 2018)</a></span>
4. <a href="https://en.wikipedia.org/wiki/Clinical_urine_tests">Wikipedia, Clinical urine tests (June 11 2018)</a></span>
5. <a href="https://github.com/yaojenkuo/learn_python_for_a_r_user">Github, 2017 IT 邦幫忙鐵人賽 (February 26 2017)</a></span>
6. <a href="http://scikit-learn.org/stable/index.html">Scikit-learn Machine Learning in Python</a></span>
