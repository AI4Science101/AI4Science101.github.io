---
layout: page
title: TDC Datasets
toc: false
toc_title: 
show_sidebar: false
hide_hero: true
---

# Overview of TDC Datasets

<div class="container">
        <div class="columns is-vcentered">
            <div class="column is-7">
                  <p class="is-size-5">At its core, TDC collects ML tasks and associated datasets across therapeutic modalities and stages of discovery. These tasks and datasets have the following properties:</p>
                  <ul class="is-size-5">
                     <li><strong>Instrumenting disease treatment from bench to bedside with AI/ML</strong>: TDC covers a variety of learning tasks going from wet-lab target identification to biomedical product manufacturing.</li>
                     <li><strong>Building off the latest biotechnological platforms</strong>: TDC is regularly updated with novel datasets and tasks, such as antibody therapeutics and gene editing. </li>   
                     <li><strong>Providing AI/ML-ready datasets</strong>: TDC datasets provide rich information on biomedical entities. This information is carefully curated, processed, and readily available in TDC. </li>
                  </ul>
            </div>
            <div class="column is-5 has-text-centered">
                <img src="{{ "/img/tdc_overview2.png" | relative_url }}" alt="TDC logo" class="img-responsive">
            </div>
        </div>
    </div>
    
<div class="column is-12">
    <hr />
</div>

# Machine Learning Tasks in TDC

<p class="is-size-5"> ML tasks cover a range of therapeutic modalities, including small molecules and biologics, including antibodies, peptides, miRNAs, and gene editing therapies. They also map to drug discovery and development pipelines:</p>
<ul class="is-size-5">
    <li><strong>Target discovery:</strong> Tasks to identify candidate drug targets.</li>
    <li><strong>Activity modeling:</strong> Tasks to screen and generate individual or combinatorial candidates with high binding activity towards targets.</li>
    <li><strong>Efficacy and safety:</strong> Tasks to optimize therapeutic signatures indicative of drug safety and efficacy.  </li>
    <li><strong>Manufacturing:</strong> Tasks in support of synthesis and manufacturing of therapeutics.</li>
  </ul>

<!-- <p class="is-size-5"> Following is a summary table of TDC learning tasks. <strong>Click the tag for the AI task of interest to explore the underlying datasets.</strong> </p> -->

<div class="column is-12">

<table class = "table is-fullwidth is-hoverable">
  <col>
  <colgroup span="3"></colgroup>
  <colgroup span="4"></colgroup>
  <tr>
    <td rowspan="2" style="vertical-align:middle;"><strong><i>ML Tasks</i></strong></td>
    <th colspan="3" scope="colgroup" style="text-align:center;"><i>Therapeutic Modalities</i></th>
    <th colspan="4" scope="colgroup" style="text-align:center;"><i>Stages of Discovery and Development</i></th>
  </tr>
  <tr>
    <th scope="col" style="text-align:center;">Small Molecules</th>
    <th scope="col" style="text-align:center;">MacroMolecules</th>
    <th scope="col" style="text-align:center;">Cell & Gene Therapy</th>
    <th scope="col" style="text-align:center;">Target Discovery</th>
    <th scope="col" style="text-align:center;">Activity Modeling</th>
    <th scope="col" style="text-align:center;">Efficacy & Safety</th>
    <th scope="col" style="text-align:center;">Manufacturing</th>
  </tr>
  <tr>
    <th scope="row"><a href="/single_pred_tasks/adme"><code>ADME</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/single_pred_tasks/tox"><code>Tox</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/single_pred_tasks/hts"><code>HTS</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/single_pred_tasks/qm"><code>QM</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/single_pred_tasks/yields"><code>Yields</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
  </tr>
  <!---
  <tr>
    <th scope="row"><a href="/single_pred_tasks/paratope"><code>Paratope</code></a></th>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  -->
  <tr>
    <th scope="row"><a href="/single_pred_tasks/epitope"><code>Epitope</code></a></th>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/single_pred_tasks/develop"><code>Develop</code></a></th>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/single_pred_tasks/CRISPROutcome"><code>CRISPROutcome</code></a></th>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/dti"><code>DTI</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/ddi"><code>DDI</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/ppi"><code>PPI</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/gdi"><code>GDA</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/drugres"><code>DrugRes</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/drugsyn"><code>DrugSyn</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/peptidemhc"><code>PeptideMHC</code></a></th>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/antibodyaff"><code>AntibodyAff</code></a></th>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/mti"><code>MTI</code></a></th>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/multi_pred_tasks/catalyst"><code>Catalyst</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
  </tr>
  <tr>
    <th scope="row"><a href="/generation_tasks/molgen"><code>MolGen</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
  </tr>
  <tr>
    <th scope="row"><a href="/generation_tasks/retrosyn"><code>RetroSyn</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
  </tr>
  <tr>
    <th scope="row"><a href="/generation_tasks/Reaction"><code>Reaction</code></a></th>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"></td>
    <td style="text-align:center;"><span class="icon"><i class="fas fa-check"></i></span></td>
  </tr>

</table>

<p class="is-size-5">
  TDC also maintains a list of <a href="/resources/overview">external data resources in therapeutic science.</a>
</p>

<div class="column is-12">
    <hr />
</div>


<p class="is-size-3 has-text-centered"> <strong> Explore TDC Datasets </strong> </p>

<div class="container">
        <div class="columns is-vcentered is-size-5">
            <div class="column is-4 has-text-centered"> <a href="/single_pred_tasks/overview" class="box has-background-info has-text-white">Single-instance Prediction</a></div>
            <div class="column is-4 has-text-centered"> <a href="/multi_pred_tasks/overview" class="box has-background-info has-text-white">Multi-instance Prediction</a></div>
            <div class="column is-4 has-text-centered"> <a href="/generation_tasks/overview" class="box has-background-info has-text-white">Generation</a></div>
        </div>
</div>