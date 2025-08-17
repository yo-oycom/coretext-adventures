---
id: deep_ruins
title: The Heart of the Ruins
set:
  stats:
    experience: "+3"
    wisdom: "+2"
  types:
    Role:
      explorer: "+2"
      druid: "+1"
options:
  - text: Continue deeper
    next: spirit
    set:
      stats:
        experience: "+2"
        wisdom: "+1"
      types:
        Role:
          explorer: "+1"
          druid: "+1"
  - text: Return to the main ruins
    next: ruins
    set:
      stats:
        experience: "+1"
---

You've ventured into the deepest chambers of the ancient ruins, where the air is thick with the weight of forgotten knowledge. The stone walls here are covered in intricate carvings and symbols that seem to pulse with a subtle, otherworldly light.

{{#visited "deep_ruins"}}
**You've explored these depths before**, and the familiar patterns in the stonework bring back memories of your previous discoveries.
{{/visited}}

The deeper chambers reveal the true purpose of this ancient structure. This was once a place of great learning and power, where scholars and mystics gathered to study the secrets of the universe. The carvings on the walls tell stories of cosmic forces, elemental magic, and the fundamental laws that govern reality itself.

{{#trait "Role" "=" "explorer"}}
Your explorer's expertise helps you decipher the complex patterns and understand the layout of these sacred chambers.
{{/trait}}

{{#trait "Role" "=" "druid"}}
Your druidic knowledge allows you to recognize the ancient magical symbols and understand their significance.
{{/trait}}

At the center of the deepest chamber, you find a circular platform surrounded by twelve stone pillars. Each pillar is carved with different symbols representing the fundamental forces of nature. The air here crackles with energy, and you can feel the power that once flowed through this place.

{{#trait "Role" "=" "explorer"}}
Your exploration skills reveal hidden mechanisms and secret passages that others might miss.
{{/trait}}

{{#trait "Role" "=" "druid"}}
Your magical senses detect that this platform was once used for powerful rituals and ceremonies.
{{/trait}}

What do you do next? 