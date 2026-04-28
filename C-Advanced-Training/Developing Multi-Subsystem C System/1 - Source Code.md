Here’s a complete example of a simple C program with multiple subsystems. This example includes:

1. **OS Information** subsystem.
2. **Hardware Information** subsystem.
3. **Logging** subsystem.
4. **Main Program** that ties everything together.

### 1. **OS Information Subsystem**

**os_info.h**
```c
#ifndef OS_INFO_H
#define OS_INFO_H

void get_os_info(void);

#endif // OS_INFO_H
```

**os_info.c**
```c
#include <stdio.h>
#include "os_info.h"

void get_os_info(void) {
    #ifdef _WIN32
        printf("Operating System: Windows\n");
    #elif __unix__
        printf("Operating System: Unix\n");
    #elif __linux__
        printf("Operating System: Linux\n");
    #elif __APPLE__
        printf("Operating System: macOS\n");
    #else
        printf("Operating System: Unknown\n");
    #endif
}
```

### 2. **Hardware Information Subsystem**

**hardware_info.h**
```c
#ifndef HARDWARE_INFO_H
#define HARDWARE_INFO_H

void get_hardware_info(void);

#endif // HARDWARE_INFO_H
```

**hardware_info.c**
```c
#include <stdio.h>
#include "hardware_info.h"

void get_hardware_info(void) {
    // For demonstration purposes, we will just print a placeholder message
    printf("Hardware Information: Placeholder\n");
}
```

### 3. **Logging Subsystem**

**logging.h**
```c
#ifndef LOGGING_H
#define LOGGING_H

void initialize_logging(void);
void log_message(const char *message);

#endif // LOGGING_H
```

**logging.c**
```c
#include <stdio.h>
#include "logging.h"

void initialize_logging(void) {
    // Initialize logging system (for simplicity, we'll just print a message)
    printf("Logging initialized\n");
}

void log_message(const char *message) {
    // Log a message (for simplicity, we'll just print it to the console)
    printf("LOG: %s\n", message);
}
```

### 4. **Main Program**

**main.c**
```c
#include <stdio.h>
#include "os_info.h"
#include "hardware_info.h"
#include "logging.h"

int main(void) {
    // Initialize logging
    initialize_logging();

    // Log a startup message
    log_message("System is starting up");

    // Get and display OS information
    get_os_info();

    // Get and display hardware information
    get_hardware_info();

    // Log a shutdown message
    log_message("System is shutting down");

    return 0;
}
```

### 5. **Compile and Link**

To compile and link the program, you can use the following commands:

```sh
gcc -c os_info.c
gcc -c hardware_info.c
gcc -c logging.c
gcc -c main.c
gcc -o my_system os_info.o hardware_info.o logging.o main.o
```

### 6. **Run the Program**

To run the program, execute the following command:

```sh
./my_system
```

### Output

The output will vary depending on your operating system, but it should look something like this:

```
Logging initialized
LOG: System is starting up
Operating System: [Your OS]
Hardware Information: Placeholder
LOG: System is shutting down
```

This example is simplified for demonstration purposes. In a real-world scenario, you would replace the placeholder code with actual implementations for gathering hardware information, and you might use more sophisticated logging mechanisms.