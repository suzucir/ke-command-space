# Karabiner-Elements Custom Rules

Custom key mapping rules for macOS using Karabiner-Elements.

## Features

### Command+Space Language Toggle

This rule allows you to toggle between English and Japanese input methods using Command+Space. This is especially useful for US keyboard layouts.

```json
{
  "description": "Command+Space toggles between English and Japanese",
  "manipulators": [
    {
      "type": "basic",
      "from": {
        "key_code": "spacebar",
        "modifiers": {
          "mandatory": ["command"],
          "optional": ["any"]
        }
      },
      "to": [
        {
          "key_code": "japanese_kana"
        }
      ],
      "conditions": [
        {
          "type": "input_source_if",
          "input_sources": [
            {
              "language": "en"
            }
          ]
        }
      ]
    },
    {
      "type": "basic",
      "from": {
        "key_code": "spacebar",
        "modifiers": {
          "mandatory": ["command"],
          "optional": ["any"]
        }
      },
      "to": [
        {
          "key_code": "japanese_eisuu"
        }
      ],
      "conditions": [
        {
          "type": "input_source_if",
          "input_sources": [
            {
              "language": "ja"
            }
          ]
        }
      ]
    }
  ]
}
```

## Installation

1. Install [Karabiner-Elements](https://karabiner-elements.pqrs.org/)
2. Copy the rule JSON to `~/.config/karabiner/assets/complex_modifications/`
3. Open Karabiner-Elements preferences
4. Go to "Complex Modifications" tab
5. Click "Add rule" and enable the rule

## Prerequisites

- macOS
- Karabiner-Elements
- Japanese input source must be added to your input sources in System Preferences

## Important: Spotlight Conflict

By default, macOS assigns Command+Space to Spotlight search. This custom rule will conflict with that default setting. To use this custom rule, you must first change the Spotlight shortcut:

1. Open System Preferences → Keyboard → Shortcuts → Spotlight
2. Change the "Show Spotlight search" shortcut to something else (e.g., Option+Space)
3. Alternatively, you can disable the Spotlight shortcut completely if you prefer

Without changing this setting, the Command+Space input switching will not work properly as Spotlight will intercept the keystroke before Karabiner-Elements can process it.

## Additional Notes

- Make sure both English and Japanese input sources are added in System Preferences → Keyboard → Input Sources
- If you experience any issues, check that Karabiner-Elements has proper permissions in System Preferences → Security & Privacy → Privacy → Accessibility

## License

MIT
