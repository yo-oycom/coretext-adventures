# Cortext Story Repository

This repository contains interactive stories for the Cortext application. Stories are loaded remotely at runtime, allowing for easy updates and distribution without modifying the main application.

## 📁 Repository Structure

```
coretext-stories/
├── stories.json                    # Main manifest listing all available stories
├── crossroads/                     # Story directory
│   ├── metadata.yml               # Story metadata and configuration
│   └── thoughts/                  # Thought files (story content)
│       ├── start.md               # Starting thought
│       ├── crossroads.md          # Story content
│       ├── deep_ruins.md          # Story content
│       ├── forest.md              # Story content
│       ├── ruins.md               # Story content
│       └── spirit.md              # Story content
└── lost-horizon/                  # Another story directory
    ├── metadata.yml               # Story metadata and configuration
    └── thoughts/                  # Thought files (story content)
        ├── start.md               # Starting thought
        ├── choice.md              # Story content
        ├── lama.md                # Story content
        └── ...                    # Additional thought files
```

## 🚀 Getting Started

### 1. Create a New Story

1. **Create a new directory** for your story (e.g., `my-adventure/`)
2. **Create `metadata.yml`** in the story directory
3. **Create `thoughts/` subdirectory** for your story content
4. **Add thought files** (`.md` files) in the thoughts directory
5. **Update `stories.json`** to include your new story

### 2. Required Files

#### `stories.json` (Root Level)
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
```yaml
id: my-adventure
title: My Adventure
description: An exciting journey through mysterious lands...
image: https://example.com/image.jpg
author: Your Name
tags: [adventure, fantasy, mystery]

# Game mechanics
score: 0
types:
  explorer: 0
  warrior: 0
  scholar: 0

# Story configuration
thoughts:
  - start.md
  - choice1.md
  - choice2.md
  - ending.md
```

## 📝 Creating Thought Files

### Basic Thought Structure
Each thought file (`.md`) should follow this format:

```markdown
---
id: start
title: The Beginning
set:
  score: "+5"
  types:
    explorer: "+2"
    warrior: "+1"
options:
  - text: Go left
    next: choice1
    set:
      score: "+3"
      types:
        explorer: "+1"
  - text: Go right
    next: choice2
    set:
      score: "+2"
      types:
        warrior: "+1"
---

# The Beginning

You find yourself at a crossroads in a mysterious forest. The path splits in two directions...

**What do you do?**
```

### Thought File Components

#### Frontmatter (YAML)
- **`id`**: Unique identifier for this thought
- **`title`**: Display title (optional)
- **`set`**: Initial state changes when this thought is reached
- **`options`**: Array of choices available to the player

#### Options
Each option has:
- **`text`**: The choice text displayed to the player
- **`next`**: The ID of the next thought to go to
- **`set`**: State changes when this option is chosen

#### Content
- **Markdown content** describing the current situation
- **Can include images, formatting, etc.**
- **Use `**bold**` for emphasis**

## 🎮 Game Mechanics

### Score System
- **`score`**: Numeric value that can be increased/decreased
- **Use `"+5"` or `"-3"` syntax** in set blocks
- **Accumulates throughout the story**

### Type System
- **`types`**: Character attributes that can be developed
- **Common types**: `explorer`, `warrior`, `scholar`, `mage`, `rogue`
- **Use `"+2"` or `"-1"` syntax** to modify types
- **Types can unlock conditional content**

### Conditional Content
Use Handlebars helpers to show content based on game state:

```markdown
{{#if (type "explorer" 3)}}
  **Your explorer instincts kick in!** You notice subtle clues that others might miss.
{{/if}}

{{#if (score 10)}}
  **You've gained enough experience** to unlock the secret path.
{{/if}}

{{#if (hasType "warrior")}}
  **Your warrior training** helps you assess the threat level.
{{/if}}
```

## 🔧 Available Handlebars Helpers

### Type Helpers
- **`(type "typeName" value)`**: Check if a type has at least the specified value
- **`(hasType "typeName")`: Check if a type exists and has any value
- **`(typeScore "typeName")`: Get the current value of a type
- **`(typeGroup "groupName" "typeName")`: Check if a type belongs to a group

### Score Helpers
- **`(score value)`**: Check if the score is at least the specified value

### State Helpers
- **`(visited "thoughtId")`: Check if a thought has been visited
- **`(visit_count "thoughtId")`: Get how many times a thought has been visited
- **`(first_time "thoughtId")`: Check if this is the first visit
- **`(returning "thoughtId")`: Check if this is a return visit

### Logic Helpers
- **`(if condition)`**: Standard if statement
- **`(unless condition)`**: Unless statement (opposite of if)
- **`(each array)`**: Loop through an array
- **`(with context)`**: Change the context for a block
- **`(log message)`**: Log a message to the console (for debugging)

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
        mage: "+1"
  - text: Fight
    next: fight-path
    set:
      types:
        warrior: "+1"
  - text: Sneak past
    next: stealth-path
    set:
      types:
        rogue: "+1"
---

{{#if (type "mage" 2)}}
  **Your magical abilities** give you multiple options.
{{/if}}

{{#if (type "warrior" 2)}}
  **Your combat training** makes you confident in a fight.
{{/if}}

{{#if (type "rogue" 2)}}
  **Your stealth skills** suggest a sneaky approach.
{{/if}}

How do you proceed?
```

### State-Dependent Content
```markdown
---
id: returning-visitor
options:
  - text: Continue
    next: next-thought
---

{{#if (first_time "returning-visitor")}}
  Welcome! This is your first time here.
{{else}}
  Welcome back! You've been here {{visit_count "returning-visitor"}} times before.
{{/if}}

{{#if (score 20)}}
  **You're becoming quite experienced** in these lands.
{{/if}}
```

## 🚨 Important Rules

### 1. Thought IDs Must Be Unique
- Each thought file must have a unique `id` in its frontmatter
- IDs are used for navigation between thoughts

### 2. Valid Navigation Paths
- Every `next` value in options must point to an existing thought ID
- The `start.md` thought is automatically loaded when a story begins

### 3. File Naming
- **Thought files**: Use descriptive names like `start.md`, `crossroads.md`, `deep_ruins.md`
- **Metadata file**: Must be named `metadata.yml`
- **Manifest file**: Must be named `stories.json`

### 4. YAML Syntax
- **Use spaces, not tabs** for indentation
- **Quote strings** that contain special characters
- **Use arrays** for lists like `thoughts: [file1.md, file2.md]`

## 🔍 Testing Your Story

### 1. Validate Structure
- Check that all `next` references point to valid thought IDs
- Ensure `start.md` exists and is properly formatted
- Verify all thought files listed in `metadata.yml` exist

### 2. Test Navigation
- Start the story and follow each path
- Check that all choices lead to the expected thoughts
- Verify that state changes (score, types) work correctly

### 3. Test Conditionals
- Play through different paths to test conditional content
- Verify that type-based and score-based conditions work
- Test visit-based conditions by revisiting thoughts

## 📖 Best Practices

### Story Design
- **Start simple**: Begin with a basic story structure and add complexity
- **Plan your paths**: Map out the story flow before writing
- **Test thoroughly**: Play through all possible paths
- **Use meaningful IDs**: Make thought IDs descriptive and memorable

### Content Organization
- **Group related thoughts**: Use subdirectories for complex stories
- **Consistent naming**: Follow a consistent pattern for file names
- **Document your story**: Include comments in metadata for complex logic

### Performance
- **Optimize images**: Use appropriately sized images for web
- **Minimize file size**: Keep thought content concise but engaging
- **Efficient navigation**: Avoid unnecessary back-and-forth between thoughts

## 🆘 Troubleshooting

### Common Issues

#### Story Not Loading
- Check that `stories.json` includes your story ID
- Verify `metadata.yml` has the correct `id` field
- Ensure all required fields are present

#### Thoughts Not Found
- Verify all thought files listed in `metadata.yml` exist
- Check that file names match exactly (including case)
- Ensure thought files are in the `thoughts/` subdirectory

#### Navigation Errors
- Check that all `next` values point to valid thought IDs
- Verify that thought IDs are unique across the entire story
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
