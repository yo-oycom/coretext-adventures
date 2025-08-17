---
id: ruins
title: Ancient Ruins
set:
  stats:
    experience: "+2"
    wisdom: "+1"
  types:
    Role:
      explorer: "+1"
      druid: "+1"
options:
  - text: Explore deeper into the ruins
    next: deep_ruins
    set:
      stats:
        experience: "+2"
      types:
        Role:
          explorer: "+1"
  - text: Return to the crossroads
    next: crossroads
    set:
      stats:
        wisdom: "+1"
---

The ancient ruins stand before you, their weathered stones telling stories of civilizations long forgotten. The air is thick with the weight of history, and you can feel the echoes of the past all around you.

{{#history "ruins"}}
**You've been here before**, and the familiar layout brings back memories of your previous exploration.
{{/history}}

{{#trait "Role" "=" "explorer"}}
Your explorer's instincts are immediately drawn to the deeper chambers, where the most interesting discoveries likely await.
{{/trait}}

{{#trait "Role" "=" "druid"}}
Your druidic senses detect ancient magic lingering in these stones, remnants of the power that once flowed through this place.
{{/trait}}

The ruins are more extensive than they appeared from the outside. You can see several chambers leading deeper into the structure, each one potentially holding secrets and treasures from the past. The stonework is remarkably well-preserved, suggesting that this was once a place of great importance.

{{#trait "Role" "=" "explorer"}}
Your exploration skills help you navigate the complex layout, identifying the most promising areas to investigate.
{{/trait}}

{{#trait "Role" "=" "druid"}}
Your connection to ancient magic allows you to sense the purpose of different chambers, understanding their original function.
{{/trait}}

What do you do next? 