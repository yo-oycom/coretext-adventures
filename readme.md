# Cortext Story Repository

This repository contains interactive stories for the Cortext application. Stories are loaded remotely at runtime, allowing for easy updates and distribution without modifying the main application.

## 🎯 **Quick Start Guide**

**Want to create a story? Here's what you need to know:**

> **🆕 New Intelligent Helper System**: We've updated to a smarter helper system that automatically detects whether you want conditional content or direct output. Use `{{#trait "Role" "=" "explorer"}}` for conditional content or `{{trait "Role"}}` for direct output - the same helper handles both! See the [Handlebars Helpers](#-available-handlebars-helpers) section for details.

1. **Create a folder** for your story
2. **Add `metadata.yml`** with your story info and game variables
3. **Create `scenes/` folder** with your story content (`.md` files)
4. **Update `stories.json`** to include your story

**That's it!** The system handles the rest automatically.

## 🎮 **What Are Game Variables?**

Think of game variables as ways to remember what happens in your story:

- **Scores** = Numbers that go up and down (like experience points)
- **Types** = Character traits that develop (like becoming more of a warrior or explorer)
- **Flags** = Yes/No questions (like "Do you have a key?" or "Is the door unlocked?")
- **Strings** = Text information (like the player's name or where they've been)

These let you create stories that remember player choices and show different content based on what they've done!

## 📁 Repository Structure

```
coretext-stories/
├── stories.json                    # Main manifest listing all available stories
├── crossroads/                     # Story directory
│   ├── metadata.yml               # Story metadata and configuration
│   └── scenes/                  # scene files (story content)
│       ├── start.md               # Starting scene
│       ├── crossroads.md          # Story content
│       ├── deep_ruins.md          # Story content
│       ├── forest.md              # Story content
│       ├── ruins.md               # Story content
│       └── spirit.md              # Story content
└── lost-horizon/                  # Another story directory
    ├── metadata.yml               # Story metadata and configuration
    └── scenes/                  # scene files (story content)
        ├── start.md               # Starting scene
        ├── choice.md              # Story content
        ├── lama.md                # Story content
        └── ...                    # Additional scene files
```

## 🚀 Getting Started

### 1. Create a New Story

**Step 1: Create a folder**
- Make a new folder with your story name (e.g., `my-adventure/`)

**Step 2: Add story information**
- Create `metadata.yml` file with your story details and game variables

**Step 3: Add story content**
- Create `scenes/` folder for your story files
- Add `.md` files for each part of your story

**Step 4: Tell the system about your story**
- Update `stories.json` to include your story name

**That's it!** Your story will now appear in the Cortext app.

### 2. Required Files

**You need 3 main files:**

#### `stories.json` (Root Level)
This tells the system what stories exist:
```json
{
  "stories": [
    "crossroads",
    "lost-horizon",
    "my-adventure"
  ]
}
```

#### `metadata.yml` (Per Story)
This contains your story information and game variables:
```yaml
id: my-adventure
title: My Adventure
description: An exciting journey through mysterious lands...
image: https://example.com/image.jpg
author: Your Name

# Game variables (what the story remembers)
stats:
  knowledge: 0
  strength: 10
  experience: 5

traits:
  Role: [explorer, warrior, scholar, mage, rogue]

has:
  hasKey: false
  doorUnlocked: false

text:
  playerName: ""
  chosenPath: ""

# List your story files
scenes:
  - start.md
  - choice1.md
  - choice2.md
  - ending.md
```

## 📝 Creating scene Files

**scene files are the building blocks of your story.** Each one represents a scene or moment where the player makes a choice.

### Basic scene Structure
Each scene file (`.md`) should follow this format:

```markdown
---
id: start
title: The Beginning
set:
  stats:
    knowledge: "+5"
    experience: "+2"
  traits:
    Role:
      explorer: "+2"
      warrior: "+1"
options:
  - text: Go left
    next: choice1
    set:
      stats:
        knowledge: "+3"
      traits:
        Role:
          explorer: "+1"
  - text: Go right
    next: choice2
    set:
      stats:
        strength: "+2"
      traits:
        Role:
          warrior: "+1"
---

# The Beginning

You find yourself at a crossroads in a mysterious forest. The path splits in two directions...

**What do you do?**
```

### What Each Part Does

- **`id`**: A unique name for this scene (like "start", "choice1", "ending")
- **`title`**: What to call this scene (optional)
- **`set`**: What happens when the player reaches this scene (scores go up, flags change, etc.)
- **`options`**: The choices the player can make
- **Content**: The story text that describes what's happening

## 🎮 Game Mechanics

**This section explains how to make your story interactive and remember what players do.**

### Variable Types

Cortext supports four main types of variables that can be used to track game state and create dynamic content:

#### 1. Stats
- **What they are**: Numbers that go up and down as players make choices
- **What they're for**: Tracking progress, experience, resources, etc.
- **How to use**: Use `"+5"` to add 5, `"-3"` to subtract 3
- **Example**:
  ```yaml
  stats:
    knowledge: 0      # Player starts with 0 knowledge
    strength: 10      # Player starts with 10 strength
    experience: 5     # Player starts with 5 experience
  ```

#### 2. Traits
- **What they are**: Character traits that develop as players make choices
- **What they're for**: Creating different character paths (warrior, explorer, etc.)
- **How to use**: Use `"+2"` to increase a trait, `"-1"` to decrease it
- **Example**:
  ```yaml
  traits:
    Role: [explorer, warrior, scholar, mage, druid]  # These are the traits players can develop
  ```

#### 3. Has
- **What they are**: Yes/No questions about the story state
- **What they're for**: Remembering if something happened (got a key, unlocked a door, etc.)
- **How to use**: Use `true` for yes, `false` for no
- **Example**:
  ```yaml
  has:
    hasKey: false     # Player doesn't have a key yet
    doorUnlocked: false  # Door is still locked
    metWizard: false  # Player hasn't met the wizard yet
  ```

#### 4. Text
- **What they are**: Text information to remember
- **What they're for**: Storing player names, choices, locations, etc.
- **How to use**: Use quoted text like `"left"` or `"forest"`
- **Example**:
  ```yaml
  text:
    playerName: ""        # Player's name (empty until they choose one)
    chosenPath: ""        # Which path they chose (empty until they choose)
    lastLocation: ""      # Where they were last (empty until they visit somewhere)
  ```

### Using Variables in Set Blocks

**The `set` block lets you change game variables when players reach a scene or make a choice.**

All variable types can be modified in the `set` block of scenes and options:

```yaml
set:
  stats:
    knowledge: "+5"      # Add 5 to knowledge
    strength: "-2"       # Subtract 2 from strength
  traits:
    Role:
      explorer: "+1"     # Add 1 to explorer trait
      warrior: "+1"      # Add 1 to warrior trait
  has:
    hasKey: true         # Set hasKey to true (player now has the key)
    doorUnlocked: true  # Set doorUnlocked to true (door is now unlocked)
  text:
    chosenPath: "left"   # Set chosenPath to "left"
    lastLocation: "crossroads"  # Set lastLocation to "crossroads"
```

**What this does**: When the player reaches this scene or makes this choice, all these changes happen automatically!

### Conditional Content

**Use Handlebars helpers to show different text based on what the player has done or what they have.**

Here are examples of how to check game variables:

```markdown
{{#trait "Role" "=" "explorer"}}
  **Your explorer instincts kick in!** You notice subtle clues that others might miss.
{{/trait}}

{{#stat "experience" ">=" 10}}
  **You've gained enough experience** to unlock the secret path.
{{/stat}}

{{#has "hasKey"}}
  **You have the key!** The door should unlock now.
{{/has}}

{{#text "chosenPath" "=" "left"}}
  **You chose the left path** earlier, and it shows in your current situation.
{{/text}}
```

**What this does**: The text inside the helper blocks only shows when the condition is true. Otherwise, that text is hidden!

### Direct Output

**You can also use the same helpers to display current values directly:**

```markdown
Your current role is: {{trait "Role"}}
Your experience level: {{stat "experience"}}
Do you have a key? {{has "hasKey"}}
Your chosen path: {{text "chosenPath"}}
```

**What this does**: These helpers output the actual current values, perfect for showing the player's current status!

### Dynamic Role-Based Content

**This is a special feature that automatically shows different text based on which character trait the player has developed the most.**

#### Setting Up Role Types
In your `metadata.yml`, simply define your role types:

```yaml
traits:
  Role: [explorer, warrior, scholar, mage, druid]
```

**That's it!** The system automatically:
- Creates score tracking for each type
- Determines which type has the highest score
- Updates the role as players make choices

#### Using Role-Based Content
Use the `{{#trait "Role" "=" "typeName"}}` helper to show different text based on the player's current role:

```markdown
{{#trait "Role" "=" "druid"}}
  **You are a Druid!** Your connection to nature guides your path.
{{/trait}}

{{#trait "Role" "=" "warrior"}}
  **You are a Warrior!** Your combat skills protect you.
{{/trait}}

{{#trait "Role" "=" "scholar"}}
  **You are a Scholar!** Your knowledge reveals hidden secrets.
{{/trait}}

{{#trait "Role" "=" "mage"}}
  **You are a Mage!** Your magical abilities open new possibilities.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
  **You are an Explorer!** Your curiosity leads you to new discoveries.
{{/trait}}
```

**You can also display the current role directly:**
```markdown
Your current role is: {{trait "Role"}}
```

#### How It Works
1. **Define your types**: `types: Role: [explorer, warrior, scholar, mage, druid]`
2. **System tracks scores**: Automatically creates `explorer_score`, `warrior_score`, etc.
3. **Dynamic content**: Text changes based on which type has the highest score
4. **Real-time updates**: Role determination updates as players make choices

#### Complete Example
```markdown
---
id: role-check
options:
  - text: Continue
    next: next-scene
---

{{#trait "Role" "=" "druid"}}
  **As a Druid**, you sense the ancient magic in these ruins. Your connection to nature tells you this place was once a sacred grove.
{{/trait}}

{{#trait "Role" "=" "warrior"}}
  **As a Warrior**, you notice the strategic layout of these ruins. Your combat experience suggests this was once a defensive structure.
{{/trait}}

{{#trait "Role" "=" "scholar"}}
  **As a Scholar**, you recognize the architectural patterns. Your knowledge of ancient civilizations reveals this was a temple complex.
{{/trait}}

{{#trait "Role" "=" "mage"}}
  **As a Mage**, you feel the lingering magical energy. Your arcane senses detect powerful enchantments still active here.
{{/trait}}

{{#trait "Role" "=" "explorer"}}
  **As an Explorer**, you're excited by the unknown. Your curiosity drives you to investigate every corner of these mysterious ruins.
{{/trait}}

**Your current role is: {{trait "Role"}}**

What do you do next?
```

## 🔧 Available Handlebars Helpers

The engine provides intelligent helpers that automatically detect whether they're being used for conditional content or direct output. Each helper works in both modes!

### Combined Helpers (Conditional + Output)

#### Trait Helpers
- **`{{#trait "group" "=" "value"}}`**: Check if a trait group has a specific dominant value (e.g., `{{#trait "Role" "=" "explorer"}}`)
- **`{{#trait "group" ">" 5}}`**: Check if a trait score meets a threshold (e.g., `{{#trait "Role" ">" 3}}`)
- **`{{trait "group"}}`**: Get the current dominant trait value (e.g., `{{trait "Role"}}` outputs "explorer")

#### Stat Helpers
- **`{{#stat "name" ">=" 10}}`**: Check if a stat meets a threshold (e.g., `{{#stat "experience" ">=" 10}}`)
- **`{{#stat "name" "<" 5}}`**: Check if a stat is below a threshold (e.g., `{{#stat "strength" "<" 5}}`)
- **`{{#stat "name" ">" 3}}`**: Check if a stat is above a threshold (e.g., `{{#stat "knowledge" ">" 3}}`)
- **`{{#stat "name" "<=" 8}}`**: Check if a stat is at or below a threshold (e.g., `{{#stat "health" "<=" 8}}`)
- **`{{#stat "name" "==" 15}}`**: Check if a stat equals a value (e.g., `{{#stat "level" "==" 15}}`)
- **`{{stat "name"}}`**: Get the current stat value (e.g., `{{stat "experience"}}` outputs 15)

#### Text Helpers
- **`{{#text "name" "=" "value"}}`**: Check if a text value equals a specific string (e.g., `{{#text "chosenPath" "=" "left"}}`)
- **`{{text "name"}}`**: Get the current text value (e.g., `{{text "chosenPath"}}` outputs "left")

#### Has Helpers
- **`{{#has "flag"}}`**: Check if a flag is true (e.g., `{{#has "foundTreasure"}}`)
- **`{{has "flag"}}`**: Get the current flag value (e.g., `{{has "foundTreasure"}}` outputs true)

#### History Helpers
- **`{{#history "visited_scene"}}`**: Check if a scene has been visited (e.g., `{{#history "visited_start"}}`)
- **`{{history "visited_scene"}}`**: Get visit count for a scene (e.g., `{{history "start"}}` outputs 1)

### How It Works
- **With `#`**: `{{#trait "Role" "=" "builder"}}content{{/trait}}` → Conditional rendering
- **Without `#`**: `{{trait "Role"}}` → Direct output of value

**Example**: The same helper handles both use cases:
```markdown
{{#trait "Role" "=" "builder"}}
  **As a Builder**, you can construct amazing structures.
{{/trait}}

Your current role is: {{trait "Role"}}
```



## 📚 Story Examples

### Simple Choice
```markdown
---
id: simple-choice
options:
  - text: Accept the quest
    next: quest-accepted
  - text: Decline
    next: quest-declined
---

A mysterious stranger offers you a quest. Will you accept?
```

### Conditional Options
```markdown
---
id: conditional-choice
options:
  - text: Use magic
    next: magic-path
    set:
      types:
        Role:
          mage: "+1"
  - text: Fight
    next: fight-path
    set:
      types:
        Role:
          warrior: "+1"
  - text: Sneak past
    next: stealth-path
    set:
      types:
        Role:
          rogue: "+1"
---

{{#trait "Role" "=" "mage"}}
  **Your magical abilities** give you multiple options.
{{/trait}}

{{#trait "Role" "=" "warrior"}}
  **Your combat training** makes you confident in a fight.
{{/trait}}

{{#trait "Role" "=" "rogue"}}
  **Your stealth skills** suggest a sneaky approach.
{{/trait}}

How do you proceed?
```

### State-Dependent Content
```markdown
---
id: returning-visitor
options:
  - text: Continue
    next: next-scene
---

{{#has "first_time"}}
  Welcome! This is your first time here.
{{/has}}

{{#has "returning"}}
  Welcome back! You've been here before.
{{/has}}

{{#stat "experience" ">=" 20}}
  **You're becoming quite experienced** in these lands.
{{/stat}}
```

### Complex Variable Usage Example
```markdown
---
id: advanced-choice
options:
  - text: Use the key
    next: unlock-door
    set:
      has:
        doorUnlocked: true
      stats:
        experience: "+5"
      text:
        lastAction: "unlocked door"
  - text: Try to break it
    next: break-attempt
    set:
      stats:
        strength: "+2"
        experience: "+3"
      traits:
        Role:
          warrior: "+1"
      text:
        lastAction: "tried to break door"
---

{{#has "hasKey"}}
  **You have a key** that might fit this door.
{{/has}}

{{#stat "strength" ">=" 15}}
  **Your strength** might be enough to break through.
{{/stat}}

{{#trait "Role" "=" "warrior"}}
  **Your warrior training** suggests this door can be forced.
{{/trait}}

{{#text "lastAction" "=" "unlocked door"}}
  **You previously unlocked a door** - this might be similar.
{{/text}}

**Current status:**
- Key: {{has "hasKey"}}
- Strength: {{stat "strength"}}
- Role: {{trait "Role"}}
- Last action: {{text "lastAction"}}

What do you do?
```

## 🚨 Important Rules

### 1. scene IDs Must Be Unique
- Each scene file must have a unique `id` in its frontmatter
- IDs are used for navigation between scenes

### 2. Valid Navigation Paths
- Every `next` value in options must point to an existing scene ID
- The `start.md` scene is automatically loaded when a story begins

### 3. File Naming
- **scene files**: Use descriptive names like `start.md`, `crossroads.md`, `deep_ruins.md`
- **Metadata file**: Must be named `metadata.yml`
- **Manifest file**: Must be named `stories.json`

### 4. YAML Syntax
- **Use spaces, not tabs** for indentation
- **Quote strings** that contain special characters
- **Use arrays** for lists like `scenes: [file1.md, file2.md]`

## 🔍 Testing Your Story

### 1. Validate Structure
- Check that all `next` references point to valid scene IDs
- Ensure `start.md` exists and is properly formatted
- Verify all scene files listed in `metadata.yml` exist

### 2. Test Navigation
- Start the story and follow each path
- Check that all choices lead to the expected scenes
- Verify that state changes (score, types) work correctly

### 3. Test Conditionals
- Play through different paths to test conditional content
- Verify that type-based and score-based conditions work
- Test visit-based conditions by revisiting scenes

## 📖 Best Practices

### Story Design
- **Start simple**: Begin with a basic story structure and add complexity
- **Plan your paths**: Map out the story flow before writing
- **Test thoroughly**: Play through all possible paths
- **Use meaningful IDs**: Make scene IDs descriptive and memorable

### Content Organization
- **Group related scenes**: Use subdirectories for complex stories
- **Consistent naming**: Follow a consistent pattern for file names
- **Document your story**: Include comments in metadata for complex logic

### Performance
- **Optimize images**: Use appropriately sized images for web
- **Minimize file size**: Keep scene content concise but engaging
- **Efficient navigation**: Avoid unnecessary back-and-forth between scenes

## 🆘 Troubleshooting

### Common Issues

#### Story Not Loading
- Check that `stories.json` includes your story ID
- Verify `metadata.yml` has the correct `id` field
- Ensure all required fields are present

#### scenes Not Found
- Verify all scene files listed in `metadata.yml` exist
- Check that file names match exactly (including case)
- Ensure scene files are in the `scenes/` subdirectory

#### Navigation Errors
- Check that all `next` values point to valid scene IDs
- Verify that scene IDs are unique across the entire story
- Ensure `start.md` exists and is properly formatted

#### Conditional Content Not Working
- Check that type and score values are being set correctly
- Verify Handlebars syntax is correct
- Test with different game states to ensure conditions work

## 📞 Support

If you encounter issues:
1. **Check the console** for error messages
2. **Verify file structure** matches the examples above
3. **Test with a simple story** to isolate the problem
4. **Check YAML syntax** for proper formatting

## 🎯 Next Steps

1. **Create your first story** using the examples above
2. **Test the story** in the Cortext application
3. **Iterate and improve** based on player feedback
4. **Share your stories** with the community!

Happy storytelling! 📚✨




