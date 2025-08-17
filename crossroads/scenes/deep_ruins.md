---
id: deep_ruins
title: Deep Ruins
set:
  score: "+3"
  treasure: true
  types:
    explorer: "+2"
options:
  - text: Take the treasure
    next: crossroads      # ← Change this from "start" to "crossroads"
    set:
      score: "+5"          # ← Keep the +5 score bonus
      types:
        explorer: "+1"     # ← Keep the +1 explorer bonus
  - text: Leave it be
    next: start          # ← This can stay as "start"
    set:
      types:
        druid: "+1"
---
{{#if (visited "deep_ruins")}}
You've explored these depths before. The treasure chest still glows with its ethereal light, casting dancing shadows across the chamber walls that seem to tell stories of their own. The air is thick with the scent of old magic and something more ancient still, and you can feel the weight of countless years pressing down upon you.

The chamber itself seems to breathe, its very stones alive with the energy of ages past, and you notice how the light from the chest seems to pulse in time with your own heartbeat. The treasure within calls to you with a voice that speaks directly to your soul, promising power and knowledge beyond mortal comprehension.

Yet there's something else here too—a sense of responsibility, perhaps, or a warning that some things are better left undisturbed.

{{#if (typeGroup "Role" "explorer")}}
Your explorer's spirit is drawn to the treasure, but your experience has taught you to be more cautious about such powerful artifacts.
{{/if}}

{{#if (typeGroup "Role" "druid")}}
Your connection to natural forces makes you wary of disturbing the ancient magic that has lain dormant for so long.
{{/if}}
{{else}}
Deep in the ruins, you find an ancient treasure chest glowing with magical energy, its surface adorned with intricate runes that pulse with an otherworldly light. The chamber around you is vast and echoing, its walls lined with carvings that seem to move and shift in the flickering illumination.

The air crackles with static electricity, and you can feel the raw power emanating from the chest like heat from a forge. The runes themselves seem to tell a story—one of creation and destruction, of power gained and lost, of choices that shaped the very fabric of reality.

The treasure within calls to you with a voice that speaks directly to your soul, promising knowledge and power beyond mortal comprehension. Yet there's something else here too—a sense of responsibility, perhaps, or a warning that some things are better left undisturbed. The chest seems to be waiting for you to make a choice that will echo through the ages.

{{#if (typeGroup "Role" "explorer")}}
Your explorer's instincts tell you this is a discovery of immense importance, but you also sense the weight of responsibility that comes with such power.
{{/if}}

{{#if (typeGroup "Role" "druid")}}
Your natural wisdom and connection to ancient forces makes you cautious about disturbing the delicate balance of magic that has been maintained here for centuries.
{{/if}}
{{/if}} 