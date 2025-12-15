# 13 Marks - ACP

---

# **Question 1** 
`2 -> 1/2`

**A company has two teams and wants to merge their performance scores and sort them in ascending order. Write a C program to merge and sort two arrays.**

---

## **AIM**

To write a C program to merge the elements of two arrays into a single array and sort the merged array in ascending order.

---

## **PROCEDURE**

1. Start the program.
2. Declare the required variables and arrays.
3. Read the size and elements of the first array.
4. Read the size and elements of the second array.
5. Merge both arrays into a third array.
6. Sort the merged array in ascending order.
7. Display the sorted array.
8. Stop the program.

---

## **ALGORITHM**

1. Include the required header file.
2. Declare integer arrays for storing elements.
3. Read the size of the first array.
4. Read elements of the first array.
5. Read the size of the second array.
6. Read elements of the second array.
7. Merge both arrays into a third array.
8. Apply bubble sort to sort the merged array.
9. Print the sorted merged array.
10. End the program.

---

## **PROGRAM**

```c
#include <stdio.h>   // Including required header file

int main()
{
    /* Declaration of arrays and variables */
    int a[50], b[50], c[100];
    int n1, n2, i, j, temp;

    /* Reading size and elements of first array */
    printf("Enter size of first array: ");
    scanf("%d", &n1);
    for(i = 0; i < n1; i++)
    {
        scanf("%d", &a[i]);
    }

    /* Reading size and elements of second array */
    printf("Enter size of second array: ");
    scanf("%d", &n2);
    for(i = 0; i < n2; i++)
    {
        scanf("%d", &b[i]);
    }

    /* Merging first array into third array */
    for(i = 0; i < n1; i++)
    {
        c[i] = a[i];
    }

    /* Merging second array into third array */
    for(i = 0; i < n2; i++)
    {
        c[n1 + i] = b[i];
    }

    /* Sorting the merged array using bubble sort */
    for(i = 0; i < n1 + n2; i++)
    {
        for(j = i + 1; j < n1 + n2; j++)
        {
            if(c[i] > c[j])
            {
                temp = c[i];
                c[i] = c[j];
                c[j] = temp;
            }
        }
    }

    /* Displaying the sorted merged array */
    printf("Merged and Sorted Array:\n");
    for(i = 0; i < n1 + n2; i++)
    {
        printf("%d ", c[i]);
    }

    return 0;
}
```

---

## **OUTPUT**

```
Enter size of first array: 3
1 4 6
Enter size of second array: 3
2 3 5
Merged and Sorted Array:
1 2 3 4 5 6
```

---

## **RESULT**

Thus, the C program to merge two arrays and sort them in ascending order was successfully executed.

---

# **Question 2** 
`4 -> 3/4`

**Given an array of integers and a positive integer k, develop a C program to find and print the number of pairs where i < j and arr[i] + arr[j] is evenly divisible by k using functions.**

---

## **AIM**

To write a C program using functions to find the number of pairs in an array such that the sum of each pair is evenly divisible by a given positive integer k.

---

## **PROCEDURE**

1. Start the program.
2. Declare the array and required variables.
3. Read the size of the array and its elements.
4. Read the value of k.
5. Call a function to count valid pairs.
6. Display the number of valid pairs.
7. Stop the program.

---

## **ALGORITHM**

1. Include the required header file.
2. Define a function to count divisible pairs.
3. Read the number of elements in the array.
4. Read array elements.
5. Read the value of k.
6. Initialize a counter to zero.
7. Use two loops to generate pairs such that i < j.
8. Check if the sum of each pair is divisible by k.
9. Increment the counter if the condition is satisfied.
10. Return the count.
11. Display the result.
12. End the program.

---

## **PROGRAM**

```c
#include <stdio.h>   // Including required header file

/* Function to count pairs whose sum is divisible by k */
int countPairs(int arr[], int n, int k)
{
    int i, j, count = 0;

    /* Checking all possible pairs */
    for(i = 0; i < n; i++)
    {
        for(j = i + 1; j < n; j++)
        {
            if((arr[i] + arr[j]) % k == 0)
            {
                count++;
            }
        }
    }
    return count;
}

int main()
{
    /* Declaration of variables */
    int arr[50], n, k, result, i;

    /* Reading number of elements */
    printf("Enter number of elements: ");
    scanf("%d", &n);

    /* Reading array elements */
    for(i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    /* Reading the value of k */
    printf("Enter value of k: ");
    scanf("%d", &k);

    /* Function call */
    result = countPairs(arr, n, k);

    /* Displaying the result */
    printf("Number of valid pairs = %d", result);

    return 0;
}
```

---

## **OUTPUT**

```
Enter number of elements: 5
1 2 3 4 5
Enter value of k: 3
Number of valid pairs = 4
```

---

## **RESULT**

Thus, the C program to find the number of pairs whose sum is evenly divisible by a given value k using functions was successfully executed.


---

# **Question 3** 
`6 -> 5/6`

**A bank wants to implement a secure PIN swapping mechanism between two accounts. Write a C function to swap two integers using pointers.**

---

## **AIM**

To write a C program using pointers to swap two integer values by passing their addresses to a function.

---

## **PROCEDURE**

1. Start the program.
2. Declare two integer variables.
3. Read the values from the user.
4. Call a swap function by passing addresses of the variables.
5. Swap the values using pointers.
6. Display the swapped values.
7. Stop the program.

---

## **ALGORITHM**

1. Include the required header file.
2. Declare a function swap() that takes two integer pointers.
3. Inside the function, use a temporary variable to swap values.
4. In the main function, read two integers.
5. Call the swap function with addresses of the variables.
6. Print the swapped values.
7. End the program.

---

## **PROGRAM (VERY EASY & READABLE)**

```c
#include <stdio.h>   // Header file for input and output functions

/* Function to swap two integers using pointers */
void swap(int *a, int *b)
{
    int temp;          // Temporary variable for swapping

    temp = *a;         // Store value of a in temp
    *a = *b;           // Assign value of b to a
    *b = temp;         // Assign value of temp to b
}

int main()
{
    int x, y;          // Variable declaration

    /* Reading input values */
    printf("Enter first number: ");
    scanf("%d", &x);

    printf("Enter second number: ");
    scanf("%d", &y);

    /* Calling swap function */
    swap(&x, &y);

    /* Displaying swapped values */
    printf("After swapping:\n");
    printf("First number = %d\n", x);
    printf("Second number = %d\n", y);

    return 0;          // End of program
}
```

---

## **OUTPUT**

```
Enter first number: 10
Enter second number: 20
After swapping:
First number = 20
Second number = 10
```

---

## **RESULT**

Thus, the C program to swap two integers using pointers was successfully executed.

---

# **Question 4** 
`8 -> 7/8`

**Write a C function that takes a singly linked list containing integer data as input. Implement a C program to check whether a singly linked list is sorted in non-decreasing order.**

---

## **AIM**

To write a C program to check whether the elements of a singly linked list are sorted in non-decreasing order.

---

## **PROCEDURE**

1. Start the program.
2. Create a singly linked list.
3. Insert elements into the linked list.
4. Traverse the linked list and compare adjacent elements.
5. Check whether the list is sorted.
6. Display the result.
7. Stop the program.

---

## **ALGORITHM**

1. Include the required header files.
2. Define a structure for the singly linked list node.
3. Create a function to insert nodes at the end of the list.
4. Create a function to check if the linked list is sorted.
5. Traverse the list and compare current node data with next node data.
6. If any element is greater than the next element, the list is not sorted.
7. If traversal completes, the list is sorted.
8. Display the result.
9. End the program.

---

## **PROGRAM (VERY EASY & READABLE)**

```c
#include <stdio.h>
#include <stdlib.h>   // Header file for dynamic memory allocation

/* Definition of node structure */
struct Node
{
    int data;
    struct Node *next;
};

/* Function to insert a node at the end */
struct Node* insertEnd(struct Node *head, int value)
{
    struct Node *newNode, *temp;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if(head == NULL)
    {
        return newNode;
    }

    temp = head;
    while(temp->next != NULL)
    {
        temp = temp->next;
    }
    temp->next = newNode;

    return head;
}

/* Function to check if the list is sorted */
int isSorted(struct Node *head)
{
    struct Node *temp = head;

    while(temp != NULL && temp->next != NULL)
    {
        if(temp->data > temp->next->data)
        {
            return 0;   // Not sorted
        }
        temp = temp->next;
    }
    return 1;           // Sorted
}

int main()
{
    struct Node *head = NULL;
    int n, value, i;

    /* Reading number of nodes */
    printf("Enter number of elements: ");
    scanf("%d", &n);

    /* Inserting elements into linked list */
    for(i = 0; i < n; i++)
    {
        scanf("%d", &value);
        head = insertEnd(head, value);
    }

    /* Checking if the linked list is sorted */
    if(isSorted(head))
    {
        printf("The linked list is sorted in non-decreasing order.");
    }
    else
    {
        printf("The linked list is NOT sorted.");
    }

    return 0;
}
```

---

## **OUTPUT**

```
Enter number of elements: 5
1 2 2 4 5
The linked list is sorted in non-decreasing order.
```

---

## **RESULT**

Thus, the C program to check whether a singly linked list is sorted in non-decreasing order was successfully executed.

---

# **Question 5** 
`9 -> 9/10`

**Write a C program that opens an existing text file "source.txt" in read mode and a new file "destination.txt" in write mode. Read the contents of "source.txt" character by character using getc() and write them to "destination.txt" using putc(). Ensure the program properly closes both files after copying.**

---

## **AIM**

To write a C program to copy the contents of one file to another file using character-by-character file operations.

---

## **PROCEDURE**

1. Start the program.
2. Open the source file in read mode.
3. Open the destination file in write mode.
4. Read characters from the source file using getc().
5. Write characters to the destination file using putc().
6. Close both files.
7. Stop the program.

---

## **ALGORITHM**

1. Include the required header file.
2. Declare file pointers for source and destination files.
3. Open the source file in read mode.
4. Open the destination file in write mode.
5. Read one character at a time from the source file.
6. Write the read character into the destination file.
7. Repeat until end of file is reached.
8. Close both files.
9. End the program.

---

## **PROGRAM (VERY SIMPLE & READABLE)**

```c
#include <stdio.h>   // Header file for file operations

int main()
{
    FILE *sourceFile, *destinationFile;
    char ch;

    /* Opening source file in read mode */
    sourceFile = fopen("source.txt", "r");

    /* Opening destination file in write mode */
    destinationFile = fopen("destination.txt", "w");

    /* Copying contents character by character */
    while((ch = getc(sourceFile)) != EOF)
    {
        putc(ch, destinationFile);
    }

    /* Closing both files */
    fclose(sourceFile);
    fclose(destinationFile);

    printf("File copied successfully.");

    return 0;
}
```

---

## **OUTPUT**

```
File copied successfully.
```

---

## **RESULT**

Thus, the C program to copy the contents of one file to another using getc() and putc() was successfully executed.

---

# **Question 6** 
`11 -> 11/12`

**University maintains a list of employee IDs but wants to remove duplicates. Write a C program to remove duplicate elements from an array.**

---

## **AIM**

To write a C program to remove duplicate elements from an integer array and display the array without duplicates.

---

## **PROCEDURE**

1. Start the program.
2. Declare an array and required variables.
3. Read the number of elements and array values.
4. Compare each element with the remaining elements.
5. Remove duplicate elements by shifting array elements.
6. Display the array after removing duplicates.
7. Stop the program.

---

## **ALGORITHM**

1. Include the required header file.
2. Declare an integer array and variables.
3. Read the size of the array.
4. Read array elements.
5. Use two loops to compare each element with others.
6. If a duplicate is found, shift elements to remove it.
7. Reduce the size of the array.
8. Repeat until all duplicates are removed.
9. Print the updated array.
10. End the program.

---

## **PROGRAM (EASY & EXAM-SAFE)**

```c
#include <stdio.h>   // Header file for input and output

int main()
{
    int arr[50];
    int n, i, j, k;

    /* Reading number of elements */
    printf("Enter number of elements: ");
    scanf("%d", &n);

    /* Reading array elements */
    for(i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    /* Removing duplicate elements */
    for(i = 0; i < n; i++)
    {
        for(j = i + 1; j < n; j++)
        {
            if(arr[i] == arr[j])
            {
                /* Shift elements to the left */
                for(k = j; k < n - 1; k++)
                {
                    arr[k] = arr[k + 1];
                }
                n--;      // Reduce array size
                j--;      // Adjust index after deletion
            }
        }
    }

    /* Displaying array after removing duplicates */
    printf("Array after removing duplicates:\n");
    for(i = 0; i < n; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

---

## **OUTPUT**

```
Enter number of elements: 6
10 20 10 30 20 40
Array after removing duplicates:
10 20 30 40
```

---

## **RESULT**

Thus, the C program to remove duplicate elements from an array was successfully executed.

---

# **Question 7** 
`13 -> 13/14`

**Implement a C program for university plagiarism detection system wants to check if two student submissions are anagrams (contain the same letters) using functions.**

---

## **AIM**

To write a C program using functions to check whether two given strings are anagrams of each other.

---

## **PROCEDURE**

1. Start the program.
2. Read two strings from the user.
3. Count the frequency of each character in both strings.
4. Compare the character frequencies.
5. Display whether the strings are anagrams or not.
6. Stop the program.

---

## **ALGORITHM**

1. Include the required header files.
2. Define a function to check anagrams.
3. Read the first string.
4. Read the second string.
5. Initialize two frequency arrays for characters.
6. Count occurrences of each character in both strings.
7. Compare the frequency arrays.
8. If all frequencies match, strings are anagrams.
9. Display the result.
10. End the program.

---

## **PROGRAM (VERY EASY & READABLE)**

```c
#include <stdio.h>
#include <string.h>   // Header file for string functions

/* Function to check whether two strings are anagrams */
int isAnagram(char str1[], char str2[])
{
    int count1[256] = {0};
    int count2[256] = {0};
    int i;

    /* If lengths are not equal, not anagrams */
    if(strlen(str1) != strlen(str2))
    {
        return 0;
    }

    /* Counting frequency of characters in first string */
    for(i = 0; str1[i] != '\0'; i++)
    {
        count1[str1[i]]++;
    }

    /* Counting frequency of characters in second string */
    for(i = 0; str2[i] != '\0'; i++)
    {
        count2[str2[i]]++;
    }

    /* Comparing both frequency arrays */
    for(i = 0; i < 256; i++)
    {
        if(count1[i] != count2[i])
        {
            return 0;
        }
    }

    return 1;   // Strings are anagrams
}

int main()
{
    char str1[50], str2[50];

    /* Reading input strings */
    printf("Enter first string: ");
    scanf("%s", str1);

    printf("Enter second string: ");
    scanf("%s", str2);

    /* Checking anagram condition */
    if(isAnagram(str1, str2))
    {
        printf("The strings are anagrams.");
    }
    else
    {
        printf("The strings are NOT anagrams.");
    }

    return 0;
}
```

---

## **OUTPUT**

```
Enter first string: listen
Enter second string: silent
The strings are anagrams.
```

---

## **RESULT**

Thus, the C program to check whether two strings are anagrams using functions was successfully executed.

---
Good. **This one is a SCORING question** if written neatly.
We keep it **slow, clean, readable, examiner-friendly**.

---

# **Question 8** 
`15 -> 15/16`

**Write a C program that demonstrates the use of a pointer to an array of strings. The program should:**

i) Define an array of strings (list of names or words).
ii) Use a pointer to iterate through the array and print each string.
iii) Modify one of the strings using pointer dereferencing.

---

## **AIM**

To write a C program to demonstrate the use of a pointer to an array of strings, including accessing and modifying strings using pointer dereferencing.

---

## **PROCEDURE**

1. Start the program.
2. Declare an array of strings.
3. Declare a pointer to point to the array of strings.
4. Use the pointer to display all strings.
5. Modify one string using pointer dereferencing.
6. Display the modified array of strings.
7. Stop the program.

---

## **ALGORITHM**

1. Include the required header files.
2. Declare and initialize an array of strings.
3. Declare a pointer to the array of strings.
4. Use a loop to print each string using the pointer.
5. Modify a string using pointer dereferencing.
6. Display the updated strings.
7. End the program.

---

## **PROGRAM (VERY SIMPLE & CLEAR)**

```c
#include <stdio.h>
#include <string.h>   // Header file for string operations

int main()
{
    /* Declaration of array of strings */
    char names[3][20] = {"Alice", "Bob", "Charlie"};

    /* Pointer to array of strings */
    char (*ptr)[20];

    int i;

    /* Assigning base address of array to pointer */
    ptr = names;

    /* Displaying strings using pointer */
    printf("Original strings:\n");
    for(i = 0; i < 3; i++)
    {
        printf("%s\n", *(ptr + i));
    }

    /* Modifying second string using pointer dereferencing */
    strcpy(*(ptr + 1), "David");

    /* Displaying modified strings */
    printf("\nAfter modifying one string:\n");
    for(i = 0; i < 3; i++)
    {
        printf("%s\n", *(ptr + i));
    }

    return 0;
}
```

---

## **OUTPUT**

```
Original strings:
Alice
Bob
Charlie

After modifying one string:
Alice
David
Charlie
```

---

## **RESULT**

Thus, the C program to demonstrate the use of a pointer to an array of strings, including modification using pointer dereferencing, was successfully executed.

---

# **Question 9** 
`18 -> 17/18`

**A library tracks borrowed books using a singly linked list. Each node contains a book title and borrower’s name. Write a C program to add a new borrowed book, return a book, and display the current borrowed list.**

---

## **AIM**

To write a C program using a singly linked list to manage borrowed books by adding a book, returning a book, and displaying the borrowed book list.

---

## **PROCEDURE**

1. Start the program.
2. Create a singly linked list structure.
3. Add new borrowed books to the list.
4. Remove a returned book from the list.
5. Display the current borrowed book list.
6. Stop the program.

---

## **ALGORITHM**

1. Include the required header files.
2. Define a structure for a linked list node containing book title and borrower name.
3. Create a function to add a new borrowed book.
4. Create a function to return a book (delete node).
5. Create a function to display borrowed books.
6. Call the functions from the main function.
7. End the program.

---

## **PROGRAM (SIMPLE & READABLE)**

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

/* Definition of singly linked list node */
struct Node
{
    char book[50];
    char borrower[50];
    struct Node *next;
};

/* Function to add a borrowed book */
struct Node* addBook(struct Node *head, char book[], char borrower[])
{
    struct Node *newNode, *temp;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    strcpy(newNode->book, book);
    strcpy(newNode->borrower, borrower);
    newNode->next = NULL;

    if(head == NULL)
    {
        return newNode;
    }

    temp = head;
    while(temp->next != NULL)
    {
        temp = temp->next;
    }
    temp->next = newNode;

    return head;
}

/* Function to return a book */
struct Node* returnBook(struct Node *head, char book[])
{
    struct Node *temp = head, *prev = NULL;

    if(head == NULL)
    {
        return head;
    }

    if(strcmp(head->book, book) == 0)
    {
        head = head->next;
        free(temp);
        return head;
    }

    while(temp != NULL && strcmp(temp->book, book) != 0)
    {
        prev = temp;
        temp = temp->next;
    }

    if(temp != NULL)
    {
        prev->next = temp->next;
        free(temp);
    }

    return head;
}

/* Function to display borrowed books */
void display(struct Node *head)
{
    struct Node *temp = head;

    if(head == NULL)
    {
        printf("No borrowed books.\n");
        return;
    }

    printf("Borrowed Books List:\n");
    while(temp != NULL)
    {
        printf("Book: %s, Borrower: %s\n", temp->book, temp->borrower);
        temp = temp->next;
    }
}

int main()
{
    struct Node *head = NULL;

    /* Adding borrowed books */
    head = addBook(head, "C Programming", "Arun");
    head = addBook(head, "Data Structures", "Ravi");

    /* Displaying borrowed books */
    display(head);

    /* Returning a book */
    head = returnBook(head, "C Programming");

    /* Display after returning */
    display(head);

    return 0;
}
```

---

## **OUTPUT**

```
Borrowed Books List:
Book: C Programming, Borrower: Arun
Book: Data Structures, Borrower: Ravi

Borrowed Books List:
Book: Data Structures, Borrower: Ravi
```

---

## **RESULT**

Thus, the C program to manage borrowed books using a singly linked list was successfully executed.

---

# **Question 10**
`20 -> 19/20`

**Write a C program that attempts to open a file for reading. If the file does not exist or an error occurs while opening it, the program should:
Use the global errno variable to capture the error code.
Use the strerror(errno) function to display a meaningful error message.**

---

## **AIM**

To write a C program that handles file opening errors using the global variable `errno` and displays a meaningful error message using the `strerror()` function.

---

## **PROCEDURE**

1. Start the program.
2. Attempt to open a file in read mode.
3. Check whether the file is opened successfully.
4. If an error occurs, capture the error using `errno`.
5. Display the corresponding error message using `strerror()`.
6. Close the file if opened.
7. Stop the program.

---

## **ALGORITHM**

1. Include the required header files.
2. Declare a file pointer.
3. Attempt to open a file in read mode.
4. Check if the file pointer is NULL.
5. If NULL, print the error message using `errno` and `strerror()`.
6. If file opens successfully, display a success message.
7. Close the file.
8. End the program.

---

## **PROGRAM (VERY SIMPLE & THEORY-FRIENDLY)**

```c
#include <stdio.h>     // Header file for file operations
#include <errno.h>     // Header file for errno
#include <string.h>    // Header file for strerror()

int main()
{
    FILE *fp;

    /* Attempting to open a file in read mode */
    fp = fopen("data.txt", "r");

    /* Checking whether file opened successfully */
    if(fp == NULL)
    {
        printf("Error opening file.\n");
        printf("Error code: %d\n", errno);
        printf("Error message: %s\n", strerror(errno));
    }
    else
    {
        printf("File opened successfully.");
        fclose(fp);   // Closing the file
    }

    return 0;
}
```

---

## **OUTPUT**

```
Error opening file.
Error code: 2
Error message: No such file or directory
```

---

## **RESULT**

Thus, the C program to handle file opening errors using `errno` and `strerror()` was successfully executed.

---

# **Question 11**
`21 -> 21/22`

**Create a C program to extract the upper triangular part and lower triangular part of a 4x4 matrix.**

---

## **AIM**

To write a C program to extract and display the upper triangular and lower triangular matrices from a given 4×4 matrix.

---

## **PROCEDURE**

1. Start the program.
2. Declare a 4×4 matrix.
3. Read matrix elements from the user.
4. Display the upper triangular matrix.
5. Display the lower triangular matrix.
6. Stop the program.

---

## **ALGORITHM**

1. Include the required header file.
2. Declare a 4×4 integer matrix.
3. Read elements of the matrix using nested loops.
4. For upper triangular matrix:

   * Print elements where column index ≥ row index.
   * Print 0 for remaining positions.
5. For lower triangular matrix:

   * Print elements where row index ≥ column index.
   * Print 0 for remaining positions.
6. End the program.

---

## **PROGRAM (VERY SIMPLE & EXAM-FRIENDLY)**

```c
#include <stdio.h>   // Header file for input and output

int main()
{
    int matrix[4][4];
    int i, j;

    /* Reading elements of the matrix */
    printf("Enter elements of 4x4 matrix:\n");
    for(i = 0; i < 4; i++)
    {
        for(j = 0; j < 4; j++)
        {
            scanf("%d", &matrix[i][j]);
        }
    }

    /* Displaying Upper Triangular Matrix */
    printf("\nUpper Triangular Matrix:\n");
    for(i = 0; i < 4; i++)
    {
        for(j = 0; j < 4; j++)
        {
            if(j >= i)
                printf("%d ", matrix[i][j]);
            else
                printf("0 ");
        }
        printf("\n");
    }

    /* Displaying Lower Triangular Matrix */
    printf("\nLower Triangular Matrix:\n");
    for(i = 0; i < 4; i++)
    {
        for(j = 0; j < 4; j++)
        {
            if(i >= j)
                printf("%d ", matrix[i][j]);
            else
                printf("0 ");
        }
        printf("\n");
    }

    return 0;
}
```

---

## **OUTPUT**

```
Enter elements of 4x4 matrix:
1 2 3 4
5 6 7 8
9 1 2 3
4 5 6 7

Upper Triangular Matrix:
1 2 3 4
0 6 7 8
0 0 2 3
0 0 0 7

Lower Triangular Matrix:
1 0 0 0
5 6 0 0
9 1 2 0
4 5 6 7
```

---

## **RESULT**

Thus, the C program to extract the upper and lower triangular parts of a 4×4 matrix was successfully executed.

---

Perfect. **Question 24 is clean recursion + easy explanation = solid marks.**
No fancy logic. Just symmetry check.

---

# **Question 12**
`24 -> 23/24`

**A smart home device processes an integer array representing sensor readings. Write a C recursive function to check if the array is symmetric (i.e., first element = last element, etc.).**

---

## **AIM**

To write a C program using a recursive function to check whether an integer array is symmetric.

---

## **PROCEDURE**

1. Start the program.
2. Read the number of elements in the array.
3. Read the array elements.
4. Call a recursive function to check symmetry.
5. Display whether the array is symmetric or not.
6. Stop the program.

---

## **ALGORITHM**

1. Include the required header file.
2. Declare a recursive function `isSymmetric()`.
3. Pass the array, start index, and end index to the function.
4. If start index is greater than or equal to end index, return true.
5. If array[start] is not equal to array[end], return false.
6. Call the function recursively by increasing start and decreasing end.
7. Display the result.
8. End the program.

---

## **PROGRAM (VERY SIMPLE & READABLE)**

```c
#include <stdio.h>   // Header file for input and output

/* Recursive function to check symmetry */
int isSymmetric(int arr[], int start, int end)
{
    /* Base condition */
    if(start >= end)
    {
        return 1;   // Array is symmetric
    }

    /* If elements are not equal */
    if(arr[start] != arr[end])
    {
        return 0;   // Not symmetric
    }

    /* Recursive call */
    return isSymmetric(arr, start + 1, end - 1);
}

int main()
{
    int arr[50];
    int n, i;

    /* Reading number of elements */
    printf("Enter number of elements: ");
    scanf("%d", &n);

    /* Reading array elements */
    for(i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    /* Checking symmetry using recursion */
    if(isSymmetric(arr, 0, n - 1))
    {
        printf("The array is symmetric.");
    }
    else
    {
        printf("The array is NOT symmetric.");
    }

    return 0;
}
```

---

## **OUTPUT**

```
Enter number of elements: 5
1 2 3 2 1
The array is symmetric.
```

---

## **RESULT**

Thus, the C program to check whether an array is symmetric using a recursive function was successfully executed.

---

# **Question 13**
`26 -> 25/26`

**An online exam portal records the marks of N students.
Write a C program to:**

1. Allocate memory dynamically using `calloc()`.
2. Accept marks from the user.
3. Calculate and display:

   * The average score
   * The highest and lowest marks
4. If the average score < 40, display **"Re-evaluation required"**.

---

## **AIM**

To write a C program that dynamically allocates memory using `calloc()` to store student marks and calculates the average, highest, and lowest marks.

---

## **PROCEDURE**

1. Start the program.
2. Read the number of students.
3. Allocate memory dynamically using `calloc()`.
4. Read marks of students.
5. Calculate total, average, highest, and lowest marks.
6. Display the results.
7. Check if average is less than 40 and display the message.
8. Free allocated memory.
9. Stop the program.

---

## **ALGORITHM**

1. Include the required header files.
2. Read the number of students.
3. Allocate memory using `calloc()`.
4. Read marks into the allocated memory.
5. Initialize highest and lowest with first element.
6. Find total, highest, and lowest marks using a loop.
7. Calculate the average.
8. Display average, highest, and lowest marks.
9. If average < 40, print re-evaluation message.
10. Free the allocated memory.
11. End the program.

---

## **PROGRAM (VERY SIMPLE & THEORY-FRIENDLY)**

```c
#include <stdio.h>
#include <stdlib.h>   // Header file for calloc()

int main()
{
    int *marks;
    int n, i;
    int total = 0;
    int highest, lowest;
    float average;

    /* Reading number of students */
    printf("Enter number of students: ");
    scanf("%d", &n);

    /* Allocating memory dynamically using calloc */
    marks = (int *)calloc(n, sizeof(int));

    /* Reading marks */
    for(i = 0; i < n; i++)
    {
        scanf("%d", &marks[i]);
    }

    /* Initializing highest and lowest */
    highest = marks[0];
    lowest = marks[0];

    /* Calculating total, highest and lowest */
    for(i = 0; i < n; i++)
    {
        total = total + marks[i];

        if(marks[i] > highest)
            highest = marks[i];

        if(marks[i] < lowest)
            lowest = marks[i];
    }

    /* Calculating average */
    average = (float)total / n;

    /* Displaying results */
    printf("Average score = %.2f\n", average);
    printf("Highest mark = %d\n", highest);
    printf("Lowest mark = %d\n", lowest);

    /* Checking average condition */
    if(average < 40)
    {
        printf("Re-evaluation required");
    }

    /* Freeing allocated memory */
    free(marks);

    return 0;
}
```

---

## **OUTPUT**

```
Enter number of students: 5
45 30 60 50 35
Average score = 44.00
Highest mark = 60
Lowest mark = 30
```

---

## **RESULT**

Thus, the C program to store student marks using `calloc()` and compute the average, highest, and lowest marks was successfully executed.

---

Good. **Next = Question 28.**
Clean logic, no tricks. Very safe for theory exams.

---

# **Question 14**
`28 -> 27/28`

**Given the head pointers of two single linked lists, develop a C code to determine if the linked lists are equal and having the same elements in the same order.**

---

## **AIM**

To write a C program to check whether two singly linked lists are equal and contain the same elements in the same order.

---

## **PROCEDURE**

1. Start the program.
2. Create two singly linked lists.
3. Insert elements into both linked lists.
4. Compare the elements of both lists node by node.
5. Display whether the linked lists are equal or not.
6. Stop the program.

---

## **ALGORITHM**

1. Include the required header files.
2. Define a structure for singly linked list node.
3. Create a function to insert nodes at the end of the list.
4. Create a function to compare two linked lists.
5. Traverse both lists simultaneously.
6. If data in any node differs, lists are not equal.
7. If both lists reach the end together, lists are equal.
8. Display the result.
9. End the program.

---

## **PROGRAM (VERY SIMPLE & READABLE)**

```c
#include <stdio.h>
#include <stdlib.h>

/* Definition of singly linked list node */
struct Node
{
    int data;
    struct Node *next;
};

/* Function to insert node at the end */
struct Node* insertEnd(struct Node *head, int value)
{
    struct Node *newNode, *temp;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if(head == NULL)
    {
        return newNode;
    }

    temp = head;
    while(temp->next != NULL)
    {
        temp = temp->next;
    }
    temp->next = newNode;

    return head;
}

/* Function to compare two linked lists */
int areEqual(struct Node *head1, struct Node *head2)
{
    while(head1 != NULL && head2 != NULL)
    {
        if(head1->data != head2->data)
        {
            return 0;   // Not equal
        }
        head1 = head1->next;
        head2 = head2->next;
    }

    /* If both lists end at the same time */
    if(head1 == NULL && head2 == NULL)
    {
        return 1;   // Equal
    }

    return 0;
}

int main()
{
    struct Node *head1 = NULL;
    struct Node *head2 = NULL;

    /* Creating first linked list */
    head1 = insertEnd(head1, 10);
    head1 = insertEnd(head1, 20);
    head1 = insertEnd(head1, 30);

    /* Creating second linked list */
    head2 = insertEnd(head2, 10);
    head2 = insertEnd(head2, 20);
    head2 = insertEnd(head2, 30);

    /* Comparing the two linked lists */
    if(areEqual(head1, head2))
    {
        printf("Both linked lists are equal.");
    }
    else
    {
        printf("Linked lists are not equal.");
    }

    return 0;
}
```

---

## **OUTPUT**

```
Both linked lists are equal.
```

---

## **RESULT**

Thus, the C program to determine whether two singly linked lists are equal and contain the same elements in the same order was successfully executed.

---

Perfect. **Final one. Close strong.**
This is **easy logic + file handling = clean marks**.

---

# **Question 15**
`30 -> 29/30`

**An online shopping site stores product ratings in a file. Write a C program to calculate the average rating for each product and store the result in a summary file.**

---

## **AIM**

To write a C program to read product ratings from a file, calculate the average rating for each product, and store the results in a summary file.

---

## **PROCEDURE**

1. Start the program.
2. Open the input file containing product ratings.
3. Open the summary file in write mode.
4. Read product name and ratings from the input file.
5. Calculate the average rating for each product.
6. Write the product name and average rating into the summary file.
7. Close both files.
8. Stop the program.

---

## **ALGORITHM**

1. Include the required header file.
2. Declare file pointers for input and summary files.
3. Open the input file in read mode.
4. Open the summary file in write mode.
5. Read product name and number of ratings.
6. Read all ratings and calculate the sum.
7. Find the average rating.
8. Write the product name and average rating to the summary file.
9. Repeat until end of file.
10. Close both files.
11. End the program.

---

## **PROGRAM (VERY SIMPLE & THEORY-FRIENDLY)**

```c
#include <stdio.h>   // Header file for file operations

int main()
{
    FILE *inputFile, *summaryFile;
    char product[50];
    int ratingsCount, i;
    float rating, sum, average;

    /* Opening input file in read mode */
    inputFile = fopen("ratings.txt", "r");

    /* Opening summary file in write mode */
    summaryFile = fopen("summary.txt", "w");

    /* Reading product details and calculating average */
    while(fscanf(inputFile, "%s %d", product, &ratingsCount) != EOF)
    {
        sum = 0;

        for(i = 0; i < ratingsCount; i++)
        {
            fscanf(inputFile, "%f", &rating);
            sum = sum + rating;
        }

        average = sum / ratingsCount;

        /* Writing result to summary file */
        fprintf(summaryFile, "%s Average Rating = %.2f\n", product, average);
    }

    /* Closing files */
    fclose(inputFile);
    fclose(summaryFile);

    printf("Average ratings stored successfully.");

    return 0;
}
```

---

## **OUTPUT**

```
Average ratings stored successfully.
```

---

## **RESULT**

Thus, the C program to calculate the average rating for each product and store it in a summary file was successfully executed.

---








