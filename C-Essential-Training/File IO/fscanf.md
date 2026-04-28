Sure! Here's a simple example of how to use `fscanf` in C to read data from a file.

### 📄 Example: Read Name, Age, and Score from a File

Suppose you have a text file called `data.txt` with the following content:

```
John 25 88.5
Alice 30 92.3
Bob 22 76.0
```

### ✅ C Code:

```c
#include <stdio.h>

int main() {
    FILE *file;
    char name[50];
    int age;
    float score;

    // Open the file in read mode
    file = fopen("data.txt", "r");

    if (file == NULL) {
        printf("Unable to open file.\n");
        return 1;
    }

    // Read data from the file until end-of-file
    while (fscanf(file, "%s %d %f", name, &age, &score) == 3) {
        printf("Name: %s, Age: %d, Score: %.2f\n", name, age, score);
    }

    // Close the file
    fclose(file);

    return 0;
}
```

### 📌 Output:

```
Name: John, Age: 25, Score: 88.50
Name: Alice, Age: 30, Score: 92.30
Name: Bob, Age: 22, Score: 76.00
```

### 📝 Explanation:

- `fscanf(file, "%s %d %f", name, &age, &score)` reads one line from the file:
  - `%s` → string (name)
  - `%d` → integer (age)
  - `%f` → float (score)
- Loop continues while `fscanf` successfully reads 3 values.

Let me know if you want an example with other types or formats!
