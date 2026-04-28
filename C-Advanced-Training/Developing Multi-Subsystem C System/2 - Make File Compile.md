Here’s a `Makefile` to manage the build process for the C project with multiple subsystems. The `Makefile` will compile each source file into an object file and then link them into a single executable.

### `Makefile`

```makefile
# Compiler and flags
CC = gcc
CFLAGS = -Wall -Wextra -O2

# Targets and files
TARGET = my_system
SRCS = main.c os_info.c hardware_info.c logging.c
OBJS = $(SRCS:.c=.o)

# Default target
all: $(TARGET)

# Link the object files to create the executable
$(TARGET): $(OBJS)
	$(CC) $(CFLAGS) -o $@ $(OBJS)

# Compile each source file into an object file
%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

# Clean up build files
clean:
	rm -f $(TARGET) $(OBJS)

# Phony targets
.PHONY: all clean
```

### Explanation

- **Compiler and Flags:**
  - `CC = gcc`: Specifies the compiler to use.
  - `CFLAGS = -Wall -Wextra -O2`: Compiler flags for warnings and optimization.

- **Targets and Files:**
  - `TARGET`: The name of the final executable.
  - `SRCS`: List of source files.
  - `OBJS`: List of object files (created from the source files).

- **Default Target (`all`):**
  - This target builds the executable by linking the object files.

- **Link Target (`$(TARGET)`):**
  - This rule links object files to create the executable.

- **Compile Target (`%.o`):**
  - This rule compiles each `.c` file into a `.o` object file.

- **Clean Target (`clean`):**
  - This rule removes the executable and object files.

- **Phony Targets (`.PHONY`):**
  - Ensures that `all` and `clean` are treated as phony targets, so they are always executed when invoked.

### Using the `Makefile`

1. **Build the Project:**
   ```sh
   make
   ```

2. **Clean the Build Files:**
   ```sh
   make clean
   ```

This `Makefile` provides a simple and efficient way to manage the build process for a multi-module C project. Adjust the source file list and any specific compiler flags as needed for your project.