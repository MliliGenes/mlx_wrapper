# MLX42 Combined Library

This repository contains the necessary libraries and dependencies for using MLX42 — an extension of the 42 Network's graphics system. The project includes everything packaged together for easier integration into your graphical projects, removing the need to manage separate dependencies manually.

**Now supports both macOS and Linux!**

## Contents

### macOS (`mlx/macOS/`)
- **MLX42.h**: The header file required to use the MLX42 graphics functions
- **libmlx42_combined.a**: A single combined static library that merges all necessary components for MLX42 and its dependencies
- **libmlx42.a**: The original MLX42 library for use in traditional setups
- **libglfw3.a**: The GLFW library for window/context management

### Linux (`mlx/linux/`)
- **MLX42.h**: The header file required to use the MLX42 graphics functions
- **libmlx42_combined.a**: A single combined static library that merges all necessary components for MLX42 and its dependencies
- **libmlx42_linux.a**: The Linux-specific variant of the library
- **libglfw3_linux.a**: The GLFW library compiled for Linux

## Dependencies

This library includes and manages the following dependencies:

- **GLFW**: The library on which MLX42 relies for window/context management
- **OpenGL**: Used for graphics rendering
- **Cocoa, IOKit**: macOS-specific frameworks
- **X11, Xrandr, Xinerama, Xcursor, Xi**: Linux-specific libraries
- **Libm (math), Libdl (dynamic loading)**: Additional libraries used in conjunction with MLX42

## Installation

To integrate MLX42 into your project, follow the steps below:

### 1. Clone the Repository

```bash
git clone https://github.com/MliliGenes/mlx_wrapper.git
```

### 2. Include the Header and Link the Library

#### For macOS

In your project, include the header:

```c
#include "mlx/macOS/MLX42.h"
```

Then, link against the combined library:

```bash
MLX_LIBRARIES = mlx/macOS/libmlx42_combined.a \
    -framework Cocoa -framework OpenGL -framework IOKit -lm -ldl
```

#### For Linux

In your project, include the header:

```c
#include "mlx/linux/MLX42.h"
```

Then, link against the combined library:

```bash
MLX_LIBRARIES = mlx/linux/libmlx42_combined.a \
    -lX11 -lXrandr -lXinerama -lXcursor -lXi -lGL -lm -ldl -lpthread
```

### 3. Compile Your Code

Now, compile your project using the flags above. Example with gcc:

#### macOS
```bash
gcc -o your_project your_project.c $MLX_LIBRARIES
```

#### Linux
```bash
gcc -o your_project your_project.c $MLX_LIBRARIES
```

### 4. Running Your Project

Once the code is compiled, you can run your graphical project just like any other executable.

## Platform-Specific Notes

### macOS
- Uses Apple's native frameworks (Cocoa, OpenGL, IOKit)
- No additional system dependencies required

### Linux
- Requires X11 development libraries (usually pre-installed)
- If you encounter linking issues, ensure you have the necessary X11 development packages installed

## Usage

After including the appropriate platform-specific `MLX42.h` header and linking with the combined library, you can start using MLX42 functions for graphics rendering. Check the official documentation or example projects for detailed usage.

## Naming of the Combined Library

We've chosen to name the combined library `libmlx42_combined.a` because it encapsulates all the required components for using MLX42 seamlessly on both platforms. If you'd prefer a different name, feel free to adjust it in your project as needed.

## Contributing

Contributions are welcome! If you have any fixes or improvements, feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.