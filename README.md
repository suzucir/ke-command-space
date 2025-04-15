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

## Notes

- If you're using macOS Spotlight with Command+Space, you'll need to change your Spotlight shortcut in System Preferences → Keyboard → Shortcuts → Spotlight
- Make sure both English and Japanese input sources are added in System Preferences → Keyboard → Input Sources

## License

MIT
