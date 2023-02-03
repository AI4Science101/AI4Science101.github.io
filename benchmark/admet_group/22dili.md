---
title: DILI Leaderboard
subtitle:
layout: page
show_sidebar: false
menubar: lb_admet_group
hide_hero: true
---

<p class="is-size-3"><b><code>TDC.DILI</code> Leaderboard</b></p>

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
    <td><a href="/single_pred_tasks/tox/#dili-drug-induced-liver-injury"> TDC.DILI </a></td>
    <td>%</td>
    <td>475</td>
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
  <td> BaseBoosting </td> 
  <td><a href="mailto:andrew@oloren.ai">Andrew Li</a></td> 
  <td><a href="https://github.com/Oloren-AI/OCE-TDC"> GitHub</a>, <a href="https://github.com/Oloren-AI/OCE-TDC/blob/main/Report.pdf">Paper </a></td> 
  <td> 23 </td> 
  <td>0.937 <span>&#177;</span> 0.004 </td> 
</tr>
<tr> 
  <td> 2 </td> 
  <td> XGBoost </td> 
  <td><a href="mailto:haot@smu.edu">Hao Tian</a></td> 
  <td><a href="https://github.com/smu-tao-group/ADMET_XGBoost"> GitHub</a>, <a href="https://arxiv.org/abs/2204.07532v2">Paper </a></td> 
  <td> 29 </td> 
  <td>0.933 <span>&#177;</span> 0.011 </td> 
</tr>
<tr> 
  <td> 3 </td> 
  <td> AttrMasking </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://arxiv.org/abs/1905.12265">Paper </a></td> 
  <td> 2,067,053 </td> 
  <td>0.919 <span>&#177;</span> 0.008 </td> 
</tr>
<tr> 
  <td> 4 </td> 
  <td> SimGCN </td> 
  <td><a href="mailto:suman@katanagraph.com">Suman Kalyan Bera</a></td> 
  <td><a href="https://github.com/KatanaGraph/SimGCN-TDC"> GitHub</a>, <a href="https://github.com/KatanaGraph/SimGCN-TDC/blob/main/Report_SimGCN_for_TDC_Benchmarks.pdf">Paper </a></td> 
  <td> 1,103,000 </td> 
  <td>0.909 <span>&#177;</span> 0.011 </td> 
</tr>
<tr> 
  <td> 5 </td> 
  <td> AttentiveFP </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://pubmed.ncbi.nlm.nih.gov/31408336/">Paper </a></td> 
  <td> 300,806 </td> 
  <td>0.886 <span>&#177;</span> 0.015 </td> 
</tr>
<tr> 
  <td> 6 </td> 
  <td> RDKit2D + MLP (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 633,409 </td> 
  <td>0.875 <span>&#177;</span> 0.019 </td> 
</tr>
<tr> 
  <td> 7 </td> 
  <td> ContextPred </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://arxiv.org/abs/1905.12265">Paper </a></td> 
  <td> 2,067,053 </td> 
  <td>0.861 <span>&#177;</span> 0.018 </td> 
</tr>
<tr> 
  <td> 8 </td> 
  <td> GCN </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://arxiv.org/abs/1609.02907">Paper </a></td> 
  <td> 191,810 </td> 
  <td>0.859 <span>&#177;</span> 0.033 </td> 
</tr>
<tr> 
  <td> 9 </td> 
  <td> NeuralFP </td> 
  <td><a href="mailto:kexinh@stanford.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/main/examples/single_pred/admet"> GitHub</a>, <a href="https://ieeexplore.ieee.org/document/9412489">Paper </a></td> 
  <td> 480,193 </td> 
  <td>0.851 <span>&#177;</span> 0.026 </td> 
</tr>
<tr> 
  <td> 10 </td> 
  <td> Morgan + MLP (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 1,477,185 </td> 
  <td>0.832 <span>&#177;</span> 0.021 </td> 
</tr>
<tr> 
  <td> 11 </td> 
  <td> CNN (DeepPurpose) </td> 
  <td><a href="mailto:kexinhuang@hsph.harvard.edu">Kexin Huang</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/single_pred/admet"> GitHub</a>, <a href="https://doi.org/10.1093/bioinformatics/btaa1005">Paper </a></td> 
  <td> 226,625 </td> 
  <td>0.792 <span>&#177;</span> 0.016 </td> 
</tr>

</table>

<i class="fas fa-long-arrow-alt-up"></i>: The higher the better.