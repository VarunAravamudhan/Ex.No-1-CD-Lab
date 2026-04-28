<img width="939" height="413" alt="image" src="https://github.com/user-attachments/assets/2229af3d-5943-400b-a62d-6d878eca5420" /># Ex. No : 1

# IMPLEMENTATION OF SYMBOL TABLE

# Register Number : 212224240178

# Date : 28.04.2026

# AIM:

To write a C program to implement a symbol table.

# ALGORITHM:

1. Start the program.
2. Get the input from the user with the terminating symbol ‘$’.
3. Allocate memory for the variable by dynamic memory allocation function.
4. If the next character of the symbol is an operator then only the memory is allocated.
5. While reading, the input symbol is inserted into symbol table along with its memory address.
6. The steps are repeated till ‘$’ is reached.
7. To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8. Stop the program.

# PROGRAM:

```c
#include <stdio.h>
#include <ctype.h>
#include <string.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0, k;
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0';
    n = i - 1;

    printf("\nGiven Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\tType\t\tAddress\n");

    for (j = 0; j <= n; j++) {
        c = b[j];
        if (isalpha(c)) {
            int alreadyExists = 0;
            for (k = 0; k < x; k++) {
                if (d[k] == c) {
                    alreadyExists = 1;
                    break;
                }
            }

            if (!alreadyExists) {
                d[x] = c;
                printf("%c\tidentifier\t%p\n", c, (void*)&d[x]);
                x++;
            }
        }
    }

    // Clear buffer
    while ((c = getchar()) != '\n' && c != EOF);

    printf("\nEnter the symbol to search: ");
    srch = getchar();

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol %c Found @ address %p\n", srch, (void*)&d[i]); // ✅ FIX
            flag = 1;
            break;
        }
    }

    if (flag == 0)
        printf("Symbol Not Found\n");

    return 0;
}
```

# OUTPUT:

<img width="883" height="417" alt="image" src="https://github.com/user-attachments/assets/51c3aee6-beab-46f8-8a2c-b850dc39a9c4" />

<img width="939" height="413" alt="image" src="https://github.com/user-attachments/assets/3f5f3230-2993-4431-8281-d64c0005c6d4" />




# RESULT:

The program to implement a symbol table is executed and the output is verified.
