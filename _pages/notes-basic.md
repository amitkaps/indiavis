---
title: Notes - Starter
layout: visdown
permalink: notes-starter
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
    aggregate: sum
    field: money
    type: quantitative
    axis:
      title: Notes in Circulation (Value ₹ Billions)
      titleFontSize: 12
  color:
    field: denom
    type: nominal
    scale:
      range: category10

config:
  cell:
    width: 600
    height: 400
```

</textarea>
