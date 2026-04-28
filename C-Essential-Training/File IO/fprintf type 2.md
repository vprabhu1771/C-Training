Great! Here's a complete example of using `fprintf` in C to **write structure data to a file**.

---

### 📄 Example: Write Struct Data to a File using `fprintf`

#### ✅ Step 1: Define a structure

```c
#include <stdio.h>

// Define a structure for student data
struct Student {
    char name[50];
    int age;
    float score;
};
```

#### ✅ Step 2: Fill the structure and write to file

```c
int main() {
    FILE *file;
    struct Student students[3] = {
        {"John", 20, 85.5},
        {"Alice", 22, 90.0},
        {"Bob", 19, 78.2}
    };

    // Open file in write mode
    file = fopen("students.txt", "w");

    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }

    // Write header
    fprintf(file, "Name Age Score\n");
    fprintf(file, "---------------------\n");

    // Write each student's data to the file
    for (int i = 0; i < 3; i++) {
        fprintf(file, "%s %d %.2f\n", students[i].name, students[i].age, students[i].score);
    }

    // Close the file
    fclose(file);

    printf("Student data written to file successfully.\n");
    return 0;
}
```

---

### 📂 Output in `students.txt`:

```
Name Age Score
---------------------
John 20 85.50
Alice 22 90.00
Bob 19 78.20
```

---

### 📝 Explanation:

- `struct Student` holds each student's name, age, and score.
- `fprintf` is used inside a loop to write each struct's data to the file.
- `%.2f` ensures the float score is written with 2 decimal places.

Let me know if you’d like the reverse example using `fscanf` to read structs from a file!
