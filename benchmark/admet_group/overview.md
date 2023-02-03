---
title: ADMET Benchmark Group
subtitle:
layout: page
show_sidebar: false
menubar: lb_admet_group
hide_hero: true
---

## ADMET Benchmark Group

<p class="is-size-5"> ADMET is a cornerstone of small molecule drug discovery, defining drug efficacy and toxicity profile. An ML model that could accurately predict all ADMET properties using structural information of compounds would be greatly valuable.</p> 

<p class="is-size-5">We formulate the ADMET Benchmark Group using <a href="/single_pred_tasks/adme/">22 ADMET datasets in TDC</a>. The ADMET Group contains the following datasets: </p>

```python
from tdc import utils
names = utils.retrieve_benchmark_names('ADMET_Group')
# ['caco2_wang', 'hia_hou', ....]
```

<p class="is-size-5">Type the following to access any benchmark in the group, for example, <code>Caco2_Wang</code>:</p>

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

<p class="is-size-5"> Follow the <b><a href="/benchmark/overview/">instructions</a></b> on how to use the <code>BenchmarkGroup</code> class and obtain training, validation, and test sets, and how to submit your model to the leaderboard. </p>

<p class="is-size-5"> For every dataset in the benchmark group, we use the <a href="/functions/data_split/">scaffold split</a> to partition the dataset into training, validation, and test sets. We hold out 20% data samples for the test set. The performance metrics are: </p>

<ul class="is-large is-size-5">
    <li>For binary classification:</li>
    <ul class="is-large">
      <li>AUROC is used when the number of positive and negative samples are similar.</li>
      <li>AUPRC is used when the number of positive samples are much smaller than negative samples. </li>
    </ul>
    <li>For regression:</li>
    <ul class="is-large">
      <li> MAE is used for majority of benchmarks.</li>
      <li> Spearman's correlation coefficient is used for benchmarks that depend on factors beyond the chemical structure.</li>
    </ul>
</ul>

<p class="is-size-5"> We encourage submissions that reports results for the entire benchmark group. Still, we welcome and accept submissions that report partial results, for example, submissions with results for just one out of five ADMET categories. </p>

<div class="column is-12">
    <hr />
</div>

### Benchmark Data Summary

<hr />

### Absorption

<p class="is-size-5"> Absorption measures how a drug travels from the site of administration to site of action.</p>

<table class="table is-striped is-hoverable">
  <thead>
  <tr>
    <th>Dataset</th>
    <th>Unit</th>
    <th>Size</th>
    <th>Task</th>
    <th>Metric</th>
    <th>Dataset Split</th>
  </tr>
  </thead>
  <tr>
    <td><a href="/single_pred_tasks/adme/#caco-2-cell-effective-permeability-wang-et-al"> Caco2 </a></td>
    <td>cm/s</td>
    <td>906</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#hia-human-intestinal-absorption-hou-et-al"> HIA </a></td>
    <td>%</td>
    <td>578</td>
    <td>Binary</td>
    <td>AUROC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#pgp-p-glycoprotein-inhibition-broccatelli-et-al"> Pgp </a></td>
    <td>%</td>
    <td>1,212</td>
    <td>Binary</td>
    <td>AUROC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#bioavailability-ma-et-al"> Bioav </a></td>
    <td>%</td>
    <td>640</td>
    <td>Binary</td>
    <td>AUROC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#lipophilicity-astrazeneca"> Lipo </a></td>
    <td>log-ratio</td>
    <td>4,200</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#solubility-aqsoldb"> AqSol </a></td>
    <td>log mol/L</td>
    <td>9,982</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Scaffold</td>
  </tr>

</table>

<hr />

### Distribution

<p class="is-size-5"> Drug distribution refers to how drug moves to and from the various tissues of the body and the amount of drugs in the tissues. </p>

<table class="table is-striped is-hoverable">
  <thead>
  <tr>
    <th>Dataset</th>
    <th>Unit</th>
    <th>Size</th>
    <th>Task</th>
    <th>Metric</th>
    <th>Dataset Split</th>
  </tr>
  </thead>
  <tr>
    <td><a href="/single_pred_tasks/adme/#bbb-blood-brain-barrier-martins-et-al"> BBB </a></td>
    <td>%</td>
    <td>1,975</td>
    <td>Binary</td>
    <td>AUROC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#ppbr-plasma-protein-binding-rate-astrazeneca"> PPBR </a></td>
    <td>%</td>
    <td>1,797</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#vdss-volumn-of-distribution-at-steady-state-lombardo-et-al"> VDss </a></td>
    <td>L/kg</td>
    <td>1,130</td>
    <td>Regression</td>
    <td>Spearman</td>
    <td>Scaffold</td>
  </tr>

</table>

<hr />

### Metabolism

<p class="is-size-5"> Drug metabolism measures how specialized enzymatic systems breakdown the drugs and it determines the duration and intensity of a drug's action. </p>

<table class="table is-striped is-hoverable">
  <thead>
  <tr>
    <th>Dataset</th>
    <th>Unit</th>
    <th>Size</th>
    <th>Task</th>
    <th>Metric</th>
    <th>Dataset Split</th>
  </tr>
  </thead>
  <tr>
    <td><a href="/single_pred_tasks/adme/#cyp-p450-2c9-inhibition-veith-et-al"> CYP2C9 Inhibition </a></td>
    <td>%</td>
    <td>12,092</td>
    <td>Binary</td>
    <td>AUPRC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#cyp-p450-2d6-inhibition-veith-et-al"> CYP2D6 Inhibition </a></td>
    <td>%</td>
    <td>13,130</td>
    <td>Binary</td>
    <td>AUPRC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#cyp-p450-3a4-inhibition-veith-et-al"> CYP3A4 Inhibition </a></td>
    <td>%</td>
    <td>12,328</td>
    <td>Binary</td>
    <td>AUPRC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
  <td><a href="/single_pred_tasks/adme/#cyp2c9-substrate-carbon-mangels-et-al"> CYP2C9 Substrate </a></td>
    <td>%</td>
    <td>666</td>
    <td>Binary</td>
    <td>AUPRC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#cyp2d6-substrate-carbon-mangels-et-al"> CYP2D6 Substrate </a></td>
    <td>%</td>
    <td>664</td>
    <td>Binary</td>
    <td>AUPRC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#cyp3a4-substrate-carbon-mangels-et-al"> CYP3A4 Substrate </a></td>
    <td>%</td>
    <td>667</td>
    <td>Binary</td>
    <td>AUROC</td>
    <td>Scaffold</td>
  </tr>

</table>

<hr />

### Excretion

<p class="is-size-5"> Drug excretion is the removal of drugs from the body using various different routes of excretion, including urine, bile, sweat, saliva, tears, milk, and stool. </p>

<table class="table is-striped is-hoverable">
  <thead>
  <tr>
    <th>Dataset</th>
    <th>Unit</th>
    <th>Size</th>
    <th>Task</th>
    <th>Metric</th>
    <th>Dataset Split</th>
  </tr>
  </thead>
  <tr>
    <td><a href="/single_pred_tasks/adme/#half-life-obach-et-al"> Half Life </a></td>
    <td>hr</td>
    <td>667</td>
    <td>Regression</td>
    <td>Spearman</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/adme/#clearance-astrazeneca"> CL-Hepa </a></td>
    <td>uL.min-1.(10^6 cells)-1</td>
    <td>1,020</td>
    <td>Regression</td>
    <td>Spearman</td>
    <td>Scaffold</td>
  </tr>

  <tr>
    <td><a href="/single_pred_tasks/adme/#clearance-astrazeneca"> CL-Micro </a></td>
    <td>mL.min-1.g-1</td>
    <td>1,102</td>
    <td>Regression</td>
    <td>Spearman</td>
    <td>Scaffold</td>
  </tr>

</table>

<hr />

### Toxicity

<p class="is-size-5"> Toxicity measures how much damage a drug could cause to organisms. </p>

<table class="table is-striped is-hoverable">
  <thead>
  <tr>
    <th>Dataset</th>
    <th>Unit</th>
    <th>Size</th>
    <th>Task</th>
    <th>Metric</th>
    <th>Dataset Split</th>
  </tr>
  </thead>
  <tr>
    <td><a href="/single_pred_tasks/tox/#acute-toxicity-ld50"> LD50 </a></td>
    <td>log(1/(mol/kg))</td>
    <td>7,385</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/tox/#herg-blockers"> hERG </a></td>
    <td>%</td>
    <td>648</td>
    <td>Binary</td>
    <td>AUROC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/tox/#ames-mutagenicity"> Ames </a></td>
    <td>%</td>
    <td>7,255</td>
    <td>Binary</td>
    <td>AUROC</td>
    <td>Scaffold</td>
  </tr>
  <tr>
    <td><a href="/single_pred_tasks/tox/#dili-drug-induced-liver-injury"> DILI </a></td>
    <td>%</td>
    <td>475</td>
    <td>Binary</td>
    <td>AUROC</td>
    <td>Scaffold</td>
  </tr>

</table>



<script>
function sortTable(n, name, d) {
  var table, rows, switching, i, x, y, shouldSwitch, dir, switchcount = 0;
  table = document.getElementById(name);
  switching = true;
  //Set the sorting direction to ascending:
  if (d == 'desc'){
    dir = "desc"; 
  } else{
    dir = "asc"; 
  }
  
  /*Make a loop that will continue until
  no switching has been done:*/
  while (switching) {
    //start by saying: no switching is done:
    switching = false;
    rows = table.rows;
    /*Loop through all table rows (except the
    first, which contains table headers):*/
    for (i = 1; i < (rows.length - 1); i++) {
      //start by saying there should be no switching:
      shouldSwitch = false;
      /*Get the two elements you want to compare,
      one from current row and one from the next:*/
      x = rows[i].getElementsByTagName("TD")[n];
      y = rows[i + 1].getElementsByTagName("TD")[n];
      /*check if the two rows should switch place,
      based on the direction, asc or desc:*/
      if (dir == "asc") {
        if (Number(x.innerHTML.substring(0,5)) > Number(y.innerHTML.substring(0,5))) {
          //if so, mark as a switch and break the loop:
          shouldSwitch= true;
          break;
        }
      } else if (dir == "desc") {
        if (Number(x.innerHTML.substring(0,5)) < Number(y.innerHTML.substring(0,5))) {
          //if so, mark as a switch and break the loop:
          shouldSwitch = true;
          break;
        }
      }
    }
    if (shouldSwitch) {
      /*If a switch has been marked, make the switch
      and mark that a switch has been done:*/
      rows[i].parentNode.insertBefore(rows[i + 1], rows[i]);
      switching = true;
      //Each time a switch is done, increase this count by 1:
      switchcount ++;      
    } else {
      /*If no switching has been done AND the direction is "asc",
      set the direction to "desc" and run the while loop again.*/
      if (d == 'desc'){
        if (switchcount == 0 && dir == "desc") {
          dir = "asc";
          switching = true;
        }
      } else{
        if (switchcount == 0 && dir == "asc") {
          dir = "desc";
          switching = true;
        }
      }
    }
  }
}
</script>
