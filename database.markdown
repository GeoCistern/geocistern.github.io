---
layout: page
title: Database
permalink: /database/
order: 2
---

<head>
    <style type="text/css">
        h3 span {
            font-size: 36px;
        }
        .button-default{
          height: 30px;
          width: 30px;
          border: white;
          border-radius: 8px;
          margin: 3px;
          float: left;
          margin-bottom: 30px;
        }
        .search-box{
          width: 70%;
          float: left;
          padding: 10px;
          margin-bottom: 20px;
        }

        .filter-box{
          width: 25%;
          float: right;
          padding: 10px;
          margin-bottom: 20px;
          background-color: WhiteSmoke;
        }

        td {
          word-break: break-word;
        }

        dt {
          clear: left;
          color: darkolivegreen;
          float: left;
          font-weight: bold;
          text-align: right;
          width: 180px;
        }
        dd {
          margin: 0 0 0 190px;
          padding: 0 0 0.5em;
        }

        .extra-details {
          display: none;
        }

        tr:not(.extra-details) {
          cursor: pointer;
        }

    </style>
</head>
<body class="mt32">
    <div>
      <h3>
      <input type="text" id="seInput" class="search-box" onkeyup="myFunction(category.value)" placeholder="Search">
      </h3>

      <select name="category" id="category" class="filter-box">
        <option value="1">Author</option>
        <option value="3">Title</option>
      </select>
    </div>

    <div style="float:left;">
      <button type="button" class = "button-default"
      onclick="input('â')">â</button>
      <button type="button" class = "button-default"
      onclick="input('ç')">ç</button>
      <button type="button" class = "button-default"
      onclick="input('ğ')">ğ</button>
      <button type="button" class = "button-default"
      onclick="input('ı')">ı</button>  
      <button type="button" class = "button-default"
      onclick="input('İ')">İ</button>
      <button type="button" class = "button-default"
      onclick="input('î')">î</button>
      <button type="button" class = "button-default"
      onclick="input('ö')">ö</button>
      <button type="button" class = "button-default"
      onclick="input('ş')">ş</button>
      <button type="button" class = "button-default"
      onclick="input('ü')">ü</button>
      <button type="button" class = "button-default"
      onclick="input('û')">û</button>
      </div>
        <script>
          function input(e){
            var seInput = document.getElementById("seInput");
            seInput.value = seInput.value + e;
            document.getElementById("seInput").focus();
          }
        </script>

  <script>
    function showHideExtraDetails(row) {
      row.nextElementSibling.style.display = (row.nextElementSibling.style.display === "table-row") ? "none" : "table-row";
    }
  </script>

  <table id="myTable">
  {% for row in site.data.database_final %}

    {% if forloop.first %}
    <tr>
      {% for pair in row limit:6 %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    <tr onclick="showHideExtraDetails(this)">
    {% for pair in row limit:6 %}
      <td>{{ pair[1] | xml_escape }}</td>
    {% endfor %}
    </tr>

    <tr class="extra-details" data-author-id="{{ row["AUTHOR_ID"] }}">
      <td colspan="6">
        <dl>
          {% for pair in row offset:6 %}
            <dt>{{ pair[0] | xml_escape }}:</dt>
            <dd>{{ pair[1] | xml_escape }}</dd>
          {% endfor %}
        </dl>
      </td>
    </tr>

  {% endfor %}
  </table>


<!-- source : https://www.w3schools.com/howto/tryit.asp?filename=tryhow_js_filter_table -->
 <script>
 function myFunction(val) {
   var input, filter, table, tr, td, i, txtValue;
   input = document.getElementById("seInput");
   filter = input.value.toUpperCase();
   table = document.getElementById("myTable");
   tr = table.getElementsByTagName("tr");
   for (i = 0; i < tr.length; i++) {
     td = tr[i].getElementsByTagName("td")[val];
     if (td) {
       txtValue = td.textContent || td.innerText;
       if (txtValue.toUpperCase().indexOf(filter) > -1) {
         tr[i].style.display = "";
       } else {
         tr[i].style.display = "none";
       }
     }       
   }
 }
 </script>
