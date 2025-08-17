---
id: spirit
title: The Spirit's Blessing
set:
  stats:
    experience: "+3"
    wisdom: "+2"
  types:
    Role:
      druid: "+2"
options:
  - text: Accept the blessing
    next: start
    set:
      has:
        blessing_received: true
      stats:
        wisdom: "+3"
      types:
        Role:
          druid: "+1"
  - text: Decline respectfully
    next: start
    set:
      stats:
        experience: "+1"
---

The spirit's ethereal form shimmers before you, its ancient eyes filled with wisdom and compassion. It speaks in a voice that seems to echo from the depths of time itself.

{{#has "blessing_received"}}
**The spirit recognizes your previous blessing** and smiles knowingly.
{{/has}}

{{#trait "Role" "=" "druid"}}
**As a druid**, you feel a deep connection to this spirit. You sense that it represents the ancient magic of this forest, a guardian of the natural world that has existed here for centuries.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
**As an explorer**, you're fascinated by this encounter. This spirit represents the kind of discovery that makes your adventures worthwhile—a glimpse into the mystical side of the world.
{{/trait}}

The spirit offers you a choice: it can bestow upon you a blessing that will enhance your natural abilities, or you can decline and continue your journey as you are. The choice is yours, and the spirit will respect whatever decision you make.

{{#trait "Role" "=" "druid"}}
**Your druidic training** tells you that this blessing would be a great honor, a recognition of your connection to the natural world.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
**Your explorer's curiosity** makes you wonder what kind of abilities this blessing might grant you.
{{/trait}}

What do you choose? 