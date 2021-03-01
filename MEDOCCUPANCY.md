---
layout: none
---

## Medical Ward Occupancy API

This API serves the reported medical ward occupancy for each hospital.

Note 1 : RH & TSKH were reported as one entity in the original report. It will be reported as RH in this API because the AED is coded under RH.

Note 2 : NLTH does not have acute medical ward and thus reports as "undefined"

{% assign data = site.data.MEDOCCUPANCY | sort | reverse %}

There are in total {{ site.data.MEDOCCUPANCY | size }} entries in this API.

Below shows the last 10 entries in the API.

<table>
  {% for row in data | limit : 10 %}
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
