---
layout: none
---

## Pediatric Ward Occupancy API

This API serves the reported pediatric ward occupancy for each hospital.

Pediatric was occupancy is newly included since Feb 2019

{% assign data = site.data.PEDOCCUPANCY | sort | reverse %}

There are in total {{ site.data.PEDOCCUPANCY | size }} entries in this API.

Below shows the last 10 entries in the API.

<table>
  {% for row in data | limit : 20 %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>
