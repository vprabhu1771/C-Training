```c
#include<stdio.h>

int main()
{
    char name[10];

    int eng_mark, tam_mark, mat_mark, phy_mark, chem_mark, total;

    FILE *marksheet;

    printf("Enter your name\n");

    scanf("%s", name);

    printf("enter your english mark\n");

    scanf("%d", &eng_mark);

    printf("enter your tamil mark\n");

    scanf("%d", &tam_mark);

    printf("enter your maths mark\n");

    scanf("%d", &mat_mark);

    printf("enter your physics mark\n");

    scanf("%d", &phy_mark);

    printf("enter your chemistry mark\n");

    scanf("%d", &chem_mark);

    total += tam_mark;

    total += eng_mark;

    total += mat_mark;

    total += phy_mark;

    total += chem_mark;

    printf("Student Name\t\t:\t%s\n", name);

    printf("english\t\t:\t%d\n", eng_mark);

    printf("tamil\t\t:\t%d\n", tam_mark);

    printf("maths\t\t:\t%d\n", mat_mark);

    printf("physics\t\t:\t%d\n", phy_mark);

    printf("chemistry\t:\t%d\n", chem_mark);

    printf("total\t:\t%d\n", total);

    marksheet = fopen("marksheet.txt", "a");

    if(marksheet == NULL)
    {
        printf("Sorry File cannot created\n");
    }
    else
    {
        printf("File created\n");

        fprintf(marksheet, "Student Name\t\t:\t%s\n", name);

        fprintf(marksheet, "english\t\t:\t%d\n", eng_mark);

        fprintf(marksheet, "tamil\t\t:\t%d\n", tam_mark);

        fprintf(marksheet, "maths\t\t:\t%d\n", mat_mark);

        fprintf(marksheet, "physics\t\t:\t%d\n", phy_mark);

        fprintf(marksheet, "chemistry\t:\t%d\n", chem_mark);

        fprintf(marksheet, "total\t\t:\t%d\n", total);
    }

  return 0;
}
```
