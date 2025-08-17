---
id: crossroads
title: The Crossroads
set:
  stats:
    experience: "+1"
options:
  - text: Go into the forest
    next: forest
    set:
      stats:
        experience: "+1"
  - text: Explore the ruins
    next: ruins
    set:
      stats:
        experience: "+1"
---

You stand at a crossroads in a mysterious land, where three paths diverge before you. Each path seems to lead to a different kind of adventure, and you can feel the weight of choice pressing down upon you.

The forest path leads into a dense, ancient woodland where the trees seem to whisper secrets to each other. The ruins path leads to crumbling stone structures that speak of civilizations long forgotten. And the third path leads to a mysterious valley that seems to shimmer with an otherworldly light.

{{#history "forest"}}
**You've been to the forest before**, and you know the secrets that lie within its ancient groves.
{{/history}}

{{#history "ruins"}}
**You've explored the ruins before**, and you're familiar with their mysterious chambers and hidden treasures.
{{/history}}

Each path calls to you in its own way, promising adventure, discovery, and perhaps even transformation. The choice you make here will shape not just your immediate journey, but potentially the course of your entire adventure.

What path will you choose? 