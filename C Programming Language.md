
 \#include <ctype.h>
 for atoi function - askii to integer

ex:
char \*ch = "1234";
int n  = atoi(ch);

putChar(int val): A function that writes a single byte to the standard output (console)

scanf(" %999\[^/n]%n", name, &nameLength); - Makes sure that the input does not go over 999
printf("Please provide your birthdate \[mm/dd/yyyy]: ");
count = scanf("%d/%d/%d", &month, &day, &year); - gets month, day, and year


### Pointers:
Main purpose to pass a pointer into a function so you can alter a variable outside of the function
- Can make a "fruitless" function (void return) to alter a variable

### Malloc - way to create arrays on the fly
char \*str1 = (char \*)malloc(10 \* sizeOf(char));

strcpy(str1, "abc");   //array dynamically allocated, str1 is "abc"

printf("str1: %s\\n", str1); //
### Free - free the array every time you use malloc 

You can only change a string (char array) if it's created using malloc


### Struct - lets you organize heterogenous information
- Akin to a java class
### Can use typeDef to assign name to structure
eg: typedef struct rectangle Rectangle; //can now reference rectangles as Rectangle instead of struct rectangle


Can allocate struct dynamically:


### To get number of elements in array:

sizeof(myarray) / sizeof(\*myarray);


### Good practice
Write functions gradually - write a few lines, compile and see if it works, then keep going - because C doesn't have error messages, very difficult to find error (without good debugger skills)