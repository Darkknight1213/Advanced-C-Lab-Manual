# EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
# Aim:
To write a C program to create a function to find the greatest number

# Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
# Program:
```
#include<stdio.h>
struct number{
    int n1;
    int n2; 
    int n3;
}n;
int main(){
    scanf("%d%d%d",&n.n1,&n.n2,&n.n3);
    if (n.n1>n.n2 && n.n1>n.n3){
        printf("%d",n.n1);
    }
    else if(n.n2>n.n3){
        printf("%d",n.n2);
    }
    else{
        printf("%d",n.n3);
    }
    return 0;
}
```
# Output:
<img width="1146" height="261" alt="image" src="https://github.com/user-attachments/assets/5f35f739-d1ac-47ff-8d87-06291961a1f0" />

# Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
# EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
# Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

# Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
# Program:
```
#include <stdio.h>

int main() {
    int n, k, a = 0, o = 0, x = 0;
    scanf("%d %d", &n, &k);
    for (int i = 1; i < n; i++)
        for (int j = i + 1; j <= n; j++) {
            int and = i & j, or = i | j, xor = i ^ j;
            if (and < k && and > a) a = and;
            if (or < k && or > o) o = or;
            if (xor < k && xor > x) x = xor;
        }
    printf("%d\n%d\n%d\n", a, o, x);
}
```
# Output:
<img width="1149" height="402" alt="image" src="https://github.com/user-attachments/assets/11b30b3d-43fd-463e-9e5f-1739a1b98064" />

# Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
# EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
# Aim:
To write a C program to write the logic for the requests

# Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
# Program:
```
#include<stdio.h>
#include<stdlib.h>
int** total_number_of_pages;
int* total_number_of_books;
int main()
{
 int total_number_of_shelves;
    scanf("%d", &total_number_of_shelves);
    
    int total_number_of_queries;
    scanf("%d", &total_number_of_queries);
    
    total_number_of_books = (int *)malloc(sizeof(int)*total_number_of_shelves);
    total_number_of_pages = (int **)malloc(sizeof(int *)*total_number_of_shelves);
    for(int i = 0; i<total_number_of_shelves; i++){
        *(total_number_of_books + i) = 0;
    }
    while(total_number_of_queries--){
        int type_of_query;
        scanf("%d", &type_of_query);
        if(type_of_query == 1){
            int x, y;
            scanf("%d %d", &x, &y);
            int booksInShelf = *(total_number_of_books + x);
            *(total_number_of_pages + x) = (int*)realloc(*(total_number_of_pages+x),sizeof(int)*(booksInShelf+1));
            *(*(total_number_of_pages+x)+booksInShelf) = y;
            *(total_number_of_books + x) += 1;
        } else if (type_of_query == 2) {
            int x, y;
            scanf("%d %d", &x, &y);
            printf("%d\n", *(*(total_number_of_pages + x) + y));
        } else {
            int x;
            scanf("%d", &x);
            printf("%d\n", *(total_number_of_books + x));
        }
    }

    if (total_number_of_books) {
        free(total_number_of_books);
    }
    
    for (int i = 0; i < total_number_of_shelves; i++) {
        if (*(total_number_of_pages + i)) {
            free(*(total_number_of_pages + i));
        }
    }
    
    if (total_number_of_pages) {
        free(total_number_of_pages);
    }
    
    return 0;
}


    
```
# Output:
<img width="795" height="324" alt="image" src="https://github.com/user-attachments/assets/b0b2a32a-9342-4c09-b04d-78c53633fb18" />

# Result:
Thus, the program to write the logic for the requests is verified successfully.


 
# EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
# Aim:
To write a C program print the sum of the integers in the array.

# Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.

# Program:
```
#include<stdio.h>
int main(){
    int a,sum=0;
    scanf("%d",&a);
    int s[a];
    for(int i=0;i<a;i++){
        scanf("%d",&s[i]);
        sum+=s[i];
    }printf("%d",sum);
}
```
# Output:
<img width="795" height="264" alt="image" src="https://github.com/user-attachments/assets/cf62e7b2-1911-426c-bbaf-4a3e0880a6d6" />

# Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
# EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE
# Aim:
To write a C program that counts the number of words in a given sentence.

# Algorithm:
1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.

# Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[200];
    int i, count = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    for (i = 0; str[i] != '\0'; i++) {

        if ((str[i] != ' ' && str[i] != '\n') &&
            (i == 0 || str[i-1] == ' ')) {
            count++;
        }
    }

    printf("Number of words = %d\n", count);

    return 0;
}
```

# Output:
<img width="488" height="302" alt="image" src="https://github.com/user-attachments/assets/3ea4d967-6c18-497d-bcc8-dcf58bfc18fc" />

# Result:
Thus, the program that counts the number of words in a given sentence is verified 
successfully.
