---
title: Solubility Leaderboard
subtitle:
layout: page
show_sidebar: false
menubar: lb_admet_group
hide_hero: true
---

<p class="is-size-3"><b><code>TDC.Solubility_AqSolDB</code> Leaderboard</b></p>

### Dataset Summary

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
    <td><a href="/single_pred_tasks/adme/#solubility-aqsoldb"> TDC.Solubility_AqSolDB </a></td>
    <td>log mol/L</td>
    <td>9,982</td>
    <td>Regression</td>
    <td>MAE</td>
    <td>Scaffold</td>
  </tr>
</table>

<div class="column is-12">
    <hr />
</div>

### Leaderboard

<table class="table is-striped is-hoverable" id="A">
  <thead>
  <tr>
   <!--When a header is clicked, run the sortTable function, with a parameter, 0 for sorting by names, 1 for sorting by country:-->  
    <th>Rank</th>
    <th>Model</th>
    <th>Contact</th>
    <th>Link</th>
    <th>#Params</th>
    <th onclick="sortTable(5, 'A', 'asc')">MAE <i class="fas fa-long-arrow-alt-down"></i> </th>
  </tr>
</thead>
  <tr> 
  <td> 1 </td> 
  <td> XGBoost </td> 
  <td><a href="mailto:haot@smu.edu">Hao Tian</a></td> 
  <td><a href="https://github.com/smu-tao-group/ADMET_XGBoost"> GitHub</a>, <a href="https://arxiv.org/abs/2204.07532v2">Paper </a></td> 
  <td> 29 </td> 
  <td>0.727 <span>&#177;</span> 0.004 </td> 
</tr>
<tr> 
  <td> 2 </td> 
  <td> AttentiveFP </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://pubmed.ncbi.nlm.nih.gov/31408336/">Paper </a></td> 
  <td> 300,806 </td> 
  <td>0.776 <span>&#177;</span> 0.008 </td> 
</tr>
<tr> 
  <td> 3 </td> 
  <td> RDKit2D + MLP (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 633,409 </td> 
  <td>0.827 <span>&#177;</span> 0.047 </td> 
</tr>
<tr> 
  <td> 4 </td> 
  <td> GCN </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://arxiv.org/abs/1609.02907">Paper </a></td> 
  <td> 191,810 </td> 
  <td>0.907 <span>&#177;</span> 0.020 </td> 
</tr>
<tr> 
  <td> 5 </td> 
  <td> NeuralFP </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://ieeexplore.ieee.org/document/9412489">Paper </a></td> 
  <td> 480,193 </td> 
  <td>0.947 <span>&#177;</span> 0.016 </td> 
</tr>
<tr> 
  <td> 6 </td> 
  <td> CNN (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 226,625 </td> 
  <td>1.023 <span>&#177;</span> 0.023 </td> 
</tr>
<tr> 
  <td> 7 </td> 
  <td> AttrMasking </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://arxiv.org/abs/1905.12265">Paper </a></td> 
  <td> 2,067,053 </td> 
  <td>1.026 <span>&#177;</span> 0.020 </td> 
</tr>
<tr> 
  <td> 8 </td> 
  <td> ContextPred </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://arxiv.org/abs/1905.12265">Paper </a></td> 
  <td> 2,067,053 </td> 
  <td>1.040 <span>&#177;</span> 0.045 </td> 
</tr>
<tr> 
  <td> 9 </td> 
  <td> Morgan + MLP (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 1,477,185 </td> 
  <td>1.203 <span>&#177;</span> 0.019 </td> 
</tr>

</table>

<i class="fas fa-long-arrow-alt-down"></i>: The lower the better.
