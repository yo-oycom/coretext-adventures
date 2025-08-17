---
id: lama
title: Meeting the High Lama
set:
  stats:
    experience: "+3"
    knowledge: "+2"
options:
  - text: Ask about the nature of Shangri-La
    next: choice
    set:
      stats:
        knowledge: "+2"
  - text: Inquire about staying in the valley
    next: choice
    set:
      stats:
        experience: "+1"
  - text: Ask about returning to the outside world
    next: choice
    set:
      stats:
        experience: "+1"
---

The High Lama's chambers are a study in simplicity and elegance. The room is sparsely furnished but every item seems to have been chosen with great care and purpose. The High Lama himself sits in a simple chair by the window, his ancient face radiating wisdom and serenity.

Despite his apparent age—which must be several hundred years—the High Lama's eyes are bright and alert, filled with the kind of understanding that comes only from centuries of study and contemplation. He greets you with a gentle smile and gestures for you to sit.

"Welcome to Shangri-La," he says, his voice soft but clear. "I have been expecting you. The valley has a way of calling to those who are ready to understand its true nature."

{{#stat "knowledge" ">=" 5}}
Your studies in the library have prepared you for this meeting. You understand that Shangri-La is more than just a place of eternal youth—it's a sanctuary of wisdom, a repository of human knowledge that has been preserved and protected for generations.
{{/stat}}

The High Lama explains that Shangri-La was founded centuries ago by a group of wise men and women who recognized that human civilization was prone to cycles of destruction and rebirth. They created this hidden valley as a place where the best of human knowledge, culture, and wisdom could be preserved.

"Time moves differently here," he explains. "Not because of some magical force, but because of the valley's unique location and the way of life we have chosen. We have learned to live in harmony with nature and with each other, and this has given us the gift of extended life."

The High Lama tells you that you are free to stay in Shangri-La if you wish, but he also understands if you choose to return to the outside world. "The choice is yours," he says. "But remember that once you leave, you may never find your way back." 