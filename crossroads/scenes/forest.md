---
id: forest
title: The Ancient Forest
set:
  stats:
    experience: "+2"
    wisdom: "+1"
  types:
    Role:
      druid: "+1"
      explorer: "+1"
options:
  - text: Continue deeper into the forest
    next: spirit
    set:
      stats:
        experience: "+2"
        wisdom: "+1"
      types:
        Role:
          druid: "+1"
          explorer: "+1"
  - text: Return to the crossroads
    next: crossroads
    set:
      stats:
        experience: "+1"
---

The ancient forest surrounds you with its towering trees and mysterious atmosphere. The air is thick with the scent of earth and growth, and you can hear the gentle rustling of leaves and the distant calls of forest creatures.

{{#history "forest"}}
**You've walked these paths before**, and the familiar sights and sounds bring back memories of your previous journey through these woods.
{{/history}}

{{#trait "Role" "=" "druid"}}
Your druidic senses immediately connect with the natural energy flowing through this forest, feeling the ancient magic that has protected these groves for centuries.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
Your explorer's instincts help you navigate the complex network of paths and identify the most promising routes deeper into the forest.
{{/trait}}

The forest seems to be alive with its own consciousness, its ancient trees standing as silent guardians of secrets that have been kept safe for generations. You can feel the weight of history pressing down upon you, and you sense that this place holds knowledge that few mortals have ever been privileged to receive.

{{#trait "Role" "=" "druid"}}
Your connection to nature allows you to understand the forest's rhythms and recognize the signs that point toward its most sacred places.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
Your exploration skills reveal hidden paths and secret clearings that others might miss, leading you toward the heart of the forest's mysteries.
{{/trait}}

What do you do next? 