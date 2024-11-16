# Deck Design State File
# Last Updated: [Current Date]

# Project Configuration
PROJECT_NAME: Deck Design
PROJECT_VERSION: 1.0.0
PROJECT_DESCRIPTION: Octagonal deck with square platform extension

# Feature Configuration
FEATURES:
  - platform: true          # Base platform
  - central_beam: true      # Central support beam
  - floor_joists: true      # Floor joists
  - rim_joists: true       # Perimeter joists
  - cross_bracing: true    # Metal cross bracing
  - footings: true         # Concrete footings
  - railing: true          # Safety railing system
  - skirting: true         # Ventilated skirting
  - drainage_holes: true   # Water drainage system
  - ventilation_gaps: true # Under-deck ventilation
  - dome_support: true     # Additional reinforcement for dome
  - deep_footings: false   # 48-inch footings for frost protection
  - beam_reinforcement: true # Extra beam support
  - joist_reinforcement: true # Extra joist support
  - stairs: false          # Stair system
  - slope: false           # Platform slope for drainage
  - ada_compliance: true   # ADA compliance measures

# Dimensional Configuration
DIMENSIONS:
  PLATFORM:
    octagonal_diameter: 6400.8  # mm (21 feet)
    square_side: 3048.0        # mm (10 feet)
    elevation: 609.6           # mm (24 inches)
    board_thickness: 38.1      # mm (1.5 inches)

  STRUCTURAL:
    central_beam:
      width: 76.2             # mm (2x 1.5 inch boards)
      height: 234.95          # mm (9.25 inches)
      reinforced: true

    floor_joists:
      width: 38.1             # mm (1.5 inches)
      height: 234.95          # mm (9.25 inches)
      spacing: 406.4          # mm (16 inches OC)
      reinforced: true

    cross_bracing:
      spacing: 1219.2         # mm (4 feet)
      material: metal

    rim_joists:
      width: 38.1             # mm (1.5 inches)
      height: 234.95          # mm (9.25 inches)

  FOOTINGS:
    base_diameter: 304.8      # mm (12 inches)
    post_diameter: 152.4      # mm (6 inches)
    depth: 914.4             # mm (36 inches)
    max_spacing: 2438.4      # mm (8 feet)
    min_spacing: 1219.2      # mm (4 feet)
    edge_margin: 304.8       # mm (1 foot)

  RAILING:
    height: 1000.0           # mm (39.37 inches)
    post_size: 101.6         # mm (4 inches)
    rail_width: 50.8         # mm (2 inches)
    rail_height: 101.6       # mm (4 inches)
    picket_size: 50.8        # mm (2 inches)
    picket_spacing: 101.6    # mm (4 inches)

  SKIRTING:
    ventilation_gap: 3.175   # mm (1/8 inch)
    lattice_spacing: 50.8    # mm (2 inches)

# Material Configuration
MATERIALS:
  wood_color: [0.85, 0.75, 0.60]    # Light wood color (RGB)
  metal_color: [0.70, 0.70, 0.70]   # Steel gray color (RGB)
  concrete_color: [0.80, 0.80, 0.80] # Light gray color (RGB)

# Implementation Details
IMPLEMENTATION:
  - Platform created using boolean fusion of octagonal and square shapes
  - Central beam implemented as cross-beam layout for enhanced support
  - Floor joists placed parallel to X-axis with specified spacing
  - Cross bracing implemented as X-pattern metal supports
  - Footings placed using calculated grid with edge support
  - Railing system includes posts, horizontal rails, and vertical pickets
  - Skirting includes ventilation gaps for proper airflow
  - All measurements converted from imperial to metric for precision
  - Error handling implemented for all critical operations
  - Validation checks included for structural integrity

# Current Issues
KNOWN_ISSUES:
  - Joist trimming requires optimization for platform edges
  - Footing placement needs refinement for optimal support
  - Railing post placement needs adjustment for vertices

# Change History
CHANGES:
  - Initial implementation of core features
  - Added support structure with cross-beam layout
  - Implemented ventilation system in skirting
  - Added structural validation checks
  - Updated joist creation method for better edge alignment

# Dependencies
DEPENDENCIES:
  - FreeCAD
  - Part module
  - Draft module
  - Base module
  - Math module
