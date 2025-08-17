---
id: start
title: The Plane Crash
set:
  stats:
    experience: "+1"
    knowledge: "+1"
options:
  - text: Investigate the crash site
    next: plane
    set:
      types:
        Role:
          investigator: "+2"
  - text: Look for other survivors
    next: plane
    set:
      types:
        Role:
          rescuer: "+2"
  - text: Follow the mysterious path
    next: path
    set:
      types:
        Role:
          explorer: "+2"
---

{{#unless (stat "knowledge" ">=" 3)}}
**You're still learning** about this mysterious place.
{{/unless}}

The plane shudders violently as you're jolted awake from a fitful sleep. Through the window, you can see nothing but swirling clouds and jagged mountain peaks. The engines are making a terrible sound, and the cabin is filled with the panicked voices of other passengers.

Suddenly, everything goes dark. When you regain consciousness, you find yourself lying in the snow, surrounded by the wreckage of what was once a passenger plane. The cold mountain air stings your lungs, and you can see your breath in the crisp air.

The crash site is eerily quiet, save for the wind howling through the mountain passes. The plane's fuselage is broken in several places, and luggage and personal items are scattered across the snow-covered ground. In the distance, you can see what appears to be a well-maintained path leading away from the crash site.

Your survival instincts kick in, but you're not sure which direction to take. The path seems too well-maintained for a remote mountain location, and you can't shake the feeling that someone—or something—is watching you.

{{#trait "Role" "=" "investigator"}}
Your analytical mind immediately begins cataloging the evidence around you.
{{/trait}}

{{#trait "Role" "=" "rescuer"}}
Your heart goes out to the other passengers who might need your help.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
The mysterious path calls to your adventurous spirit.
{{/trait}}

{{#trait "Role" ">" 1}}
**Your skills are already developing** in your chosen path.
{{/trait}} 