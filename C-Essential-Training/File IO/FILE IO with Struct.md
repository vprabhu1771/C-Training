Here’s an example demonstrating **file I/O in C** using a **struct** along with `fprintf` and `fscanf` functions to **write** and **read** structured data:

---

### 📄 **Program Overview**  
✅ Define a `struct Student` with `name`, `age`, and `marks`.  
✅ Use `fprintf` to write student data to a file.  
✅ Use `fscanf` to read the data back from the file.

---

### ✅ **Code Example: Writing and Reading Struct Data**

```c
#include <stdio.h>

typedef struct {
    char name[50];
    int age;
    float marks;
} Student;

int main() {
    Student s1 = {"Alice", 20, 88.5}, s2 = {"Bob", 22, 91.0}, s3;
    FILE *file;

    // 📝 Write struct data to file
    file = fopen("students.txt", "w");
    if (file == NULL) {
        printf("Error opening file for writing.\n");
        return 1;
    }

    fprintf(file, "%s %d %.2f\n", s1.name, s1.age, s1.marks);
    fprintf(file, "%s %d %.2f\n", s2.name, s2.age, s2.marks);
    fclose(file);
    printf("Data written successfully.\n\n");

    // 📖 Read struct data from file
    file = fopen("students.txt", "r");
    if (file == NULL) {
        printf("Error opening file for reading.\n");
        return 1;
    }

    printf("Reading data from file:\n");
    while (fscanf(file, "%s %d %f", s3.name, &s3.age, &s3.marks) != EOF) {
        printf("Name: %s | Age: %d | Marks: %.2f\n", s3.name, s3.age, s3.marks);
    }

    fclose(file);
    return 0;
}
```

---

### 🚀 **Output Example:**

```plaintext
Data written successfully.

Reading data from file:
Name: Alice | Age: 20 | Marks: 88.50
Name: Bob | Age: 22 | Marks: 91.00
```

---

### 🔍 **Explanation:**  
1. **Struct Definition:**  
   `Student` contains `name`, `age`, and `marks`.

2. **Writing Data (`fprintf`):**  
   - Opens `students.txt` in write mode (`"w"`).  
   - `fprintf` formats and writes each field to the file.

3. **Reading Data (`fscanf`):**  
   - Opens the file in read mode (`"r"`).  
   - `fscanf` reads data into the struct variables.  
   - Loop runs until `EOF` (End Of File).

4. **Safety Tip:**  
   Always check if `file` is `NULL` to avoid crashes.

---

💡 **Want an example using `fwrite` and `fread` for binary files?** Let me know! 😃
