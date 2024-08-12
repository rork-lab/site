+++
title = "Showdata Shortcode"
description = "A brief description of a custom Shortcode for Zola that implements loading and displaying external data."
date = 2021-05-04
draft = false

[taxonomies]
tags = ["Features","Data","Shortcodes"]
[extra]
keywords = "Data, Load, External, Shortcodes"
toc = true
series = "Features"
+++

The `showdata` shortcode can load and display data from an external source via Zola's [load_data()](https://www.getzola.org/documentation/templates/overview/#load-data) function.

<!-- more -->

These are the parameters, currently all 3 are required.

- `src` path or url to file (if url, must include the http(s):// prefix).
- `type` the type of file to load. ([supported types](https://www.getzola.org/documentation/templates/overview/#load-data))
- `key` the field in the data that you want to display.

### Usage

This theme requires version &#123;&#123; showdata(src="../theme.toml" type="toml" key="min_version") &#125;&#125; or later of Zola.

### Output

This theme requires version {{ showdata(src="../theme.toml" type="toml" key="min_version") }} or later of Zola.

# Chart

## Line chart

Line chart displays series of data points in the form of lines. It can be used to show trend data, or comparison of different data sets.

**Code**

```
{%/* chart() */%}
{
  "type": "Line",
  "title": "Monthly income of an indie developer",
  "xLabel": "Month",
  "yLabel": "$ Dollars",
  "data": {
    "labels": ["1", "2", "3", "4", "5", "6", "7", "8", "9", "10"],
    "datasets": [
      {
        "label": "Plan",
        "data": [30, 70, 200, 300, 500, 800, 1500, 2900, 5000, 8000]
      },
      {
        "label": "Reality",
        "data": [0, 1, 30, 70, 80, 100, 50, 80, 40, 150]
      }
    ]
  }
}
{%/* end */%}
```

**Output**

{% chart() %}
{
  "type": "Line",
  "title": "Monthly income of an indie developer",
  "xLabel": "Month",
  "yLabel": "$ Dollars",
  "data": {
    "labels": ["1", "2", "3", "4", "5", "6", "7", "8", "9", "10"],
    "datasets": [
      {
        "label": "Plan",
        "data": [30, 70, 200, 300, 500, 800, 1500, 2900, 5000, 8000]
      },
      {
        "label": "Reality",
        "data": [0, 1, 30, 70, 80, 100, 50, 80, 40, 150]
      }
    ]
  }
}
{% end %}
