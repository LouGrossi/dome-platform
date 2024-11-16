# Parametric Deck Designer for FreeCAD

A parametric deck design macro for FreeCAD that generates customizable octagonal decks with square platform extensions. Features include support structures, railings, footings, and ADA compliance measures.

## Features

- Octagonal platform with square extension
- Support structure (beams, joists, bracing)
- Concrete footings with configurable placement
- Railing system with posts and pickets
- Ventilated skirting system
- ADA compliance measures
- Configurable dimensions and materials
- Imperial to metric conversion

## Prerequisites

- FreeCAD (version 0.20 or later)
- Python 3.8+

## Installation

### Installing FreeCAD on macOS

1. Using Homebrew (recommended):
```bash
brew install --cask freecad
```

2. Alternative: Download from FreeCAD website
   - Visit [FreeCAD Downloads](https://www.freecadweb.org/downloads.php)
   - Download the macOS version
   - Drag FreeCAD to your Applications folder

### Setting Up the Macro

1. Open FreeCAD
2. Go to Macro menu -> Macros...
3. Click "Create"
4. Name the macro 'deck.FCMacro'
5. Copy the entire macro code into the editor
6. Save the macro

Alternative method:
1. Navigate to FreeCAD's macro directory:
```bash
cd ~/Library/Application\ Support/FreeCAD/Macro/
```
2. Copy deck.FCMacro to this location

## Usage

1. Open FreeCAD
2. Create a new document: File -> New
3. Open Macro menu -> Macros...
4. Select 'deck.FCMacro'
5. Click "Execute"

## Configuration

The deck design is controlled by the DECK_CONFIG dictionary in deck.FCMacro. Key configurations include:

### Platform Dimensions
```python
'platform': {
    'octagonal_diameter': 21 * 304.8,    # 6400.8 mm (21 feet)
    'square_side': 10 * 304.8,           # 3048.0 mm (10 feet)
    'elevation': 24 * 25.4,              # 609.6 mm (24 inches)
    'board_thickness': 1.5 * 25.4        # 38.1 mm (1.5 inches)
}
```

### Structural Elements
```python
'structural': {
    'central_beam': {
        'width': 2 * (1.5 * 25.4),       # 76.2 mm (2x 1.5 inch boards)
        'height': 9.25 * 25.4,           # 234.95 mm (9.25 inches)
        'reinforced': True
    },
    'floor_joists': {
        'width': 1.5 * 25.4,             # 38.1 mm (1.5 inches)
        'height': 9.25 * 25.4,           # 234.95 mm (9.25 inches)
        'spacing': 16 * 25.4,            # 406.4 mm (16 inches OC)
        'reinforced': True
    }
}
```

### Feature Toggles
```python
'features': {
    'platform': True,          # Base platform
    'central_beam': True,      # Central support beam
    'floor_joists': True,      # Floor joists
    'rim_joists': True,        # Perimeter joists
    'cross_bracing': True,     # Metal cross bracing
    'footings': True,          # Concrete footings
    'railing': True,           # Safety railing system
    'skirting': True,          # Ventilated skirting
}
```

## Customization

To modify the deck design:

1. Open deck.FCMacro
2. Locate the DECK_CONFIG dictionary
3. Adjust dimensions and configurations as needed
4. Save the file
5. Run the macro

Note: The .state directory contains a statefile that tracks the project's state for AI development tools and project recreation purposes. It should not be used for configuration.

## Development

The project uses a configuration-driven architecture where all settings are stored in the DECK_CONFIG dictionary within deck.FCMacro. The macro reads this configuration and generates the 3D model accordingly.

### Project Structure
- deck.FCMacro: Main implementation and configuration
- .state/statefile.txt: Project state tracking for AI tools
- README.md: Documentation

## License

MIT License

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## Support

For issues and feature requests, please create an issue in the repository. 