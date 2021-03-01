---
layout: none
---

## Medical Ward Occupancy API

This API serves the reported medical ward occupancy for each hospital.

Note 1 : RH & TSKH were reported as one entity in the original report. It will be reported as RH in this API because the AED is coded under RH.

Note 2 : NLTH does not have acute medical ward and thus reports as "undefined"

{% assign last_one = site.data.MEDOCCUPANCY | sort | last %}

There are in total {{ site.data.MEDOCCUPANCY | size }} entries in this API. The latest entry is

{{ last_one[1].DATE }}
