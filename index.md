---
rps_9:
  -
    symbol: https://github.githubassets.com/images/icons/emoji/unicode/1faa8.png?v8
    name: Rock
  -
    symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f9fb.png?v8
    name: Paper
  -
    symbol: https://github.githubassets.com/images/icons/emoji/unicode/2702.png?v8
    name: Scissors
  -
    symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f525.png?v8
    name: Fire
  -
    symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f4a6.png?v8
    name: Water
  -
    symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f32c.png?v8
    name: Air
  -
    symbol https://github.githubassets.com/images/icons/emoji/unicode/1f9fd.png?v8
    name: Sponge
  -
    symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f52b.png?v8
    name: Laser
  -
    symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f9e0.png?v8
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
