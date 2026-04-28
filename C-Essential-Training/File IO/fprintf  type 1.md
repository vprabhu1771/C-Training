Sure! Here's a simple example of how to use `fprintf` in C to **write data to a file**.

---

### 📄 Example: Write Name, Age, and Score to a File

```c
#include <stdio.h>

int main() {
    FILE *file;
    char name1[] = "John";
    int age1 = 25;
    float score1 = 88.5;

    char name2[] = "Alice";
    int age2 = 30;
    float score2 = 92.3;

    // Open the file in write mode ("w" creates a new file or overwrites an existing one)
    file = fopen("output.txt", "w");

    if (file == NULL) {
        printf("Unable to open file for writing.\n");
        return 1;
    }

    // Write formatted data to the file
    fprintf(file, "%s %d %.2f\n", name1, age1, score1);
    fprintf(file, "%s %d %.2f\n", name2, age2, score2);

    // Close the file
    fclose(file);

    printf("Data written to file successfully.\n");

    return 0;
}
```

---

### 📂 After running this code, `output.txt` will contain:

```
John 25 88.50
Alice 30 92.30
```

---

### 📝 Explanation:

- `fprintf` works like `printf`, but writes to a **file** instead of the screen.
- The format specifiers are the same: `%s` for strings, `%d` for integers, and `%.2f` for floats with 2 decimal places.
- `fopen("output.txt", "w")` opens the file for writing.

Let me know if you want to append to the file instead (`"a"` mode) or write more complex structures like arrays or structs!
