---
id: temple
title: The Ancient Temple
set:
  stats:
    experience: "+2"
    knowledge: "+1"
  types:
    Role:
      investigator: "+1"
      rescuer: "+1"
      explorer: "+1"
options:
  - text: Explore the temple chambers
    next: choice
    set:
      stats:
        experience: "+2"
        knowledge: "+1"
      types:
        Role:
          investigator: "+1"
          explorer: "+1"
  - text: Return to the valley
    next: valley
    set:
      stats:
        experience: "+1"
---

The ancient temple rises before you, its weathered stone walls telling stories of civilizations long forgotten. The architecture is unlike anything you've ever seen, with intricate carvings and symbols that seem to pulse with a subtle, otherworldly light.

The temple appears to be dedicated to some kind of ancient wisdom or knowledge, with its walls covered in hieroglyphs and mystical symbols. The air is thick with the weight of history, and you can feel the echoes of the past all around you.

{{#trait "Role" "=" "investigator"}}
Your analytical mind immediately begins studying the temple's structure and the symbols on its walls, looking for clues about its purpose and the people who built it.
{{/trait}}

{{#trait "Role" "=" "rescuer"}}
Your protective instincts make you cautious about entering the temple, concerned about potential dangers that might lurk within its ancient chambers.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
Your adventurous spirit is immediately drawn to the temple's mysterious chambers, eager to discover what secrets and treasures they might contain.
{{/trait}}

The temple's main entrance is flanked by two massive stone pillars, each carved with different symbols representing what appear to be fundamental forces of nature. The air around the entrance crackles with energy, and you can feel the power that once flowed through this place.

What do you do next? 