---
id: temple
title: The Temple of Wisdom
set:
  score: "+2"
  knowledge: "+2"
  types:
    investigator: "+1"
options:
  - text: Meet the High Lama
    next: lama
    set:
      types:
        investigator: "+1"
  - text: Explore the temple library
    next: library
    set:
      knowledge: "+1"
  - text: Meditate in the gardens
    next: lama
    set:
      types:
        rescuer: "+1"
---
The temple complex is even more magnificent up close. Intricate carvings adorn every surface, telling stories of ancient wisdom and forgotten knowledge. The architecture seems to blend elements from every major civilization throughout history, yet it all works together in perfect harmony.

Chang leads you through the temple's grand halls, explaining that this place has been a sanctuary of knowledge for centuries. "The High Lama has been waiting for someone like you," he says. "Someone who can understand the true nature of Shangri-La."

{{#if (typeGroup "Role" "investigator")}}
Your analytical mind is working overtime, cataloging every detail. The temple's construction techniques, the materials used, the artwork—all suggest a level of sophistication that shouldn't exist in this remote location.
{{/if}}

{{#if (typeGroup "Role" "rescuer")}}
Your compassionate nature makes you wonder about the people who built this place and whether they might have needed help or protection in creating such a sanctuary.
{{/if}}

{{#if (typeGroup "Role" "explorer")}}
Your explorer's spirit is thrilled by the discovery of this ancient place, and you're eager to uncover every secret it holds.
{{/if}}

The temple's interior is filled with the soft glow of candlelight and the gentle sound of chanting. Monks in saffron robes move about their duties with practiced ease, and the air is thick with the scent of incense and ancient wisdom.

As you walk through the halls, you notice that the temple seems to be built around a central library—a vast collection of books and scrolls that contains knowledge from every corner of the world and every era of human history.

The High Lama's chambers are located at the very top of the temple, accessible only by a winding staircase that seems to spiral upward forever. Chang tells you that the High Lama is very old—perhaps hundreds of years old—and that he has been the guardian of Shangri-La's secrets for generations. 