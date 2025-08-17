---
id: spirit
title: Forest Spirit
set:
  wisdom: true
  blessing_received: true
  types:
    druid: "+2"
---
{{#if (has "blessing_received")}}
The forest spirit recognizes you from before and grants you an additional blessing, its ethereal form shimmering with renewed light as it reaches out to touch your soul. The spirit's presence fills the clearing with a warmth that seems to emanate from the very heart of the forest itself, and you can feel the ancient wisdom flowing through you like a gentle stream.

{{#if (typeGroup "Role" "druid")}}
Your deepened connection to nature allows you to understand the spirit's language more clearly, receiving insights that few mortals could comprehend.
{{/if}}

{{#if (typeGroup "Role" "explorer")}}
Your explorer's spirit recognizes the unique opportunity this represents, and you carefully observe the spirit's form and behavior for future reference.
{{/if}}

The blessing this time feels deeper, more profound, as if the spirit has come to know you better and has chosen to share secrets that few mortals have ever been privileged to receive. The air around you seems to sparkle with unseen magic, and you notice how the trees themselves seem to lean in closer, their branches forming a protective circle around the clearing.

The spirit's voice, when it speaks, is like the rustling of leaves and the babbling of brooks combined, carrying with it the weight of countless years of forest wisdom.
{{else}}
A forest spirit blesses your journey, its ethereal form materializing from the very essence of the forest itself. The spirit appears as a being of pure light and shadow, its form shifting and flowing like water, yet somehow solid and real. Its eyes, deep pools of ancient wisdom, seem to look directly into your soul, reading the truth of your heart and intentions.

{{#if (typeGroup "Role" "druid")}}
Your natural affinity for the forest allows you to immediately connect with the spirit, feeling the ancient magic that flows between you.
{{/if}}

{{#if (typeGroup "Role" "explorer")}}
Your explorer's curiosity is piqued by this supernatural encounter, and you carefully observe every detail of the spirit's manifestation.
{{/if}}

The blessing flows through you like warm honey, filling you with a sense of connection to all living things and a deep understanding of the natural world's rhythms and cycles. You can feel the spirit's power coursing through your veins, granting you insights that transcend ordinary human perception.

The forest around you seems to respond to the spirit's presence, with flowers blooming where there were none before and animals emerging from their hiding places to witness this sacred moment. The spirit's voice, when it speaks, is like the rustling of leaves and the babbling of brooks combined, carrying with it the weight of countless years of forest wisdom.
{{/if}} 