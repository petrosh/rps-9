---
players: [tizio,caio,sempronio]
order: 2
---
# Classic 🏆️

The most classic of the cups.

{% include players.html players=page.players %}

## Match

```liquid
{% raw %}{% include match.html players=page.players %}{% endraw %}
```

{% include match.html players=page.players %}