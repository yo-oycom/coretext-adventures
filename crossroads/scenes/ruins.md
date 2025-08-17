---
id: ruins
title: Ancient Ruins
set:
  score: "+2"
  types:
    explorer: "+5"
options:
  - text: Search deeper
    next: deep_ruins
    set:
      types:
        explorer: "+1"
  - text: Leave
    next: start
---
{{#if (visited "ruins")}}
You've been here before. The familiar stone walls greet you with their weathered faces, each crack and crevice telling stories of time's relentless passage. The ancient masonry, though worn by centuries of wind and rain, still stands proud against the elements, its geometric precision speaking of a civilization that understood both beauty and function.

{{#if (typeGroup "Role" "explorer")}}
Your explorer's spirit recognizes patterns you missed before, and you notice subtle markings that suggest hidden chambers yet to be discovered.
{{/if}}

{{#if (typeGroup "Role" "druid")}}
Even in this place of stone and artifice, you sense the natural forces that have shaped these ruins over the centuries, feeling the earth's patient work of erosion and time.
{{/if}}

The air is thick with the dust of ages, and you can almost hear the echoes of footsteps that once walked these halls. The stone beneath your feet is cool and smooth, worn down by countless feet before yours, and you notice how the shadows seem to dance differently in the corners, as if the very darkness remembers the light that once filled these chambers.

The ruins feel like an old friend now, their secrets partially revealed but still holding mysteries yet to be uncovered.
{{else}}
The ancient stone walls hum with forgotten energy, their weathered surfaces bearing the scars of time while still radiating an aura of power that defies the centuries. As you step into the ruins, your footsteps echo through corridors that have stood silent for generations, each sound amplified by the perfect acoustics of the ancient architecture.

{{#if (typeGroup "Role" "explorer")}}
Your explorer's instincts immediately begin mapping the layout, noting the strategic positioning of each chamber and the careful engineering that has preserved this place.
{{/if}}

{{#if (typeGroup "Role" "druid")}}
You feel a strange resonance with the natural forces that have shaped these stones, sensing the ancient earth magic that still lingers in the air.
{{/if}}

The stone blocks, fitted together with impossible precision, seem to pulse with a subtle, otherworldly light that flickers at the edge of your vision. Carvings adorn the walls, their meanings lost to time but their beauty undiminished, telling stories of a people who understood both the practical and the mystical.

The air is thick with the scent of old stone and something else—perhaps the lingering essence of the magic that once flowed through these halls. You can feel the weight of history pressing down upon you, and you sense that these ruins hold secrets that could change everything you thought you knew about the world.
{{/if}} 