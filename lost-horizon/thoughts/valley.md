---
id: valley
title: Shangri-La
set:
  score: "+2"
  knowledge: "+1"
  types:
    explorer: "+1"
options:
  - text: Approach the temple complex
    next: temple
    set:
      score: "+1"
      types:
        investigator: "+1"
  - text: Explore the valley gardens
    next: temple
    set:
      knowledge: "+1"
      types:
        explorer: "+1"
  - text: Seek out the inhabitants
    next: temple
    set:
      score: "+1"
      types:
        rescuer: "+1"
---
The valley of Shangri-La stretches before you in all its glory. Lush gardens filled with exotic flowers and fruit trees surround elegant buildings that seem to have been designed by a master architect. The air is filled with the sweet scent of blossoms and the gentle sound of flowing water.

{{#if (type "Role" "explorer")}}
Your explorer's spirit is overwhelmed by the sheer wonder of this hidden paradise, and you can't wait to discover every corner of this magical place.
{{/if}}

{{#if (type "Role" "investigator")}}
Your analytical mind immediately begins cataloging the architectural details, the cultural patterns, and the technological marvels that make this place possible.
{{/if}}

{{#if (type "Role" "rescuer")}}
Your compassionate nature makes you wonder about the people who live here and whether they might need any assistance or have stories to share.
{{/if}}

The inhabitants of this hidden paradise move about their daily activities with a grace and serenity that's almost otherworldly. They appear to be of various ages and backgrounds, yet all share a certain timeless quality. Their clothing is simple but elegant, and they greet you with warm smiles and curious glances.

{{#if (visited "plane")}}
You recognize some of the people from the plane—they seem to have been here for some time, yet they look exactly as they did when you last saw them. The passage of time seems to have no effect on them.
{{/if}}

A tall, distinguished man approaches you. He introduces himself as Chang, the High Lama's assistant. "Welcome to Shangri-La," he says with a gentle smile. "You have been expected. The High Lama would like to speak with you."

The temple complex rises majestically in the center of the valley, its golden spires reaching toward the sky. It's clear that this is the heart of Shangri-La, where the secrets of this mysterious place are kept. 