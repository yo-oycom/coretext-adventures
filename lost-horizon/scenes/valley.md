---
id: valley
title: The Hidden Valley
set:
  stats:
    experience: "+2"
    knowledge: "+1"
  traits:
    Role:
      explorer: "+1"
      investigator: "+1"
      rescuer: "+1"
options:
  - text: Explore the valley
    next: temple
    if: trait "Role" "=" "explorer"
    set:
      stats:
        experience: "+3"
        knowledge: "+2"
      traits:
        Role:
          explorer: "+1"
  - text: Explore the valley
    next: temple
    if: trait "Role" "=" "investigator"
    set:
      stats:
        experience: "+2"
        knowledge: "+3"
      traits:
        Role:
          investigator: "+1"
  - text: Explore the valley
    next: temple
    if: trait "Role" "=" "rescuer"
    set:
      stats:
        experience: "+2"
        knowledge: "+1"
      traits:
        Role:
          rescuer: "+1"
  - text: Return to the crash site
    next: plane
    set:
      stats:
        experience: "+1"
---

The hidden valley stretches before you in all its breathtaking beauty. Lush green meadows dotted with colorful wildflowers, crystal-clear streams flowing from snow-capped peaks, and ancient trees that seem to touch the sky—this place is like nothing you've ever seen before.

The air is crisp and clean, filled with the sweet scent of flowers and the gentle sound of flowing water. The temperature is perfect—not too hot, not too cold—and you feel an immediate sense of peace and tranquility wash over you.

{{#trait "Role" "=" "explorer"}}
Your explorer's instincts are immediately drawn to the valley's many mysteries, from the ancient stone structures you can see in the distance to the hidden paths that wind through the landscape. You can't wait to discover every corner of this hidden paradise. The thrill of exploration pulses through your veins.
{{/trait}}

{{#trait "Role" "=" "investigator"}}
Your analytical mind immediately begins cataloging the valley's features, noting the unusual climate, the perfect weather, and the way everything seems to be arranged with purpose and intention. This place defies natural laws, and you're determined to understand how it works.
{{/trait}}

{{#trait "Role" "=" "rescuer"}}
Your protective instincts make you concerned about the other passengers from the plane, and you're determined to find help or a way to get them to safety. This valley might be the sanctuary you've been searching for, a place where everyone can find refuge and healing.
{{/trait}}

{{#visited "plane"}}
**You remember the crash site** and the mysterious path that led you here, and you're grateful that you followed it to this beautiful place.
{{/visited}}

The valley seems to be completely isolated from the outside world, surrounded by towering mountain peaks that would be impossible to climb. Yet despite its remote location, the valley shows signs of human habitation—well-maintained paths, cultivated gardens, and what appears to be a temple complex in the distance.

How will you approach exploring this mysterious valley? 