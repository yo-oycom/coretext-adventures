---
id: choice
title: The Final Choice
set:
  scores:
    experience: "+5"
options:
  - text: Stay in Shangri-La forever
    next: stay-forever
    if: score >= 3
  - text: Return to the outside world
    next: return-world
---

You stand at a crossroads that will determine the course of your life. Shangri-La stretches before you in all its beauty and wonder—a place of eternal youth, wisdom, and peace. The outside world, with all its chaos, conflict, and uncertainty, lies behind you.

{{#if (score "experience" ">=" 5)}}
Your time in the library and your conversations with the High Lama have given you a deep understanding of Shangri-La's true purpose. This isn't just a place of escape—it's a sanctuary of human wisdom, a beacon of hope for future generations.
{{/if}}

{{#if (typeGroup "Role" "investigator")}}
Your investigator's instincts tell you that there's more to this choice than meets the eye. The valley's existence, the way you were brought here, the timing of your arrival—all suggest that this moment was carefully orchestrated.
{{/if}}

The High Lama has explained that Shangri-La needs people like you—people who can understand its true value and help preserve its wisdom for future generations. But he also understands that the outside world needs people who can carry the valley's lessons back to humanity.

If you choose to stay, you will become part of Shangri-La's eternal community, helping to preserve and protect the knowledge and wisdom that makes this place so special. You will have the gift of extended life, but you will also have the responsibility of maintaining the valley's traditions and values.

If you choose to return, you will carry the memory and lessons of Shangri-La with you, perhaps helping to make the outside world a better place. But you will also face the challenges and uncertainties of mortal life, and you may never find your way back to this paradise.

The choice is yours, and it will shape not just your own destiny, but potentially the destiny of humanity itself. 