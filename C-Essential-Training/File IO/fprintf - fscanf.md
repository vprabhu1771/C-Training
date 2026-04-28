```
#include<stdio.h>

struct student
{
    char *name;

	char *course;

    char gender;
};

int main()
{

    struct student records[2] = {
        {"nova", "C", 'M'}, 
        {"vishnu", "C", 'M'}
    };

    FILE *file = fopen("students.txt", "w");

    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }

    // Write each student's data to the file
    for (int i = 0; i < 2; i++) {
        fprintf(file, "%s %s %c\n", records[i].name, records[i].course, records[i].gender);
    }

    // Close the file
    fclose(file);

    // Read from file
    file = fopen("students.txt", "r");
    if (file == NULL) {
        printf("Error opening file for reading!\n");
        return 1;
    }

    char name[100], course[100];
    char gender;
    printf("\nReading from file:\n");

    while (fscanf(file, "%s %s %c", name, course, &gender) == 3) {
        printf("Name: %s, Course: %s, Gender: %c\n", name, course, gender);
    }

    fclose(file);

    return 0;
}
```

# OUTPUT

```
Reading from file:
Name: nova, Course: C, Gender: M
Name: vishnu, Course: C, Gender: M
```
