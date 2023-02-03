---
title: Model Evaluation
subtitle:
layout: page
toc: true
toc_title: Function Index
show_sidebar: false
menubar: function_menu
hide_hero: true
---

## Regression Metrics

### Mean Squared Error (MSE)

<p class='is-size-6'>  <strong> Description: </strong> The mean square error measures the averages of the squares of the errors between the true value and the predicted value. It takes in a list/array of true values <code>y_true</code> and a list/array of predicted values <code>y_pred</code>, and outputs the MSE value.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'MSE')
# y_true: [0.8, 0.7, ...]; y_pred: [0.75, 0.73, ...]
score = evaluator(y_true, y_pred)
# score: 0.1
```

### Root-Mean Squared Error (RMSE)

<p class='is-size-6'>  <strong> Description: </strong> The root mean square error measures the square root of MSE. It takes in a list/array of true values <code>y_true</code> and a list/array of predicted values <code>y_pred</code>, and outputs the RMSE value.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'RMSE')
# y_true: [0.8, 0.7, ...]; y_pred: [0.75, 0.73, ...]
score = evaluator(y_true, y_pred)
# score: 0.31
```

### Mean Absolute Error (MAE)
<p class='is-size-6'>  <strong> Description: </strong> The mean absolute error measures the averages of the absolute value of the errors between the true value and the predicted value. It takes in a list/array of true values <code>y_true</code> and a list/array of predicted values <code>y_pred</code>, and outputs the MAE value.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'MAE')
# y_true: [0.8, 0.7, ...]; y_pred: [0.75, 0.73, ...]
score = evaluator(y_true, y_pred)
# score: 0.1
```

### Coefficient of Determination (R²)

<p class='is-size-6'>  <strong> Description: </strong> The R² measures the amount of associations between the true values and the predicted values. It takes in a list/array of true values <code>y_true</code> and a list/array of predicted values <code>y_pred</code>, and outputs the R² score.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'R2')
# y_true: [0.8, 0.7, ...]; y_pred: [0.75, 0.73, ...]
score = evaluator(y_true, y_pred)
# score: 0.8
```

### Pearson Correlation Coefficient (PCC)

<p class='is-size-6'>  <strong> Description: </strong> The PCC measures the amount of linear correlations between the true values and the predicted values. It takes in a list/array of true values <code>y_true</code> and a list/array of predicted values <code>y_pred</code>, and outputs the PCC score.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'PCC')
# y_true: [0.8, 0.7, ...]; y_pred: [0.75, 0.73, ...]
score = evaluator(y_true, y_pred)
# score: 0.8
```

### Spearman Correlation Coefficient

<p class='is-size-6'>  <strong> Description: </strong> The Spearman Correlation Coefficient is a nonparametric measure of monotonicity of relationship between the true values and the predicted values. It takes in a list/array of true values <code>y_true</code> and a list/array of predicted values <code>y_pred</code>, and outputs the spearman score.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Spearman')
# y_true: [0.8, 0.7, ...]; y_pred: [0.75, 0.73, ...]
score = evaluator(y_true, y_pred)
# score: 0.8
```

----

## Binary Classification Metrics

### Area Under Receiver Operating Characteristic Curve (ROC-AUC)

<p class='is-size-6'>  <strong> Description: </strong> The ROC-AUC measures the area under the ROC curve which is plotting the true positive and false positive at various threshold. It takes in a list/array of binary true values <code>y_true</code> and a list/array of real-valued predicted scores <code>y_pred</code>, and outputs the ROC-AUC score.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'ROC-AUC')
# y_true: [1, 0, ...]; y_pred: [0.75, 0.23, ...]
score = evaluator(y_true, y_pred)
# score: 0.88
```

### Area Under the Precision-Recall Curve (PR-AUC)

<p class='is-size-6'>  <strong> Description: </strong> The PR-AUC measures the area under the precision-recall curve which is plotting the precision and recall at various threshold. It takes in a list/array of binary true values <code>y_true</code> and a list/array of real-valued predicted scores <code>y_pred</code>, and outputs the PR-AUC score.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'PR-AUC')
# y_true: [1, 0, ...]; y_pred: [0.75, 0.23, ...]
score = evaluator(y_true, y_pred)
# score: 0.88
```


### Range LogAUC

<p class='is-size-6'>  <strong> Description: </strong> In a realistic setting, only a small percentage of samples can be selected for experimental tests in consideration of cost. This means only molecules with very high predicted score can be worth testing, i.e., the decision threshold is high. And the high decision threshold corresponds to the left side of the ROC curve, i.e., those FPRs with small values. Also, because the threshold cannot be predetermined, the area under the curve is used to consolidate all possible thresholds within a certain FPR range. Finally, the logarithm is used to bias smaller FPRs. See [1] for reference.</p>

<p class='is-size-6'>Default range: [0.001, 0.1]. The higher the logAUC[0.001, 0.1], the better the performance. A perfect classifer gets a logAUC[0.001, 0.1] ) of 1, while a random classifer gets a logAUC[0.001, 0.1] ) of around 0.0215 (See [2]) </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'range_logAUC')
score = evaluator(y_true, y_pred)
# score: 0.0215
```

<p class='is-size-6'> <strong> References: </strong> </p>

[1] Mysinger, M.M. and B.K. Shoichet, Rapid Context-Dependent Ligand Desolvation in Molecular Docking. Journal of Chemical Information and Modeling, 2010. 50(9): p. 1561-1573.

[2] Mendenhall, J. and J. Meiler, Improving quantitative structure–activity relationship models using Artificial Neural Networks trained with dropout. Journal of computer-aided molecular design, 2016. 30(2): p. 177-189.


<p class='is-size-6'> <strong> Contributed by Yunchao Liu.</strong> </p>

----

### Accuracy Metrics

<p class='is-size-6'>  <strong> Description: </strong> The accuracy calculates the fraction of correct prediction at a threshold. It takes in a list/array of binary true values <code>y_true</code> and a list/array of real-valued predicted scores <code>y_pred</code> and a threshold value <code>thr</code>, and outputs the accuracy score. The default of threshold value is 0.5. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Accuracy')
# y_true: [1, 0, ...]; y_pred: [0.75, 0.23, ...]
score = evaluator(y_true, y_pred, threshold = 0.5)
# score: 0.8
```

### Precision

<p class='is-size-6'>  <strong> Description: </strong> The precision calculates the fraction of correctly predicted positive instance out of the total predicted positive values at a threshold. It takes in a list/array of binary true values <code>y_true</code> and a list/array of real-valued predicted scores <code>y_pred</code> and a threshold value <code>thr</code>, and outputs the precision score. The default of threshold value is 0.5. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Precision')
# y_true: [1, 0, ...]; y_pred: [0.75, 0.23, ...]
score = evaluator(y_true, y_pred, threshold = 0.5)
# score: 0.8
```

### Recall

<p class='is-size-6'>  <strong> Description: </strong> The recall calculates the fraction of correctly predicted positive instance out of all the positive instances at a threshold. It takes in a list/array of binary true values <code>y_true</code> and a list/array of real-valued predicted scores <code>y_pred</code> and a threshold value <code>thr</code>, and outputs the recall score. The default of threshold value is 0.5. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Recall')
# y_true: [1, 0, ...]; y_pred: [0.75, 0.23, ...]
score = evaluator(y_true, y_pred, threshold = 0.5)
# score: 0.8
```

### F1 Score

<p class='is-size-6'>  <strong> Description: </strong> The F1 is the harmonic mean of recall and precision. It takes in a list/array of binary true values <code>y_true</code> and a list/array of real-valued predicted scores <code>y_pred</code> and a threshold value <code>thr</code>, and outputs the recall score. The default of threshold value is 0.5. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'F1')
# y_true: [1, 0, ...]; y_pred: [0.75, 0.23, ...]
score = evaluator(y_true, y_pred, threshold = 0.5)
# score: 0.8
```

### Precision at Recall of K

<p class='is-size-6'>  <strong> Description: </strong> At some realistic settings for retrieval tasks, it is important to have high precision given a high recall rate for increasing the precision in the retrieved positive set while retrieve large proportions of positive data. This metric calculates the precision value at the minimum threshold where recall has K. It takes in a list/array of binary true values <code>y_true</code> and a list/array of real-valued predicted scores <code>y_pred</code> and a threshold value <code>thr</code>, and outputs the PR@K score. The default of threshold value is 0.9. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'PR@K')
# y_true: [1, 0, ...]; y_pred: [0.75, 0.23, ...]
score = evaluator(y_true, y_pred, threshold = 0.9)
# score: 0.8
```

### Recall at Precision of K

<p class='is-size-6'>  <strong> Description: </strong> At some realistic settings for retrieval tasks, it is important to have high recall given a high precision rate to prevent false alarms. This metric calculates the recall value at the minimum threshold where precision has K. It takes in a list/array of binary true values <code>y_true</code> and a list/array of real-valued predicted scores <code>y_pred</code> and a threshold value <code>thr</code>, and outputs the RP@K score. The default of threshold value is 0.9. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'RP@K')
# y_true: [1, 0, ...]; y_pred: [0.75, 0.23, ...]
score = evaluator(y_true, y_pred, threshold = 0.9)
# score: 0.8
```

----

## Multi-class Classification Metrics

### Micro-F1, Micro-Precision, Micro-Recall, Accuracy
<p class='is-size-6'>  <strong> Description: </strong> The micro-F1 in multi-class prediction is the same as micro-precision, micro-recall and accuracy. It calculates the fraction of correct prediction. It takes in a list/array of true integer label index <code>y_true</code> and a list/array of predicted integer label index <code>y_pred</code>, and outputs the score. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'MicroF1')
# y_true: [1, 3, ...]; y_pred: [1, 2, ...]
score = evaluator(y_true, y_pred)
# score: 0.8
```

### Macro-F1
<p class='is-size-6'>  <strong> Description: </strong> The macro-F1 calculates the fraction of correct prediction for each label and then takes the unweighted average. This is useful when the label distribution is highly imbalanced and one wants to test the performance on low-data labels. It takes in a list/array of true integer label index <code>y_true</code> and a list/array of predicted integer label index <code>y_pred</code>, and outputs the score. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'MacroF1')
# y_true: [1, 3, ...]; y_pred: [1, 2, ...]
score = evaluator(y_true, y_pred)
# score: 0.5
```

### Cohen's Kappa (Kappa)

<p class='is-size-6'>  <strong> Description: </strong> The Kappa score calculates the level of agreement between the prediction and the true labels. It takes in a list/array of true integer label index <code>y_true</code> and a list/array of predicted integer label index <code>y_pred</code>, and outputs the Kappa score. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Kappa')
# y_true: [1, 3, ...]; y_pred: [1, 2, ...]
score = evaluator(y_true, y_pred)
# score: 0.5
```

----

## Token-level Classification Metrics

### Average ROC-AUC

<p class='is-size-6'>  <strong> Description: </strong> The averages ROC-AUC first calculates ROC-AUC score between the sequence of 1/0 true labels and the sequence of prediction labels for every instance. Then, it takes the average of all the instances' ROC-AUC scores. It takes in a list of list/array of true integer label index for every instance <code>y_true</code> and a list of list/array of predicted integer label index for every instance <code>y_pred</code>, and outputs the average ROC-AUC score. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Avg-ROC-AUC')
# y_true: [[0, 1, ...], [1, 1, ...], ...]; y_pred: [[0.1, 0.8, ...], [0.9, 0.89, ...], ...]
score = evaluator(y_true, y_pred)
# score: 0.8
```

----

## Molecule Generation Metrics

### Diversity

<p class='is-size-6'>  <strong> Description: </strong>The diversity of a set of molecules is defined as the average pairwise Tanimoto distance between the Morgan fingerprints.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Diversity')
evaluator(['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'C[C@@H]1CCc2c(sc(NC(=O)c3ccco3)c2C(N)=O)C1', \
            'CCNC(=O)c1ccc(NC(=O)N2CC[C@H](C)[C@H](O)C2)c(C)c1', \
            'C[C@@H]1CCN(C(=O)CCCc2ccccc2)C[C@@H]1O'])
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://arxiv.org/abs/1708.08227"> Benhenda, Mostapha. "ChemGAN challenge for drug discovery: can AI reproduce natural chemical diversity?." arXiv preprint arXiv:1708.08227 (2017).</a>

<hr />

### KL divergence
 
<p class='is-size-6'>  <strong> Description: </strong>  KL divergence between the probability distributions of a variety of physicochemical descriptors for the training set and a set of generated molecules. Models able to capture the distributions of molecules in the training set will lead to small KL divergence values. To increase diversity, we want high KL.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'KL_Divergence')
generated = ['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'CCNC(=O)c1ccc(NC(=O)N2CC[C@H](C)[C@H](O)C2)c(C)c1', \
            'C[C@@H]1CCN(C(=O)CCCc2ccccc2)C[C@@H]1O']
training = ['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'C[C@@H]1CCc2c(sc(NC(=O)c3ccco3)c2C(N)=O)C1']
evaluator(generated, training)
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.8b00839"> Brown, Nathan, et al. "GuacaMol: benchmarking models for de novo molecular design." Journal of chemical information and modeling 59.3 (2019): 1096-1108. </a>

<hr />

### Frechet ChemNet Distance (FCD)

<p class='is-size-6'>  <strong> Description: </strong> FCD first takes the means and covariances of the activations of the penultimate layer of ChemNet are calculated for the reference set and for the set of generated molecules. The FCD is then calculated as the Frechet distance for both pairs of values. Similar molecule distributions are characterized by low FCD values.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'FCD_Distance')
generated = ['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'CCNC(=O)c1ccc(NC(=O)N2CC[C@H](C)[C@H](O)C2)c(C)c1', \
            'C[C@@H]1CCN(C(=O)CCCc2ccccc2)C[C@@H]1O']
training = ['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'C[C@@H]1CCc2c(sc(NC(=O)c3ccco3)c2C(N)=O)C1']
evaluator(generated, training)
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://pubs.acs.org/doi/abs/10.1021/acs.jcim.8b00839"> Brown, Nathan, et al. "GuacaMol: benchmarking models for de novo molecular design." Journal of chemical information and modeling 59.3 (2019): 1096-1108. </a>

<hr />

### Novelty

<p class='is-size-6'>  <strong> Description: </strong> Novelty is the fraction of the generated molecules that are not present in the training set.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Novelty')
generated = ['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'CCNC(=O)c1ccc(NC(=O)N2CC[C@H](C)[C@H](O)C2)c(C)c1', \
            'C[C@@H]1CCN(C(=O)CCCc2ccccc2)C[C@@H]1O']
training = ['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'C[C@@H]1CCc2c(sc(NC(=O)c3ccco3)c2C(N)=O)C1']
evaluator(generated, training)
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://arxiv.org/abs/1811.12823">[1] Polykovskiy et al. "Molecular Sets (MOSES): A Benchmarking Platform for Molecular Generation Models.", Frontiers in Pharmacology. (2020). </a> 

<hr />
 
### Validity

<p class='is-size-6'>  <strong> Description: </strong> Validity is calculated using RDKit’s molecular structure parser that checks atoms’ valency and consistency of bonds in aromatic rings.</p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Validity')
generated = ['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'CCNC(=O)c1ccc(NC(=O)N2CC[C@H](C)[C@H](O)C2)c(C)c1', \
            'C[C@@H]1CCN(C(=O)CCCc2ccccc2)C[C@@H]1O']
evaluator(generated)
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://arxiv.org/abs/1811.12823">[1] Polykovskiy et al. "Molecular Sets (MOSES): A Benchmarking Platform for Molecular Generation Models.", Frontiers in Pharmacology. (2020). </a> 

<hr />

### Uniqueness

<p class='is-size-6'>  <strong> Description: </strong> Uniqueness measures how often a model is able to generate duplicated molecules. If that is the case, the uniqueness is low and vice versa. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name = 'Uniqueness')
generated = ['CC(C)(C)[C@H]1CCc2c(sc(NC(=O)COc3ccc(Cl)cc3)c2C(N)=O)C1', \
            'CCNC(=O)c1ccc(NC(=O)N2CC[C@H](C)[C@H](O)C2)c(C)c1', \
            'C[C@@H]1CCN(C(=O)CCCc2ccccc2)C[C@@H]1O']
evaluator(generated)
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="https://arxiv.org/abs/1811.12823">[1] Polykovskiy et al. "Molecular Sets (MOSES): A Benchmarking Platform for Molecular Generation Models.", Frontiers in Pharmacology. (2020). </a> 

<hr />

### RMSD

<p class='is-size-6'>  <strong> Description: </strong> RMSD measures the average distance between the atoms of two structures. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name='rmsd')
evaluator(structure1, structure2) # structures of shape [N particles, 3]
```
<hr />


### Kabsch-RMSD

<p class='is-size-6'>  <strong> Description: </strong> Kabsch-RMSD measures the average distance between the atoms of two structures after superimposing by the Kabsch algorithm [1]. </p>

```python
from tdc import Evaluator
evaluator = Evaluator(name='kabsch_rmsd')
evaluator(structure1, structure2) # structures of shape [N particles, 3]
```

<p class='is-size-6'>  <strong> References: </strong>  </p>

<a href="http://scripts.iucr.org/cgi-bin/paper?S0567739476001873">[1]  Kabsch, W., 1976. A solution for the best rotation to relate two sets of vectors. Acta Crystallographica Section A: Crystal Physics, Diffraction, Theoretical and General Crystallography, 32(5), pp.922-923
 </a> 

<hr />