---
title: Home
layout: default
---

# visualisation
---

<textarea id="input" oninput="visdown()">

Make detailed visualisations

```vis
data:
  url: data/money.csv
  format:
    type: csv

transform:
  filter:
      field: Type
      equal: Notes

mark: area

encoding:
  x:
    timeUnit: year
    field: Year
    type: temporal
    axis:
      format: %Y
      labelAngle: 0
      title: Year
      titleFontSize: 14
  y:
    field: Value
    type: quantitative
    aggregate: sum
    axis:
      format: %
      title: Share of Notes
      titleFontSize: 14

  color:
    field: Currency
    type: nominal
    scale:
      range: ["#9087A8", "#BEA58A", "#819C74", "#AE8B80", "#E58275", "#958087", "#979B9B", "#AEA98E", "#EB8D8C"]

config:
  cell:
    width: 800
    height: 400
  mark:
    stacked: normalize
```

```vis
data:
  url: data/money.csv
  format:
    type: csv

transform:
  filter:
      field: Type
      equal: Notes

mark: area

encoding:
  x:
    timeUnit: year
    field: Year
    type: temporal
    axis:
      format: %Y
      labelAngle: 0
      title: Year
      titleFontSize: 14
  y:
    field: Quantity
    type: quantitative
    aggregate: sum
    axis:
      format: %
      title: Share of Notes
      titleFontSize: 14

  color:
    field: Currency
    type: nominal
    scale:
      range: ["#9087A8", "#BEA58A", "#819C74", "#AE8B80", "#E58275", "#958087", "#979B9B", "#AEA98E", "#EB8D8C"]

config:
  cell:
    width: 800
    height: 400
  mark:
    stacked: normalize
```


Another one

```vis
data:
  url: data/money.csv
  format:
    type: csv

transform:
  filter:
      field: Type
      equal: Notes

mark: area

encoding:
  x:
    timeUnit: year
    field: Year
    type: temporal
  y:
    aggregate: sum
    field: Value
    type: quantitative
  color:
    field: Currency
    type: nominal
    scale:
      range: ["#9087A8", "#BEA58A", "#819C74", "#AE8B80", "#E58275", "#958087", "#979B9B", "#AEA98E", "#EB8D8C"]

config:
  cell:
    width: 800
    height: 400
```

And one more

```vis
width: 960
height: 500
padding: 2.5
data:
- name: tree
  url: data/money.csv
  format:
    type: csv
  transform:
  - type: treemap
    field: size
    size:
    - 960
    - 500
scales:
- name: color
  type: ordinal
  range:
  - "#3182bd"
  - "#6baed6"
  - "#9ecae1"
  - "#c6dbef"
  - "#e6550d"
  - "#fd8d3c"
  - "#fdae6b"
  - "#fdd0a2"
  - "#31a354"
  - "#74c476"
  - "#a1d99b"
  - "#c7e9c0"
  - "#756bb1"
  - "#9e9ac8"
  - "#bcbddc"
  - "#dadaeb"
  - "#636363"
  - "#969696"
  - "#bdbdbd"
  - "#d9d9d9"
- name: size
  type: ordinal
  domain:
  - 0
  - 1
  - 2
  - 3
  range:
  - 256
  - 28
  - 20
  - 14
- name: opacity
  type: ordinal
  domain:
  - 0
  - 1
  - 2
  - 3
  range:
  - 0.15
  - 0.5
  - 0.8
  - 1
marks:
- type: rect
  from:
    data: tree
    transform:
    - type: filter
      test: datum.children
  interactive: false
  properties:
    enter:
      x:
        field: layout_x
      y:
        field: layout_y
      width:
        field: layout_width
      height:
        field: layout_height
      fill:
        scale: color
        field: name
- type: rect
  from:
    data: tree
    transform:
    - type: filter
      test: "!datum.children"
  properties:
    enter:
      x:
        field: layout_x
      y:
        field: layout_y
      width:
        field: layout_width
      height:
        field: layout_height
      stroke:
        value: "#fff"
    update:
      fill:
        value: rgba(0,0,0,0)
    hover:
      fill:
        value: red
- type: text
  from:
    data: tree
    transform:
    - type: filter
      test: datum.children
  interactive: false
  properties:
    enter:
      x:
        field: layout_x
      y:
        field: layout_y
      dx:
        field: layout_width
        mult: 0.5
      dy:
        field: layout_height
        mult: 0.5
      font:
        value: Helvetica Neue
      fontSize:
        scale: size
        field: depth
      align:
        value: center
      baseline:
        value: middle
      fill:
        value: "#000"
      fillOpacity:
        scale: opacity
        field: depth
      text:
        field: name

```



---
Handcrafted by [Amit Kapoor](http://amitkaps.com)

</textarea>
<section id="output"></section>
