---
title: Notes - Stacked
layout: visdown
permalink: notes-stacked
---

<section id="output"></section>

<textarea id="input" oninput="visdown()">

```vis
data:
  url: data/notes.csv
  format:
    type: csv

mark: area

encoding:
  x:
    timeUnit: year
    field: year
    type: temporal
    axis:
      format: %Y
      labelAngle: 0
      title: Year
      titleFontSize: 12
  y:
    field: money
    type: quantitative
    aggregate: sum
    axis:
      format: %
      title: Share of Notes (by Value)
      titleFontSize: 12

  color:
    field: denom
    type: nominal
    scale:
      range: category10

config:
  cell:
    width: 650
    height: 500
  mark:
    stacked: normalize
```


</textarea>
