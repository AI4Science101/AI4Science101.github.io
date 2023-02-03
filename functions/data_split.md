---
title: Dataset Splits
subtitle: 
toc: true
toc_title: Function Index
layout: page
show_sidebar: false
menubar: function_menu
hide_hero: true
---

## Overview of Dataset Splits

<p class='is-size-6'> Data split functions partition a dataset into training, validation, and test sets to support training of ML models, hyperparameter tuning, and fair evaluation and comparison of ML models. The function is called from within the data loader class. It accepts the following three inputs: </p>

<ul>
	<li><code>method</code>: Type of dataset split. TDC provides several types dataset splits to support realistic evaluations. Default type is Random Split. </li>
	<li><code>seed</code>: random seed. </li>
	<li><code>frac</code>: proportional size of training, validation, and test sets. By default, the sizes are set to 70%, 10%, and 20%, respectively.</li>
</ul>
<p class='is-size-6'> 
As the default TDC data format is Pandas DataFrame, it will return a dictionary with key 'train', 'valid', and 'test' and value of each set's data frame. 
</p>

```python
from tdc.X import Y
data = Y(name = Z)
split = data.get_split(method = 'random', seed = 42, frac = [0.7, 0.1, 0.2])
# split: {'train': train dataframe, 'valid': valid dataframe, 'test': test dataframe}
```

<p class='is-size-6'> 
<strong> Important Note: </strong> in this part, TDC provides a generic data split function where you can tune splitting schemes for your various research needs. In the benchmark mode, it is set to be a specific splitting method with fixed seed and fractions. To get that split, please use the <code>BenchmarkGroup</code> class in the <a href="/benchmark/overview">Leaderboard</a> page.
</p>

<p class='is-size-6'> 
We continue with brief description of different kinds of dataset splits provided in the TDC 
</p>

### Random Split

<p class='is-size-6'>  <strong> Description: </strong> The default for any split function. Randomly split the data into train, validation, and test set. </p>

```python
from tdc.single_pred import ADME
data = ADME(name = 'Caco2_Wang')
split = data.get_split(method = 'random')
```

### Scaffold Split

<p class='is-size-6'>  <strong> Description: </strong> Scaffold split is based on the scaffold of the molecules so that train/val/test set is more structurally different. It is more challenging than random split. </p>

<p class='is-size-6'>  <strong> Note: </strong> Scaffold split only applies to single-instance drugs-related tasks (ADME, Tox, HTS). Scaffold split also requires RDKit installed. </p>

```python
from tdc.single_pred import ADME
data = ADME(name = 'Caco2_Wang')
split = data.get_split(method = 'scaffold')
```

### Cold-Start Split
<p class='is-size-6'>  <strong> Description: </strong> Cold-start split is for multi-instance prediction problems such as DTI, GDA, DrugRes, MTI, where they present two entity types. It first splits on one entity type into train/valid/test and then move all pairs associated with that entity in each set as the final splits. To use that, set <code>column_name</code> to be the entity that you want to split on. For example, to do cold drug split on DTI task: </p>

```python
from tdc.multi_pred import DTI
data = DTI(name = 'DAVIS')
split = data.get_split(method = 'cold_split', column_name = 'Drug')
```

<p class='is-size-6'> From <code>0.3.3</code>, you can now pass a list of columns such that training/validation/testing would have distinct entities for all entities in the column list. For example, if you want to split on both drug and cell line, you can now do: </p>

```python
from tdc.multi_pred import DrugRes
data = DrugRes(name = 'GDSC1')
split = data.get_split(method = 'cold_split', column_name = ['Drug_ID', 'Cell Line_ID'])
```

### Combination Split

<p class='is-size-6'>  <strong> Description: </strong> Drug Combination Split is for drug combination dataset, where we split on drug combinations such that training/validation/testing would have distinct set of combinations. </p>

<p class='is-size-6'>  <strong> Note: </strong> Combination split only applies to drug combination tasks such as <code>DrugSyn</code>. </p>

```python
from tdc.multi_pred import DrugSyn
data = DrugSyn(name = 'DrugComb')
split = data.get_split(method = 'combination')
```