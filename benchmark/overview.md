---
title: Leaderboard Guide
subtitle:
layout: page
show_sidebar: false
hide_hero: true
---


# Leaderboard Guidelines

<p class="is-size-5"> Every dataset in TDC is a benchmark, and we provide training, validation, and test sets for it, together with data splits and performance evaluation metrics. </p>

<p class="is-size-5">To participate in the leaderboard for a specific benchmark, follow these steps: </p>
<ol>
    <li><p class="is-size-5">Use the TDC benchmark data loader to retrieve the benchmark.</p></li>
    <li><p class="is-size-5">Use training and/or validation set to train your model.</p></li>
    <li><p class="is-size-5">Use the TDC model evaluator to calculate the performance of your model on the test set.</p></li>
    <li><p class="is-size-5">Submit the test set performance to a TDC leaderboard.</p></li>
</ol>

<p class="is-size-5">Below we provide detailed instructions on how to participate in TDC leaderboards. </p>

<p class="is-size-5">As many datasets share a therapeutics theme, we organize benchmarks into meaningfully defined groups, which we refer to as <b>benchmark groups</b>. Datasets and tasks within a benchmark group are carefully curated and centered around a theme (for example, TDC contains a benchmark group to support ML predictions of the ADMET properties). While every benchmark group consists of multiple benchmarks, it is possible to separately submit results for each benchmark in the group.</p>

<div class="column is-12">
    <hr />
</div>

## Step-by-step Instructions

<p class='is-size-5'> TDC provides a programmatic framework to access the benchmarks and use them for model evaluation.</p>

#### Step 1: Train your model using a TDC BenchmarkGroup

<p class='is-size-5'> Suppose you want to evaluate your model on the <code>Caco2_Wang</code> benchmark that belongs to the <code>ADMET_Group</code> benchmark group. Take the following code and replace the commented line block with the code to train your model. The <code>train</code>, <code>valid</code>, <code>test</code> variables contain the split of the benchmark dataset. </p>

```python
from tdc.benchmark_group import admet_group
group = admet_group(path = 'data/')
predictions_list = []

for seed in [1, 2, 3, 4, 5]:
    benchmark = group.get('Caco2_Wang') 
    # all benchmark names in a benchmark group are stored in group.dataset_names
    predictions = {}
    name = benchmark['name']
    train_val, test = benchmark['train_val'], benchmark['test']
    train, valid = group.get_train_valid_split(benchmark = name, split_type = 'default', seed = seed)
    
        # --------------------------------------------- # 
        #  Train your model using train, valid, test    #
        #  Save test prediction in y_pred_test variable #
        # --------------------------------------------- #
        
    predictions[name] = y_pred_test
    predictions_list.append(predictions)

results = group.evaluate_many(predictions_list)
# {'caco2_wang': [6.328, 0.101]}
```

<p class='is-size-5'> The output <code>results</code> is a dictionary storing average values and standard deviations of each performance metric achieved by your model on the <code>Caco2_Wang</code> benchmark. </p>


#### Step 2: Submit results of your model to a TDC Leaderboard

<p class='is-size-5'> We invite submissions to any one or multiple benchmarks in a group. To be included in the leaderboard, please fill out <b><a href="https://forms.gle/HYupGaV7WDuutbr9A">THIS FORM</a></b>, include results of your model and provide a brief summary about your model (e.g., the number of parameters and hardware details).</p>

<div class="column is-12">
    <hr />
</div>

## Further Details about Benchmark Groups in TDC

<p class="is-size-5"> The <code>BenchmarkGroup</code> class is a wrapper class that provides utility functions for benchmarking. For each benchmark, TDC provides a separate <code>test</code> set and a <code>train_val</code> set. </p>

```python
from tdc.benchmark_group import admet_group
group = admet_group(path = 'data/')
benchmark = group.get('Caco2_Wang')

predictions = {}
name = benchmark['name']
train_val, test = benchmark['train_val'], benchmark['test']

## --- train your model --- ##

predictions[name] = y_pred
group.evaluate(predictions)
# {'caco2_wang': {'mae': 0.234}}
```

<p class="is-size-5"> You can use <code>train_val</code> to construct training and validation sets as you see best fit. For example, you can (1) construct a customized training and validation set using the <code>train_val</code> or (2) use a <a href="https://tdcommons.ai/functions/data_split/">TDC utility function</a> to get data splits for different random seeds: </p>

```python
train, valid = group.get_train_valid_split(benchmark = 'Caco2_Wang', split_type = 'default', seed = 42)
```	

<p class="is-size-5"> Importantly, you must evaluate your model on the test set as specified by TDC to ensure fair comparison of models. To promote robust measurement of model performance, TDC requires at minimum five independent runs of the model to calculate average performance and standard deviation. Following is an example showing how to obtain five different train and validation splits: </p>

```python
from tdc.benchmark_group import admet_group
group = admet_group(path = 'data/')
predictions_list = []

for seed in [1, 2, 3, 4, 5]:

    benchmark = group.get('Caco2_Wang')
    
    predictions = {}
    name = benchmark['name']
    train_val, test = benchmark['train_val'], benchmark['test']
    train, valid = group.get_train_valid_split(benchmark = name, split_type = 'default', seed = seed)
    
    ## --- train your model --- ##
        
    predictions[name] = y_pred_test
    predictions_list.append(predictions)

group.evaluate_many(predictions_list)
# {'caco2_wang': [6.328, 0.101]}
```

<p class='is-size-5'> You can get a list of benchmarks included in the benchmark group as follows: </p>

```python
from tdc import utils
names = utils.retrieve_benchmark_names('ADMET_Group')
# ['caco2_wang', 'hia_hou', ....]
```
<p class='is-size-5'> Alternatively, the same can be achieved via: </p>

```python
from tdc.benchmark_group import admet_group
group = admet_group(path = 'data/')
group.dataset_names
# ['caco2_wang', 'hia_hou', ....]
```

<p class='is-size-5'> For every benchmark group, we provide multiple benchmarks that all instantiate the same learning task. We encourage you to submit results for the entire benchmark group; however, we also accept submissions reporting performance on just one benchmark in the group. To access all benchmarks in a group, TDC provides the following helper function:</p>

```python
from tdc.benchmark_group import admet_group
group = admet_group(path = 'data/')
predictions_list = []

for seed in [1, 2, 3, 4, 5]:
    predictions = {}
    for benchmark in group:
        name = benchmark['name']
        train_val, test = benchmark['train_val'], benchmark['test']
        train, valid = group.get_train_valid_split(benchmark = name, split_type = 'default', seed = seed)
        ## --- train your model --- ##
        predictions[name] = y_pred_test
    predictions_list.append(predictions)

group.evaluate_many(predictions_list)
# {'caco2_wang': [6.328, 0.101], 'hia_hou': [0.5, 0.01], ...}
```
<div class="column is-12">
    <hr />
</div>

## The FAIR Guiding Principles

<p class='is-size-5'>ML tools have become essential for research. TDC leaderboards keep track of ML tools across the entire range of therapeutics. To improve the findability, accessibility, interoperability, and reuse of ML tools, we apply <a href="https://github.com/force11/FAIR4RS">FAIR4RS principles and implementation guidelines</a> to all software and ML tools included in TDC leaderboards.</p> 

<p class="is-size-5">We strongly believe that software and ML tools should be open and adhere to FAIR principles to encourage repeatability, reproducibility, and reuse. TDC follows the FAIR guidelines for both <a href="https://www.nature.com/articles/sdata201618%22"> datasets </a> as well as <a href="https://content.iospress.com/articles/data-science/ds190026#ref001">ML tools and data functions</a>. </p>

<div class="column is-12">
    <hr />
</div>

<p class="is-size-3 has-text-centered"> <strong>Start Exploring Groups of Leaderboards in TDC</strong> </p>

<div class="container">
        <div class="columns is-vcentered is-size-5">
            <div class="column is-4 has-text-centered"> <a href="/benchmark/admet_group/overview" class="box has-background-info has-text-white">ADMET Group</a></div>
            <div class="column is-4 has-text-centered"> <a href="/benchmark/drugcombo_group/overview" class="box has-background-info has-text-white">Drug Combination Group</a></div>
            <div class="column is-4 has-text-centered"> <a href="/benchmark/docking_group/overview" class="box has-background-info has-text-white">Docking Group</a></div>
        </div>
</div>

