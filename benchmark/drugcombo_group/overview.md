---
title: Drug Combination Benchmark Group
subtitle:
layout: page
show_sidebar: false
menubar: lb_drugcombo_group
hide_hero: true
---

## Drug Combination Benchmark Group

<p class="is-size-5">Drug combinations create promising new therapeutic opportunities for expanding the use of drugs and improving their efficacy. For instance, simultaneous modulation of multiple targets can address the issue of drug resistance seen in cancer treatments. However, experimentally exploring the space of possible drug combinations is not a feasible. For this reason, ML models capable of identifying candidate combinatorial treatments could be very valuable. </p>

<p class="is-size-5"> Synergy represents the deviation of observed drug combination response from expected effects had non-interaction. This benchmark group is defined on <a href="https://academic.oup.com/nar/article-abstract/47/W1/W43/5486743"> <code>TDC.DrugComb</code> </a>dataset and evaluates ML models for their ability to predict five established synergy endpoints:</p> 
<ul class="is-size-5">
    <li>The main endpoint is called drug combination sensitivity score <code>TDC.DrugComb_CSS</code>, which is derived using the relative IC50 values of compounds and the areas under dose-response curves. For the CSS, we also provide information on tissue identity of cell lines where drug response was measured.</li>
    <li>The Bliss model endpoint <code>TDC.DrugComb_Bliss</code>.</li>
    <li>The highest single agent endpoint <code>TDC.DrugComb_HSA</code>. </li>
    <li>The Loewe additivity model endpoint <code>TDC.DrugComb_Loewe</code>.</li>
    <li>The zero interaction potency endpoint <code>TDC.DrugComb_ZIP</code>.</li>
</ul>

<p class="is-size-5">To retrieve names of all benchmarks in this group, type the following:</p> 

```python
from tdc import utils
names = utils.retrieve_benchmark_names('DrugCombo_Group')
# ['drugcomb_css', 'drugcomb_hsa', ...]
```

<p class="is-size-5">To access a benchmark in the group, use the following code:</p>

```python
from tdc.benchmark_group import drugcombo_group
group = drugcombo_group(path = 'data/')

benchmark = group.get('Drugcomb_CSS')

predictions = {}
name = benchmark['name']
train_val, test = benchmark['train_val'], benchmark['test']

## --- train your model --- ##

predictions[name] = pred_test
out = group.evaluate(predictions)
print(out)
'''
Note that the output includes the automatic evaluations across tissues:

{'drugcomb_css': {'mae': 23.082},
 'drugcomb_css_kidney': {'mae': 21.906},
 'drugcomb_css_lung': {'mae': 21.341},
 'drugcomb_css_breast': {'mae': 18.542},
 'drugcomb_css_hematopoietic_lymphoid': {'mae': 40.55},
 'drugcomb_css_colon': {'mae': 25.224},
 'drugcomb_css_prostate': {'mae': 22.19},
 'drugcomb_css_ovary': {'mae': 19.638},
 'drugcomb_css_skin': {'mae': 18.777},
 'drugcomb_css_brain': {'mae': 21.855}}
'''
```

<p class="is-size-5"> Follow the <b><a href="/benchmark/overview/">instructions</a></b> on how to use the <code>BenchmarkGroup</code> class and obtain training, validation, and test sets, and how to submit your model to the leaderboard. </p>

<p class="is-size-5"> For every dataset in the benchmark, we use the <a href="/functions/data_split/">drug combination split</a> to partition the dataset into training, validation, and test sets. We hold out 20% data samples for the test set. The performance metric is MAE. </p>

<p class="is-size-5"> Note that tissue types are <b>automatically</b> determined based on test set prediction on the <code>TDC.DrugComb_CSS</code> endpoint.</p>

<div class="column is-12">
    <hr />
</div>

### Benchmark Data Summary

<hr />

<table class="table is-striped is-hoverable">
  <thead>
  <tr>
    <th>Dataset</th>
    <th>Size</th>
    <th>Task</th>
    <th>Metric</th>
    <th>Dataset Split</th>
  </tr>
  </thead>
  <tr>
    <td><code>TDC.DrugComb_CSS</code></td>
    <td>297,098</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Combination</td>
  </tr>
  <tr>
    <td><code>TDC.DrugComb_HSA</code></td>
    <td>297,098</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Combination</td>
  </tr>
  <tr>
    <td><code>TDC.DrugComb_Loewe</code></td>
    <td>297,098</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Combination</td>
  </tr>
  <tr>
    <td><code>TDC.DrugComb_Bliss</code></td>
    <td>297,098</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Combination</td>
  </tr>
  <tr>
    <td><code>TDC.DrugComb_Zip</code></td>
    <td>297,098</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Combination</td>
  </tr>
</table>
