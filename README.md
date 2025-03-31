# GBA Framework

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

This is a C++ framework for developing Game Boy Advance (GBA) games using
Object-Oriented Programming (OOP) principles. The framework provides core
functionality for graphics, input handling, sound, and system initialization,
making it easier to develop and maintain GBA games.

## Purpose

The purpose of this framework is to provide a reusable and organized codebase
for GBA development. By using this framework, you can focus on game-specific
logic while leveraging the core functionalities provided by the framework. This
approach promotes code reuse and maintainability across multiple GBA projects.

## Features

- **Graphics**: Initialization and rendering of graphics.
- **Input Handling**: Reading and processing input from the GBA buttons.
- **Sound**: Initialization and management of sound.
- **System Initialization**: Setting up hardware registers and waiting for VBlank.

## Getting Started

### Prerequisites

- **DevkitARM**: Ensure you have DevkitARM installed for GBA development.
- **Make**: A build system like `make` to compile the project.

### Installation

1. **Clone the Repository**:

    ```sh
    git clone https://github.com/yourusername/gba-framework.git
    ```

2. **Include the Framework in Your Project**:

    You can add the framework as a submodule to your GBA project:

    ```sh
    cd /path/to/your-gba-project
    git submodule add https://github.com/yourusername/gba-framework.git
    ```

### Usage

Include the necessary headers from the framework and initialize the core components in your project.

**Example `main.cpp`**:

    ```cpp
    #include "gba-framework/include/system.hpp"
    #include "gba-framework/include/graphics.hpp"
    #include "gba-framework/include/input.hpp"
    #include "gba-framework/include/sound.hpp"

    int main()
    {
        System system;
        Graphics graphics;
        Input input;
        Sound sound;

        system.Init();
        graphics.Init();
        input.Init();
        sound.Init();

        for (;;)
        {
            input.ReadKeys();
            // Update game state
            graphics.Render();
            system.WaitForVBlank();
        }

        return 0;
    }
    ```

### Documentation

The framework is organized into the following core classes:

- **System**: Handles system initialization and VBlank waiting.
- **Graphics**: Manages graphics initialization and rendering.
- **Input**: Handles input initialization and reading.
- **Sound**: Manages sound initialization.

#### System

**Header**: `gba-framework/include/system.hpp`

**Methods**:
- `void Init()`: Initializes the system and hardware registers.
- `void WaitForVBlank()`: Waits for the vertical blanking interval.

#### Graphics

**Header**: `gba-framework/include/graphics.hpp`

**Methods**:
- `void Init()`: Initializes the graphics system.
- `void Render()`: Renders graphics to the screen.

#### Input

**Header**: `gba-framework/include/input.hpp`

**Methods**:
- `void Init()`: Initializes the input system.
- `void ReadKeys()`: Reads the current state of the GBA buttons.

#### Sound

**Header**: `gba-framework/include/sound.hpp`

**Methods**:
- `void Init()`: Initializes the sound system.

### Contributing

Contributions are welcome! If you have suggestions for improvements or new features, feel free to open an issue or submit a pull request.

### License

This project is licensed under the GPL v3 License. See the [LICENSE](LICENSE) file for details.

### Acknowledgments

- Inspired by various GBA development resources and communities, but primarily [Pret](https://github.com/pret).