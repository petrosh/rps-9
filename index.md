---
---
# Home
- [Actions](https://github.com/petrosh/rps-9/actions)
- [Workflow](https://github.com/petrosh/rps-9/blob/main/.github/workflows/rps-9.yml)
- [Turns](https://github.com/petrosh/rps-9/tree/main/_data/turns.csv)

{% for d in site.data.turns %}- {{ d | inspect }}
{% endfor %}

{% for s in site.data.rps_9 %}- {{ s | inspect }}
{% endfor %}
