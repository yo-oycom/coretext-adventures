---
id: plane
title: The Crash Site
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
  - text: Search for survivors
    next: valley
    set:
      types:
        Role:
          rescuer: "+1"
  - text: Investigate the wreckage
    next: valley
    set:
      types:
        Role:
          investigator: "+1"
  - text: Follow the path
    next: path
    set:
      types:
        Role:
          explorer: "+1"
---

The crash site is a scene of devastation and mystery. The plane's fuselage is broken in several places, with debris scattered across the snow-covered ground. The cold mountain air stings your lungs, and you can see your breath in the crisp air.

Your survival instincts kick in immediately. You need to assess the situation, look for other survivors, and find a way to get help or reach safety. The well-maintained path you noticed earlier seems to be your best option, but first you should check if anyone else needs your assistance.

The wreckage tells a story of what happened. The plane appears to have been caught in some kind of storm or turbulence, and the pilots may have been trying to make an emergency landing when they lost control. The fact that you survived relatively unscathed is nothing short of miraculous.

{{#trait "Role" "=" "investigator"}}
Your analytical mind immediately begins cataloging the evidence around you, looking for clues about what caused the crash and what might happen next.
{{/trait}}

{{#trait "Role" "=" "rescuer"}}
Your heart goes out to the other passengers who might need your help, and you're determined to do everything you can to assist them.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
Your adventurous spirit is already looking ahead to what lies beyond the crash site, eager to discover what this mysterious mountain valley has to offer.
{{/trait}}

What do you do next? 