---
rps_9:
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/1faa8.png?v8
  name: Rock
  win_over: [Fire,Scissors,Brain,Sponge]
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f9fb.png?v8
  name: Paper
  win_over: [Air,Rock,Water,Laser]
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/2702.png?v8
  name: Scissors
  win_over: [Air,Paper,Brain,Sponge]
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f525.png?v8
  name: Fire
  win_over: [Scissors,Paper,Brain,Sponge]
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f4a6.png?v8
  name: Water
  win_over: [Rock,Fire,Scissors,Laser]
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f32c.png?v8
  name: Air
  win_over: [Fire,Rock,Water,Laser]
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f9fd.png?v8
  name: Sponge
  win_over: [Paper,Air,Water,Laser]
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f52b.png?v8
  name: Laser
  win_over: [Rock,Fire,Scissors,Brain]
- symbol: https://github.githubassets.com/images/icons/emoji/unicode/1f9e0.png?v8
  name: Brain
  win_over: [Sponge,Paper,Air,Water]
dice: [Brain,Brain,Paper,Paper,Rock,Rock]
diceb: [Laser,Laser,Sponge,Sponge,Scissors,Scissors]
dicet: [Water,Water,Air,Air,Fire,Fire]
---
# Home
- [Actions](https://github.com/petrosh/rps-9/actions)
- [Workflow](https://github.com/petrosh/rps-9/blob/main/.github/workflows/rps-9.yml)
- [Turns](https://github.com/petrosh/rps-9/tree/main/_data/turns.csv)

|{% for p in page.rps_9.first %}{{ p[0] }}|{% endfor %}
|--:|{% for p in page.rps_9.first offset: 1 %}:--|{% endfor %}
{% for s in page.rps_9 %}|{% for p in s %}{% if forloop.index == 1 %}<img src="{{ p[1] }}">{% else %}{{ p[1] }}{% endif %}|{% endfor %}
{% endfor %}

{% assign points_dice = 0 %}
{% assign points_diceb = 0 %}
{% assign points_dicet = 0 %}
|Turn|Date|Philosophy|Science|Spirit|
|:--:|:--:|:--:|:--:|:--:|
{% for run in site.data.turns %}|{{ run.run }}|<time datetime='{{ run.unix | date_to_rfc822 }}'></time>|
{%- assign d6_dice = run.dice | minus: 1 -%}
{%- assign play_dice = page.rps_9 | where: 'name', page.dice[d6_dice] -%}
<img src='{{ play_dice | map: 'symbol' }}' title='{{ run.dice }}'>{%- assign name_dice = play_dice | map: 'name' -%}
{%- assign win_over_dice = play_dice | map: 'win_over' -%}
{%- assign win_dice = 0 -%}
{%- assign d6_diceb = run.diceb | minus: 1 -%}
{%- assign play_diceb = page.rps_9 | where: 'name', page.diceb[d6_diceb] -%}
{%- assign name_diceb = play_diceb | map: 'name' -%}
{%- assign win_over_diceb = play_diceb | map: 'win_over' -%}
{%- assign win_diceb = 0 -%}
{%- assign d6_dicet = run.dicet | minus: 1 -%}
{%- assign play_dicet = page.rps_9 | where: 'name', page.dicet[d6_dicet] -%}
{%- assign name_dicet = play_dicet | map: 'name' -%}
{%- assign win_over_dicet = play_dicet | map: 'win_over' -%}
{%- assign win_dicet = 0 -%}
{%- if win_over_dice[0] contains name_diceb[0] -%}{% assign win_dice = win_dice | plus: 1 %}<br>beat Science{%- endif -%}{%- if win_over_dice[0] contains name_dicet[0] -%}{% assign win_dice = win_dice | plus: 1 %}<br>beat Spirit{%- endif -%}<br>{%- assign points_dice = points_dice | plus: win_dice -%}{{ points_dice }} points|<img src='{{ play_diceb | map: 'symbol' }}' title='{{ run.diceb }}'>{%- if win_over_diceb[0] contains name_dice[0] -%}{% assign win_diceb = win_diceb | plus: 1 %}<br>beat Philosophy{%- endif -%}{%- if win_over_diceb[0] contains name_dicet[0] -%}{% assign win_diceb = win_diceb | plus: 1 %}<br>beat Spirit{%- endif -%}{%- assign points_diceb = points_diceb | plus: win_diceb -%}<br>{{ points_diceb }} points|<img src='{{ play_dicet | map: 'symbol' }}' title='{{ run.dicet }}'>{%- if win_over_dicet[0] contains name_dice[0] -%}{% assign win_dicet = win_dicet | plus: 1 %}<br>beat Philosophy{%- endif -%}{%- if win_over_dicet[0] contains name_diceb[0] -%}{% assign win_dicet = win_dicet | plus: 1 %}<br>beat Science{%- endif -%}<br>{%- assign points_dicet = points_dicet | plus: win_dicet -%}{{ points_dicet }} points|
{% endfor %}{: data-sort='desc'}

{% include widgets/view.html csv='turns' sort='desc' %}

<style>td img{max-height: 1.2em;}</style>
