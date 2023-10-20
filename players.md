---
order: 1
---
# Players

|name|{% for dice in (1..6) %}{{ dice }}|{% endfor %}
|--:|{% for dice in (1..6) %}:--:|{% endfor %}
{% for p in site.data.players %}|{{ p[0] | capitalize }}|{% for j in p[1] %}{%- include symbol.html name=j -%}|{% endfor %}
{% endfor %}

{% include widgets/view.html yml='players' title='_data/players.yml' %}