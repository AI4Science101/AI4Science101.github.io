---
title: DrugComb_CSS Leaderboard
subtitle:
layout: page
show_sidebar: false
menubar: lb_drugcombo_group
hide_hero: true
---

<p class="is-size-3"><b><code>TDC.DrugComb_CSS</code> Leaderboard</b></p>

### Dataset Summary

<table class="table is-striped is-hoverable">
  <thead>
  <tr>
    <th>Label</th>
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
    <th onclick="sortTable(5, 'A', 'asc')">MAE</th>
  </tr>
</thead>
  <tr> 
  <td> 1 </td> 
  <td> MLP </td> 
  <td><a href="mailto:yroohani@stanford.edu">Yusuf Roohani</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/multi_pred/drugcombo"> GitHub</a>, <a href="https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-018-2509-3">Paper </a></td> 
  <td> 7,141,297 </td> 
  <td>16.858 <span>&#177;</span> 0.005 </td> 
</tr>
</table>

<div class="column is-12">
    <hr />
</div>

### Performance Across Tissues

<p class="is-size-5">For this leaderboard, an automatic stratified evaluation on performance across various tissue types on the test set is generated. These scores are intended to examine if a model favors towards certain tissue types. An ideal model should perform equally well across all tissue types.</p>

<table class="table is-striped is-hoverable">
  <thead>
  <tr>
    <th>Tissue</th>
    <th>Label</th>
    <th># of Cell Lines</th>
    <th>Test Set Size</th>
    <th>Metric</th>
  </tr>
  </thead>
  <tr>
    <td>Kidney</td>
    <td>CSS</td>
    <td>8</td>
    <td>8,096</td>
    <td>MAE</td>
  </tr>
  <tr>
    <td>Lung</td>
    <td>CSS</td>
    <td>9</td>
    <td>9,108</td>
    <td>MAE</td>
  </tr>
  <tr>
    <td>Breast</td>
    <td>CSS</td>
    <td>5</td>
    <td>20,551</td>
    <td>MAE</td>
  </tr>
  <tr>
    <td>Hema</td>
    <td>CSS</td>
    <td>6</td>
    <td>6,072</td>
    <td>MAE</td>
  </tr>
  <tr>
    <td>Prostate</td>
    <td>CSS</td>
    <td>2</td>
    <td>2,024</td>
    <td>MAE</td>
  </tr>
  <tr>
    <td>Ovary</td>
    <td>CSS</td>
    <td>7</td>
    <td>7,084</td>
    <td>MAE</td>
  </tr>
  <tr>
    <td>Skin</td>
    <td>CSS</td>
    <td>9</td>
    <td>9,108</td>
    <td>MAE</td>
  </tr>
  <tr>
    <td>Brain</td>
    <td>CSS</td>
    <td>6</td>
    <td>6,072</td>
    <td>MAE</td>
  </tr>
  <tr>
    <td>Colon</td>
    <td>CSS</td>
    <td>7</td>
    <td>7,084</td>
    <td>MAE</td>
  </tr>
</table>

<div class="column is-12">
    <hr />
</div>

### Leaderboard on Performances Across Tissues

<table class="table is-striped is-hoverable" id="A">
  <thead>
  <tr>
   <!--When a header is clicked, run the sortTable function, with a parameter, 0 for sorting by names, 1 for sorting by country:-->  
    <th>Rank</th>
    <th>Model</th>
    <th>Contact</th>
    <th>Link</th>
    <th>#Params</th>
    <th onclick="sortTable(5, 'A', 'asc')">Kidney <i class="fas fa-sort"></i> </th>
    <th onclick="sortTable(6, 'A', 'asc')">Lung <i class="fas fa-sort"></i></th>
    <th onclick="sortTable(7, 'A', 'asc')">Breast <i class="fas fa-sort"></i></th>
    <th onclick="sortTable(8, 'A', 'asc')">Hema <i class="fas fa-sort"></i></th>
  </tr>
</thead>
  <tr> 
  <td> 1 </td> 
  <td> MLP </td> 
  <td><a href="mailto:yroohani@stanford.edu">Yusuf Roohani</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/multi_pred/drugcombo"> GitHub</a>, <a href="https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-018-2509-3">Paper </a></td> 
  <td> 7,141,297 </td> 
  <td>14.570 <span>&#177;</span> 0.003 </td> 
  <td>15.653 <span>&#177;</span> 0.017 </td> 
  <td>13.432 <span>&#177;</span> 0.049 </td> 
  <td>28.764 <span>&#177;</span> 0.201 </td> 
</tr>

</table>


<table class="table is-striped is-hoverable" id="A">
  <thead>
  <tr>
   <!--When a header is clicked, run the sortTable function, with a parameter, 0 for sorting by names, 1 for sorting by country:-->  
    <th>Rank</th>
    <th>Model</th>
    <th>Contact</th>
    <th>Link</th>
    <th>#Params</th>
    <th onclick="sortTable(5, 'A', 'asc')">Prost. <i class="fas fa-sort"></i></th>
    <th onclick="sortTable(6, 'A', 'asc')">Ovary <i class="fas fa-sort"></i></th>
    <th onclick="sortTable(7, 'A', 'asc')">Skin <i class="fas fa-sort"></i></th>
    <th onclick="sortTable(8, 'A', 'asc')">Brain <i class="fas fa-sort"></i></th>
    <th onclick="sortTable(9, 'A', 'asc')">Colon <i class="fas fa-sort"></i></th>
  </tr>
</thead>
  <tr> 
  <td> 1 </td> 
  <td> MLP </td> 
  <td><a href="mailto:yroohani@stanford.edu">Yusuf Roohani</a></td> 
  <td><a href="https://github.com/mims-harvard/TDC/tree/master/examples/multi_pred/drugcombo"> GitHub</a>, <a href="https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-018-2509-3">Paper </a></td> 
  <td> 7,141,297 </td> 
  <td>15.692 <span>&#177;</span> 0.005 </td> 
  <td>15.263 <span>&#177;</span> 0.041 </td> 
  <td>15.663 <span>&#177;</span> 0.065 </td> 
  <td>15.694 <span>&#177;</span> 0.006 </td> 
  <td>17.729 <span>&#177;</span> 0.042 </td> 
</tr>
</table>

<i class="fas fa-sort"></i>: Click to sort models for specific benchmark column.



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
