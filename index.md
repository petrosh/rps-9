---
---
# Home
- [Actions](https://github.com/petrosh/rps-9/actions)
- [Workflow](https://github.com/petrosh/rps-9/blob/main/.github/workflows/rps-9.yml)
- [Turns](https://github.com/petrosh/rps-9/tree/main/_data/turns.csv)

|{% for p in site.data.rps_9.first %}{{ p[0] }}|{% endfor %}
|--:|{% for p in site.data.rps_9.first offset: 1 %}:--|{% endfor %}
{% for s in site.data.rps_9 %}|{% for p in s %}{% if forloop.index == 1 %}<img src="{{ p[1] }}">{% else %}{{ p[1] }}{% endif %}|{% endfor %}
{% endfor %}

<style>td img{max-height: 1.2em;}</style>

### Turns

{% for d in site.data.turns %}- {{ d | inspect }}
{% endfor %}
