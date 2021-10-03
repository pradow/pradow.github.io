---
title: "Iterate With Index Value in Hugo"
date: 2021-10-03T10:14:08-07:00
draft: false
author: "pradow"
category: "hugo"
image: "/images/forest.jpg"
---

When using hugo to loop through data an index variable can be added using the following syntax

{{< highlight go "linenos=table,hl_lines=8 15-17,linenostart=1">}}

{{ range $index, $projects := .Site.Data.home.projects }}

{{< / highlight >}}

We can then use the index variable within the loop to add conditionals based on the current iteration

{{< highlight go "linenos=table,hl_lines=8 15-17,linenostart=1">}}

{{ range $index, $projects := .Site.Data.home.projects }}
<a class="{{ if eq $index 0}}first-item{{ end }} grid-item" href="{{ .url }}">
    <div class="image-container" style="background-image: url({{ .image }})"></div>
    <div class="info">
        <h6 class="item-title">{{ .title }}</h6>
        <div class="item-icon">
            {{ partial "svg.html" . }}
        </div>
    </div>
</a>
{{ end }}

{{< / highlight >}}
