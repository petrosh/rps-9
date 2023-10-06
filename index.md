---
rps_9:
  - symbol:🪨
    name: Rock
  - symbol: 🧻
    name: Paper
  - symbol: ✂️
    name: Scissors
  - symbol: 🔥
    name: Fire
  - symbol: 💦
    name: Water
  - symbol: 🌬️
    name: Air
  - symbol 🧽
    name: Sponge
  - symbol: 🔫
    name: Laser
  - symbol: 🧠
    name: Brain
---
# Home
- [Actions](https://github.com/petrosh/rps-9/actions)
- [Workflow](https://github.com/petrosh/rps-9/blob/main/.github/workflows/rps-9.yml)
- [Turns](https://github.com/petrosh/rps-9/tree/main/_data/turns.csv)

{% for d in site.data.turns %}- {{ d | inspect }}
{% endfor %}

{% for s in page.rps_9 %}- {{ s | inspect }}
{% endfor %}
