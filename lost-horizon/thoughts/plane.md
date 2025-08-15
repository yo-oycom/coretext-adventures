---
id: plane
title: Investigating the Wreckage
set:
  score: "+1"
  knowledge: "+1"
  types:
    investigator: "+1"
options:
  - text: Search for clues about the flight
    next: path
    set:
      knowledge: "+1"
      types:
        investigator: "+1"
  - text: Look for supplies and equipment
    next: path
    set:
      score: "+1"
      types:
        rescuer: "+1"
  - text: Examine the mysterious path
    next: path
    set:
      score: "+1"
      types:
        explorer: "+1"
---
You carefully make your way through the wreckage, your instincts taking over. The plane appears to be a commercial airliner, but something about it seems... off. The interior is more luxurious than you'd expect, with plush seating and fine wood paneling.

As you search through the debris, you notice several unusual details: the flight manifest is missing, there are no standard airline markings, and the navigation equipment seems to be from a different era entirely. The pilot's logbook contains entries in a language you don't recognize, and the coordinates listed don't match any known flight paths.

{{#if (type "Role" "investigator")}}
Your analytical training kicks in, and you begin to systematically document everything you find. The evidence suggests this wasn't a regular commercial flight at all, but something much more mysterious.
{{/if}}

{{#if (type "Role" "rescuer")}}
Your protective instincts drive you to search more thoroughly, looking for any signs of other survivors who might need immediate assistance.
{{/if}}

{{#if (type "Role" "explorer")}}
The mysterious nature of this crash site excites your adventurous spirit, and you're eager to discover what secrets this place holds.
{{/if}}

Among the scattered luggage, you find several items that seem out of place: ancient-looking books, maps with strange symbols, and what appears to be a journal written in an elegant hand. The journal's last entry mentions "Shangri-La" and "the valley of eternal youth."

The path you noticed earlier seems to beckon you, its smooth stones and careful construction suggesting it was made by human hands—but who would build such a path in this remote location? 