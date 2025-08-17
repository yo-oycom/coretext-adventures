---
id: library
title: The Library of All Knowledge
set:
  scores:
    experience: "+1"
    knowledge: "+3"
options:
  - text: Study the ancient texts
    next: choice
    set:
      scores:
        knowledge: "+2"
  - text: Search for information about Shangri-La
    next: choice
    set:
      scores:
        knowledge: "+1"
  - text: Return to the High Lama
    next: lama
---
The library is a vast, circular chamber filled with bookshelves that reach from floor to ceiling. The air is thick with the scent of old parchment and leather bindings, and the soft light filtering through stained glass windows creates an atmosphere of reverence and wonder.

{{#if (typeGroup "Role" "investigator")}}
Your investigator's training helps you navigate the library's complex organization system. The books are arranged not by subject or author, but by some deeper, more esoteric classification that seems to follow patterns of wisdom and understanding.
{{/if}}

The collection is truly extraordinary. You find ancient manuscripts from civilizations long forgotten, scientific treatises that predate modern discoveries, and philosophical works that contain insights that would revolutionize human understanding if they were known to the outside world.

Among the most fascinating items are:
- A complete history of Shangri-La, written by the High Lama himself
- Ancient maps showing the valley's location and the paths that lead to it
- Scientific studies on the valley's unique properties and their effects on aging
- Philosophical texts that explore the nature of time, wisdom, and human potential

{{#if (score "experience" ">=" 5)}}
Your growing knowledge of Shangri-La helps you understand the deeper significance of what you're reading. The valley isn't just a place of eternal youth—it's a repository of human wisdom, a sanctuary where knowledge is preserved and protected from the ravages of time and conflict.
{{/if}}

The library's central reading room is dominated by a massive table covered in ancient scrolls and open books. It's clear that this is where the High Lama and his scholars study and preserve the knowledge that makes Shangri-La so special.

As you explore the library, you begin to understand that Shangri-La's true purpose isn't just to provide eternal youth—it's to serve as a beacon of hope and wisdom for humanity, a place where the best of human knowledge and culture can be preserved for future generations. 