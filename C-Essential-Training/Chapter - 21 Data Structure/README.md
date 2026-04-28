# 1 - Basic Structure.

```
// standard input and output header file
#include<stdio.h>

// console input and output header file
#include<conio.h>

// structure declaration

struct date_of_birth
{
	int date;
	int month;
	int year;
};

// main function
void main()
{
	// structure initializing
	struct date_of_birth abi, ram;

	clrscr();

	abi.date = 3;

	abi.month = 8;

	abi.year = 1992;

	ram.date = 23;

	ram.month = 3;

	ram.year = 1990;

	printf(“%d - %d - %d\n”, abi.date, abi.month, abi.year);

	printf(“%d - %d - %d\n”, abi.date, abi.month, abi.year);

	getch();
}

output
3-8-1992
23-3-1990
```

# 2 - Basic Structure Initializing

```
// standard input and output header file
#include<stdio.h>

// console input and output header file
#include<conio.h>

// structure declaration

struct date_of_birth
{
	int date;
	int month;
	int year;
};

// main function
void main()
{
	// structure initializing
	struct date_of_birth abi = {3,8,1992}, ram = {23,3,1990};

	clrscr();

	printf(“%d - %d - %d\n”, abi.date, abi.month, abi.year);

	printf(“%d - %d - %d\n”, abi.date, abi.month, abi.year);

	getch();
}

output
3-8-1992
23-3-1990
```

# 3 - Account Structures

```
// standard input and output header file
#include<stdio.h>

// console input and output header file
#include<conio.h>

// array size
#define size 30

struct accounts
{
	int ac_no;

	int ac_type;

	char name[size];

	char street[size];

	char city_state[size];

	float balance;

	float last_payment;
};

// main function
void main()
{
	int ac_no;

	struct account raja = {1212, 1, “raja”, “m.g.road”, 
	“bangalore”, 2000.0, 500.0 };

	clrscr();

	puts(“Enter Account no”);

	scanf(“%d”, &ac_no);
	
	
	if(ac_no == raja.ac_no)
	{
	
	printf(“Account Holder Name\t:\t %s\n”,raja.name);		

		if(raja.ac_type == 1)
		{
			puts(“Account Type\t:\tSaving”);
		}
		else
		{
			puts(“Account Type\t:\tCurrent”);
		}

	printf(“Street\t:\t %s\n”,raja.street);		

	printf(“City or State\t:\t %s\n”,raja.city_state);		
	
	printf(“Last Payment\t:\t %.1f\n”, raja.last_payment);

	printf(“Balance\t:\t %.1f\n”,raja.balance);
	}

	getch();
}

output
Account Holder Name : raja
Account Type : Saving
Street : m.g.road
City or State : Banglore
Last Payment : 2000.0
Balance : 500.0
```

# 4 - Array of Structures

```
// standard input and output header file
#include<stdio.h>

// console input and output header file
#include<conio.h>

// array size
#define size 40


struct employee
{
	int emp_no;

	char emp_name[size];

	int emp_salary;
};

// main function
void main()
{
	int i;

	struct employee engineers[2];

	clrscr();

	for(i = 0; i < 2; i++)
	{
		printf(“index : %d\n”, i);

		puts(“Enter employee no\n”);

		scanf(“%d”, &engineers[i].emp_no);

		puts(“Enter employee name\n”);

		scanf(“%s”, engineers[i].name);

		puts(“Enter employee salary\n”);

		scanf(“%d”, &engineers[i].emp_salary);
	}	
	
	for(i = 0; i < 2; i++)
	{
	  printf(“employee no : %d\n”, engineers[i].emp_no);
	
       printf(“employee name : %s\n”, engineers[i].emp_name);

	  printf(“employee salary : %d\n”, engineers[i].salary);
	}

	getch();
}

output
index : 0
Enter employee no
121
Enter employee name
ram
Enter employee salary
2000

index : 1
Enter employee no
122
Enter employee name
abi
Enter employee salary
3000


employee no : 121

employee name : ram

employee salary : 2000


employee no : 122

employee name : abi

employee salary : 3000
```

# 5 - Passing Structures to Function

```
// standard input and output header file
#include<stdio.h>

// console input and output header file
#include<conio.h>

struct record
{
	char *name;

	int ac_no;

	char *ac_type;

	float balance;
};

// step 1 function declaration with structres parameter
struct recoard update(struct record cust);

// main function
void main()
{

	
 struct record customers = {“sanjey”, 3333, “saving” , 33.33};

 clrscr();

 puts(“Before update”);

 printf(“Name : %s\n”, customers.name);

 printf(“AC NO : %d\n”, customers.ac_no);

 printf(“Account Type : %s\n”, customers.ac_type);

 printf(“Balance : %.2f\n”, customers.balance);

 // step 3 function calling with structures arguments
 customer = update(customer);

 puts(“After update”);

 printf(“Name : %s\n”, customers.name);

 printf(“AC NO : %d\n”, customers.ac_no);

 printf(“Account Type : %s\n”, customers.ac_type);

 printf(“Balance : %.2f\n”, customers.balance);

 getch();

}

// step 2 function definition with structres parameter
struct recoard update(struct record cust)
{
	cust.name = “jones”;

	cust.ac_no = 9999;

	cust.ac_type = “current”;

	cust.balance = 100.0;

	return cust;
}

output
Before update
Name : sanjey
Account No : 3333
Account Type : saving
Balance : 33.33

After update
Name : jones
Account No : 9999
Account Type : current
Balance : 100.00
```

# 6 - Passing Structures to Function using Pointer

```
// standard input and output header file
#include<stdio.h>

// console input and output header file
#include<conio.h>

struct record
{
	char *name;

	int ac_no;

	char *ac_type;

	float balance;
};

// step 1 function declaration with structres parameter
struct recoard update(struct record *cust_ptr);

// main function
void main()
{
 struct record customers = {“sanjey”, 3333, “saving” , 33.33};

 clrscr();


 puts(“Before update”);

 printf(“Name : %s\n”, customers.name);

 printf(“AC NO : %d\n”, customers.ac_no);

 printf(“Account Type : %s\n”, customers.ac_type);

 printf(“Balance : %.2f\n”, customers.balance);

 // step 3 function calling with structures arguments
 update(&customer);

 puts(“After update”);

 printf(“Name : %s\n”, customers.name);

 printf(“AC NO : %d\n”, customers.ac_no);

 printf(“Account Type : %s\n”, customers.ac_type);

 printf(“Balance : %.2f\n”, customers.balance);

 getch();

}

// step 2 function definition with structres parameter
struct recoard update(struct record *cust_ptr)
{
	cust_ptr->name = “jones”;

	cust_ptr->ac_no = 9999;

	cust_ptr->ac_type = “current”;

	cust_ptr->balance = 100.0;

	return cust;
}
```