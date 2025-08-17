---
id: path
title: The Mysterious Path
set:
  stats:
    experience: "+2"
    knowledge: "+1"
  types:
    Role:
      explorer: "+1"
      investigator: "+1"
      rescuer: "+1"
options:
  - text: Continue following the path
    next: valley
    set:
      stats:
        experience: "+2"
        knowledge: "+1"
      types:
        Role:
          explorer: "+1"
          investigator: "+1"
  - text: Return to the crash site
    next: plane
    set:
      stats:
        experience: "+1"
---

The mysterious path winds its way through the mountain passes, its smooth stones and careful construction suggesting it was made by human hands. The path seems to know where it's going, leading you through the most accessible routes and avoiding the most dangerous terrain.

The air is crisp and clean, and you can see for miles in every direction. The mountain peaks around you are covered in snow, creating a stark contrast with the green valleys below. The path itself is well-maintained, with stone markers and occasional rest areas that suggest regular use.

{{#trait "Role" "=" "explorer"}}
Your explorer's instincts are immediately drawn to the path's many mysteries, from the ancient stone markers to the hidden viewpoints that offer spectacular vistas of the surrounding landscape.
{{/trait}}

{{#trait "Role" "=" "investigator"}}
Your analytical mind immediately begins studying the path's construction, noting the engineering techniques used and the way it seems to have been designed to guide travelers safely through the mountains.
{{/trait}}

{{#trait "Role" "=" "rescuer"}}
Your protective instincts make you concerned about the other passengers from the plane, and you're determined to find help or a way to get them to safety.
{{/trait}}

The path leads you higher into the mountains, and as you climb, you begin to notice something strange about the landscape. The air seems to become warmer rather than colder, and you can see what appears to be a lush, green valley in the distance—something that shouldn't exist at this altitude.

What do you do next? 