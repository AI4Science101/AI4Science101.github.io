---
title: Drug Target Domain Generalization Benchmark Group
subtitle:
layout: page
show_sidebar: false
menubar: lb_dti_dg_group
hide_hero: true
---

## Drug-Target Interaction Domain Generalization Benchmark Group

<p class="is-size-5">Drug-target interactions (DTI) characterize the binding of compounds to disease targets. Identifying high-affinity compounds is the first crucial step for drug discovery. Recent ML models have shown strong performances in DTI prediction, but they adopt a random dataset splitting where testing sets contain unseen pair of compound-target, but both of the compounds and targets are seen. However, pharmaceutical companies develop compound screening campaigns for novel targets or screen a novel class of compounds for known targets. These novel compounds and targets shift over the years. Thus, it requires a DTI ML model to achieve consistent performances to the subtle domain shifts along the temporal dimension. </p>

<p class="is-size-5">In this benchmark, we use DTIs in TDC.BindingDB that have patent information. Specifically, we formulate each domain consisting of DTIs that are patented in a specific year. We test various domain generalization methods to predict out-of-distribution DTIs in 2019-2021 after training on 2013-2018 DTIs, simulating the realistic scenario. </p>


<p class="is-size-5">To access a benchmark in the group, use the following code:</p>

```python
from tdc import BenchmarkGroup
group = BenchmarkGroup(name = 'DTI_DG_Group', path = 'data/')
benchmark = group.get('BindingDB_Patent')

predictions = {}
name = benchmark['name']
train_val, test = benchmark['train_val'], benchmark['test']

## --- train your model --- ##

predictions[name] = pred_test
out = group.evaluate(predictions)
```

<p class="is-size-5"> Follow the <b><a href="/benchmark/overview/">instructions</a></b> on how to use the <code>BenchmarkGroup</code> class and obtain training, validation, and test sets, and how to submit your model to the leaderboard. </p>

<p class="is-size-5"> The evaluation metric is pearson correlation coefficient (PCC). Validation set selection is crucial for a fair domain generalization methods comparison. Following the strategy of "Training-domain validation set" in DomainBed, from the 2013-2018 DTIs, we randomly set 20% of them as the validation set and use them as the in-distribution performance calculations as they follow the same as the training set and 2018-2021 are only used during testing, which we called out-of-distribution.</p>


<div class="column is-12">
    <hr />
</div>