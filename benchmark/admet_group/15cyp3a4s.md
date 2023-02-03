---
title: CYP3A4_Substrate_CarbonMangels Leaderboard
subtitle:
layout: page
show_sidebar: false
menubar: lb_admet_group
hide_hero: true
---

<p class="is-size-3"><b><code>TDC.CYP3A4_Substrate_CarbonMangels</code> Leaderboard</b></p>

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
    <td><a href="/single_pred_tasks/adme/#cyp3a4-substrate-carbon-mangels-et-al"> TDC.CYP3A4_Substrate_CarbonMangels </a></td>
    <td>%</td>
    <td>667</td>
    <td>Binary</td>
    <td>AUROC</td>
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
    <th onclick="sortTable(5, 'A', 'asc')">AUROC <i class="fas fa-long-arrow-alt-up"></i> </th>
  </tr>
</thead>
 <tr> 
  <td> 1 </td> 
  <td> XGBoost </td> 
  <td><a href="mailto:haot@smu.edu">Hao Tian</a></td> 
  <td><a href="https://github.com/smu-tao-group/ADMET_XGBoost"> GitHub</a>, <a href="https://arxiv.org/abs/2204.07532v2">Paper </a></td> 
  <td> 29 </td> 
  <td>0.680 <span>&#177;</span> 0.005 </td> 
</tr>
<tr> 
  <td> 2 </td> 
  <td> CNN (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 226,625 </td> 
  <td>0.662 <span>&#177;</span> 0.031 </td> 
</tr>
<tr> 
  <td> 3 </td> 
  <td> SimGCN </td> 
  <td><a href="mailto:suman@katanagraph.com">Suman Kalyan Bera</a></td> 
  <td><a href="https://github.com/KatanaGraph/SimGCN-TDC"> GitHub</a>, <a href="https://github.com/KatanaGraph/SimGCN-TDC/blob/main/Report_SimGCN_for_TDC_Benchmarks.pdf">Paper </a></td> 
  <td> 1,103,000 </td> 
  <td>0.640 <span>&#177;</span> 0.016 </td> 
</tr>
<tr> 
  <td> 4 </td> 
  <td> RDKit2D + MLP (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 633,409 </td> 
  <td>0.639 <span>&#177;</span> 0.012 </td> 
</tr>
<tr> 
  <td> 5 </td> 
  <td> Morgan + MLP (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 1,477,185 </td> 
  <td>0.633 <span>&#177;</span> 0.013 </td> 
</tr>
<tr> 
  <td> 6 </td> 
  <td> GCN </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://arxiv.org/abs/1609.02907">Paper </a></td> 
  <td> 191,810 </td> 
  <td>0.590 <span>&#177;</span> 0.023 </td> 
</tr>
<tr> 
  <td> 7 </td> 
  <td> NeuralFP </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://ieeexplore.ieee.org/document/9412489">Paper </a></td> 
  <td> 480,193 </td> 
  <td>0.578 <span>&#177;</span> 0.020 </td> 
</tr>
<tr> 
  <td> 8 </td> 
  <td> AttentiveFP </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://pubmed.ncbi.nlm.nih.gov/31408336/">Paper </a></td> 
  <td> 300,806 </td> 
  <td>0.576 <span>&#177;</span> 0.025 </td> 
</tr>
</table>

<i class="fas fa-long-arrow-alt-up"></i>: The higher the better.