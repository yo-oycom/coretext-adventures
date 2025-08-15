---
id: path
title: The Mysterious Path
set:
  score: "+1"
  types:
    explorer: "+1"
options:
  - text: Follow the path deeper into the mountains
    next: valley
    set:
      score: "+1"
      types:
        explorer: "+1"
  - text: Return to the crash site
    next: plane
  - text: Wait and observe
    next: valley
    set:
      types:
        investigator: "+1"
---
The path is unlike anything you've ever seen. Smooth, perfectly fitted stones form a gentle slope that winds its way through the mountain passes. The craftsmanship is exquisite, suggesting a level of skill and resources that shouldn't exist in such a remote location.

As you walk along the path, you notice that the air becomes warmer and more pleasant. The harsh mountain winds give way to a gentle breeze, and the snow-covered ground gradually transitions to lush vegetation. Strange flowers bloom along the path, their colors more vibrant than any you've seen before.

{{#if (typeGroup "Role" "explorer")}}
Your explorer's instincts tell you that this path was designed to be discovered—it's too well-maintained, too inviting. Someone wants visitors to find their way to whatever lies at the end.
{{/if}}

{{#if (typeGroup "Role" "investigator")}}
Your analytical mind notes the strategic placement of the path, the careful engineering that makes it accessible while remaining hidden from casual observation.
{{/if}}

{{#if (typeGroup "Role" "rescuer")}}
Your compassionate nature makes you wonder about the people who built this path and whether they might need help or welcome visitors.
{{/if}}

The path continues to wind through the mountains, and you begin to notice subtle architectural details: carved stone markers, small shrines, and what appear to be viewing platforms. The craftsmanship becomes more elaborate the further you travel, suggesting you're approaching something significant.

After what feels like hours of walking, the path opens into a breathtaking vista. Before you lies a hidden valley, its lush green landscape dotted with elegant buildings that seem to blend seamlessly with the natural environment. In the center of the valley stands a magnificent temple complex, its golden spires catching the sunlight.

This must be Shangri-La—the legendary valley of eternal youth and wisdom. 