# BLEH 3D Editor

BLEH 3D Editor is a Windows desktop 3D creation and simulation application
built by **decayzxz**. It provides a lightweight, Blender-inspired workspace
for creating scenes, editing objects, experimenting with physics, animating
transforms, designing procedural materials, and exploring atomic simulations.

## Copyright and ownership

Copyright (c) 2026 decayzxz. All rights reserved for the original BLEH
application source code, original editor UI, original scene systems, original
application artwork, original shaders, and original documentation unless a
file says otherwise.

BLEH and the BLEH 3D Editor name belong to decayzxz. You may use the released
application for personal, educational, and evaluation purposes. Do not
remove copyright notices, claim the BLEH source code as your own, or
redistribute modified binaries as official BLEH releases without permission
from decayzxz.

This copyright statement applies only to original BLEH work. Third-party
libraries, generated code, fonts, icons, and other external assets remain
owned by their respective authors and are governed by their own licenses.
Their licenses take priority over this project notice where applicable.

See [LICENSE.txt](LICENSE.txt) for the short distribution notice. This file
does not replace the licenses included by third-party projects.

## Main features

### 3D scene editing

- Real-time OpenGL 3.3 viewport
- Visible ground plane for orientation and depth
- Scene hierarchy and Outliner
- Object selection, deletion, duplication, renaming, hiding, and focusing
- Position, rotation, and scale editing
- Live X, Y, and Z transform values in the Inspector
- Transform reset and object visibility controls
- Automatic selection of newly created objects
- New objects spawned in front of the camera

### Procedural geometry

- Cube
- Sphere
- Plane
- Cylinder
- Cone
- Capsule
- Torus

The sphere, cylinder, cone, capsule, and torus use generated mesh geometry
with vertices, normals, UV coordinates, and indexed triangles rather than
being displayed as cube placeholders.

### Camera and navigation

- `W`, `A`, `S`, and `D` movement
- Arrow-key camera movement
- `Q` and `E` vertical movement
- Right-mouse camera look
- Left `Shift` speed boost
- Camera position, rotation, field of view, and clipping controls
- Camera reset and focus behavior

### Object manipulation

- Move, rotate, and scale tools
- Left-mouse drag manipulation
- `Shift` drag support for depth movement
- Transform recording while dragging
- Snapping and proportional-editing settings
- Wireframe and viewport display options

### Physics

- Gravity simulation
- Fixed-step-safe delta handling
- Ground collision
- Bounce and restitution
- Friction
- Mass
- Collision radius
- Velocity controls
- Static-body mode
- Per-object gravity toggle
- Velocity reset

Physics controls are available through the Inspector and are designed for
lightweight interactive demonstrations rather than production rigid-body
simulation.

### Materials and rendering

- Lit shading
- Unlit shading
- Toon shading
- Glossy shading
- Base material color
- Emission
- Metallic response
- Roughness
- Texture scale
- Procedural checker pattern
- Procedural stripe pattern
- Procedural band pattern
- Exposure and gamma controls
- Ambient-occlusion and bloom settings
- World and render settings

### Animation and timeline

- Timeline with configurable frame range
- Playback and frame stepping
- Playback speed
- Transform keyframes
- X, Y, and Z transform recording
- Interpolation during playback
- Bounce animation preset
- Spin animation preset
- Pulse animation preset
- Record mode for automatic transform capture

### Atom Studio

Atom Studio creates an editable atomic simulation scene inside the same
project. It is intended for visualization and experimentation, not a
scientifically complete quantum-mechanics simulator.

- Atom project creation
- Nucleus creation
- Multiple nuclei
- Electron creation and removal
- Electron orbit targeting
- Electron orbit radius and speed
- Electron spin
- Atomic number
- Nucleus mass
- Gravity controls
- Electric-field controls
- Magnetic-field controls
- Electron collision separation
- Optional nucleus collision separation
- Animated electron spheres
- Field-line display setting
- Element presets:
  - Hydrogen
  - Helium
  - Carbon
  - Oxygen
  - Iron
  - Gold

### Projects and editor tools

- New project workflow
- New Atom Project workflow
- Project save and load
- Saved Files browser for local `.bleh` projects
- Startup welcome and terms screen
- Local terms-acceptance marker
- File, Edit, Add, Select, View, Help, Object, Mesh, Render, and Window menus
- Asset browser
- Console history and status feedback
- Scene statistics
- Tool Settings
- World Settings
- Render Settings
- Project Settings
- Keyboard-shortcut help
- Dear ImGui demo access
- Dark navy and cyan editor theme
- Rounded panels and colored action controls

## User interface layout

The editor follows a Blender-inspired layout:

- **Left:** Outliner and scene object list
- **Center:** 3D viewport
- **Right:** Inspector and options
- **Bottom:** Timeline and playback controls

The selected object's transform, material, physics, and animation state are
shown in the right-side Inspector.

## Controls

| Input | Action |
|---|---|
| `W` / `A` / `S` / `D` | Move the camera |
| Arrow keys | Move the camera forward, backward, left, or right |
| `Q` / `E` | Move the camera down or up |
| `Left Shift` | Move faster |
| Right mouse drag | Look around |
| Left mouse drag | Manipulate the selected object |
| `Shift` + left drag | Move the selected object along depth |

Additional actions are available through the menus, toolbar, Inspector,
Outliner, and Timeline.

## Project structure

```text
BLEH/
├── assets/                 Project assets
├── shaders/                GLSL vertex and fragment shaders
├── src/
│   ├── Assets/             Asset management
│   ├── Core/               Application, window, and input lifecycle
│   ├── Editor/             Dear ImGui editor UI and workflows
│   ├── Renderer/           OpenGL renderer and shader wrappers
│   ├── Scene/              Objects, meshes, camera, lights, materials
│   └── Serialization/      Project save/load support
├── third_party/            Bundled helper code such as stb_image
├── CMakeLists.txt          Build and installer configuration
├── LICENSE.txt             BLEH distribution copyright notice
└── README.md               This documentation
```

## Programming languages and formats

- **C++20:** Application, editor, renderer, scene, physics, animation,
  project, and asset-management code
- **C11:** The generated GLAD OpenGL loader
- **GLSL:** OpenGL vertex and fragment shaders
- **Python 3.9:** Build-time GLAD generation only; it is not the application
  runtime language
- **CMake:** Build configuration, dependency configuration, installation,
  and CPack packaging
- **PowerShell:** Optional Windows build and packaging commands
- **JSON-like project data:** Used by the `.bleh` project serialization
  workflow where applicable

## Technology stack

- C++20
- OpenGL 3.3 core profile
- GLFW for window creation and input
- GLM for mathematics
- GLAD for OpenGL function loading
- Dear ImGui for the editor interface
- Assimp for model and asset pipeline support
- stb_image for image loading support
- CMake for builds
- CPack and WiX for the Windows MSI installer
- MinGW-w64 for the packaged Windows compiler runtime

Third-party projects retain their own copyrights and licenses. Refer to
their upstream license files and project pages for complete legal terms:

- GLFW: https://github.com/glfw/glfw
- GLM: https://github.com/g-truc/glm
- GLAD: https://github.com/Dav1dde/glad
- Dear ImGui: https://github.com/ocornut/imgui
- Assimp: https://github.com/assimp/assimp
- stb: https://github.com/nothings/stb
- MinGW-w64: https://www.mingw-w64.org/
- CMake: https://cmake.org/
- WiX Toolset: https://wixtoolset.org/

## Requirements

For normal use:

- Windows 10 or newer
- OpenGL 3.3-compatible graphics hardware and drivers
- A monitor capable of displaying the editor window

For building from source:

- CMake 3.20 or newer
- A C++20-compatible compiler
- A C11-compatible C compiler
- Git or locally available dependencies
- Python 3 for GLAD generation
- OpenGL development libraries and headers

The repository also contains bundled Windows build tools used by the
maintainer's build environment. They are not required when using the MSI.

## Build from source

From the project directory:

```bash
cmake -S . -B build
cmake --build build --config Release
```

The executable is written to:

```text
build/bin/BLEH3D.exe
```

If a previous `BLEH3D.exe` process is open, close it before rebuilding so the
linker can replace the executable.

## Windows MSI installer

The release package is:

```text
BLEH 3D Editor-1.0.0-win64.msi
```

The MSI installs:

- `BLEH3D.exe`
- MinGW runtime DLLs
- `shaders/`
- `assets/`
- `README.md`
- `LICENSE.txt`

It also creates BLEH 3D Editor shortcuts on the Desktop and in the Start
Menu and registers an uninstall entry. The installer is generated with CPack
using the WiX generator.

## Terms and privacy

The startup dialog identifies the application as “BLEH was built by
decayzxz” and asks the user to accept the displayed terms before entering the
editor. The current implementation stores a local acceptance marker in the
application's working directory. BLEH does not intentionally transmit scene
data to a remote service.

Users are responsible for the files, models, images, projects, and other
content they import or create. Do not import material that you do not have
permission to use.

## Current scope

BLEH is an expandable editor and simulation prototype, not a complete
replacement for Blender or a production physics engine. Some advanced
features remain future work, including full undo/redo history, production
rendering, complete material serialization, a comprehensive model-import
dialog, advanced node editing, audio systems, and physically accurate
quantum-mechanics simulation.

## Credits

Original BLEH application and editor concept: **decayzxz**.

BLEH incorporates or builds with the open-source projects listed in the
Technology stack section. Appreciation and copyright remain with those
projects' authors and contributors.

## Contact and bug reports

When reporting a problem, include:

1. Windows version
2. Graphics hardware and driver version
3. BLEH version
4. Steps to reproduce the problem
5. Console output or screenshots when available
6. Whether the issue occurs in the installed MSI or a source build
