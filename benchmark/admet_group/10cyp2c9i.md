---
title: CYP2C9_Veith Leaderboard
subtitle:
layout: page
show_sidebar: false
menubar: lb_admet_group
hide_hero: true
---

<p class="is-size-3"><b><code>TDC.CYP2C9_Veith</code> Leaderboard</b></p>

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
    <td><a href="/single_pred_tasks/adme/#cyp-p450-2c9-inhibition-veith-et-al"> TDC.CYP2C9_Veith </a></td>
    <td>%</td>
    <td>12,092</td>
    <td>Binary</td>
    <td>AUPRC</td>
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
    <th onclick="sortTable(5, 'A', 'asc')">AUPRC <i class="fas fa-long-arrow-alt-up"></i> </th>
  </tr>
</thead>

<tr> 
  <td> 1 </td> 
  <td> XGBoost </td> 
  <td><a href="mailto:haot@smu.edu">Hao Tian</a></td> 
  <td><a href="https://github.com/smu-tao-group/ADMET_XGBoost"> GitHub</a>, <a href="https://arxiv.org/abs/2204.07532v2">Paper </a></td> 
  <td> 29 </td> 
  <td>0.794 <span>&#177;</span> 0.004 </td> 
</tr>
<tr> 
  <td> 2 </td> 
  <td> BaseBoosting </td> 
  <td><a href="mailto:andrew@oloren.ai">Andrew Li</a></td> 
  <td><a href="https://github.com/Oloren-AI/OCE-TDC/blob/main/submission.ipynb"> GitHub</a>, <a href="https://github.com/Oloren-AI/OCE-TDC/blob/main/submission.ipynb">Paper </a></td> 
  <td> 27 </td> 
  <td>0.791 <span>&#177;</span> 0.005 </td> 
</tr>
<tr> 
  <td> 3 </td> 
  <td> ColorRefinement + Weighted Ensemble LGBM </td> 
  <td><a href="mailto:parkerburchett@gmail.com">Parker Burchett</a></td> 
  <td><a href="https://github.com/parkerburchett/TDC-DeepLearning/blob/main/modeling/CYP%20Weighted%20Model.ipynb"> GitHub</a>, <a href="No paper">Paper </a></td> 
  <td> 68 </td> 
  <td>0.767 <span>&#177;</span> 0.003 </td> 
</tr>
<tr> 
  <td> 4 </td> 
  <td> AttentiveFP </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://pubmed.ncbi.nlm.nih.gov/31408336/">Paper </a></td> 
  <td> 300,806 </td> 
  <td>0.749 <span>&#177;</span> 0.004 </td> 
</tr>
<tr> 
  <td> 5 </td> 
  <td> RDKit2D + MLP (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 633,409 </td> 
  <td>0.742 <span>&#177;</span> 0.006 </td> 
</tr>
<tr> 
  <td> 6 </td> 
  <td> NeuralFP </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://ieeexplore.ieee.org/document/9412489">Paper </a></td> 
  <td> 480,193 </td> 
  <td>0.739 <span>&#177;</span> 0.010 </td> 
</tr>
<tr> 
  <td> 7 </td> 
  <td> GCN </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://arxiv.org/abs/1609.02907">Paper </a></td> 
  <td> 191,810 </td> 
  <td>0.735 <span>&#177;</span> 0.004 </td> 
</tr>
<tr> 
  <td> 8 </td> 
  <td> Morgan + MLP (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 1,477,185 </td> 
  <td>0.715 <span>&#177;</span> 0.004 </td> 
</tr>
<tr> 
  <td> 9 </td> 
  <td> CNN (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 226,625 </td> 
  <td>0.713 <span>&#177;</span> 0.006 </td> 
</tr>


</table>

<i class="fas fa-long-arrow-alt-up"></i>: The higher the better.