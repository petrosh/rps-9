---
order: 1
---
# Symbols

> [Bolg post](https://trasparente.github.io/log/2023/02/18/rps-9/)

|{% for p in site.data.rps_9.first %}{{ p[0] }}|{% endfor %}
|--:|{% for p in site.data.rps_9.first offset: 1 %}:--:|{% endfor %}
{% for s in site.data.rps_9 %}|{% for p in s %}{%- assign p1 = p[1] -%}{% if p[0] == 'symbol' %}{%- include symbol.html url=p1 -%}{% elsif p[0] == 'win_over' %}{%- for win in p1 -%}{%- include symbol.html name=win -%}{%- endfor -%}{% else %}{{ p[1] }}{% endif %}|{% endfor %}
{% endfor %}

{% include widgets/view.html yml='rps_9' %}
