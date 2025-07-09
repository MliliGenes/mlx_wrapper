# MLX42 Combined Library

This repository contains the necessary libraries and dependencies for using MLX42 — an extension of the 42 Network's graphics system. The project includes everything packaged together for easier integration into your graphical projects, removing the need to manage separate dependencies manually.

## Contents

- **mlx/MLX42.h**: The header file required to use the MLX42 graphics functions
- **mlx/libmlx42_combined.a**: A single combined static library that merges all necessary components for MLX42 and its dependencies
- **mlx/libmlx42.a**: The original MLX42 library for use in traditional setups
- **mlx/libglfw3.a**: The GLFW library for window/context management

## Dependencies

This library includes and manages the following dependencies:

- **GLFW**: The library on which MLX42 relies for window/context management
- **OpenGL**: Used for graphics rendering
- **Cocoa, IOKit**: macOS-specific frameworks
- **Libm (math), Libdl (dynamic loading)**: Additional libraries used in conjunction with MLX42

## Installation

To integrate MLX42 into your project, follow the steps below:

### 1. Clone the Repository

```bash
git clone https://github.com/MliliGenes/mlx_wrapper.git
```

### 2. Include the Header and Link the Library

In your project, include the header:

```c
#include "mlx/MLX42.h"
```

Then, link against the combined library. On macOS, use the following compile flags:

#### macOS Compile Flags

```bash
MLX_LIBRARIES = mlx/libmlx42_combined.a \
    -framework Cocoa -framework OpenGL -framework IOKit -lm -ldl
```

### 3. Compile Your Code

Now, compile your project using the flags above. Example with gcc:

```bash
gcc -o your_project your_project.c $MLX_LIBRARIES
```

### 4. Running Your Project

Once the code is compiled, you can run your graphical project just like any other executable.

## Usage

After including the `mlx/MLX42.h` header and linking with the combined library, you can start using MLX42 functions for graphics rendering. Check the official documentation or example projects for detailed usage.

## Naming of the Combined Library

We've chosen to name the combined library `libmlx42_combined.a` because it encapsulates all the required components for using MLX42 seamlessly. If you'd prefer a different name, feel free to adjust it in your project as needed.

## Contributing

Contributions are welcome! If you have any fixes or improvements, feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.