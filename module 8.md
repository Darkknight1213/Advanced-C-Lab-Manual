# EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
# Aim:
To write a C program print the lowercase English word corresponding to the number
# Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
# Program:
```
#include <stdio.h>
int main()
{
    int a;
    scanf("%d",&a);
    switch(a)
    {
        case 71:
        printf("seventy one");
        break;
        case 72:
        printf("seventy two");
        break;
        case 73:
        printf("seventy three");
        break;
        case 74:
        printf("seventy four");
        break;
        case 75:
        printf("seventy five");
        break;
        case 76:
        printf("seventy six");
        break;
        case 77:
        printf("seventy seven");
        break;
        case 78:
        printf("seventy eight");
        break;
        case 79:
        printf("seventy nine");
        break;
        default:
        printf("Greater than 79");
    }
    return 0;
}
```
# Output:
<img width="387" height="127" alt="image" src="https://github.com/user-attachments/assets/8c8d75b5-4f00-471d-ae31-e9457af799fe" />

# Result:
Thus, the program is verified successfully

 
# EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
# Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
# Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
# Program:
```
#include <stdio.h>
#include <string.h>
int main()
{
    char s[1000];  
    int digit_count[10] = {0};
    scanf("%s",s);
    for (int i = 0; s[i] != '\0'; i++) 
    {
        if (s[i] >= '0' && s[i] <= '9') 
        { 
            digit_count[s[i] - '0']++;  
        }
    }
    for (int i = 0; i < 10; i++) 
    {
        printf("%d ", digit_count[i]);
    }
    
    return 0;
}
```

# Output:
<img width="834" height="229" alt="image" src="https://github.com/user-attachments/assets/6d9e44fe-1079-44dd-b250-9900c0a3d3d4" />

# Result:
Thus, the program is verified successfully


# EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
# Aim:
To write a C program to print all of its permutations in strict lexicographical order.

# Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)
3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
# Program:
```
#include <string.h>
int next_permutation(int n, char **s)
{
    for (int i = n - 1; i > 0; i--)
        if (strcmp(s[i], s[i - 1]) > 0)
        {
            int j = i + 1;
            for (; j < n; j++) if (strcmp(s[j], s[i - 1]) <= 0) break;
            char *t = s[i - 1];
            s[i - 1] = s[j - 1];
            s[j - 1] = t;
            for (; i < n - 1; i++, n--)
            {
                t = s[i];
                s[i] = s[n - 1];
                s[n - 1] = t;
            }
            return 1;
        }
    for (int i = 0; i < n - 1; i++, n--)
    {
        char *t = s[i];
        s[i] = s[n - 1];
        s[n - 1] = t;
    }
    return 0;
}
int main()
{
    char **s;
    int n;
    scanf("%d", &n);
   s = calloc(n, sizeof(char*));
   
    for (int i = 0; i < n; i++)
    {
        s[i] = calloc(n, sizeof(char) * 11);
        scanf("%s", s[i]);
    }
    do
    {
        for (int i = 0; i < n; i++)
            printf("%s%c", s[i], i == n - 1 ? '\n' : ' ');
    } while (next_permutation(n, s));
   
    for (int i = 0; i < n; i++)
    free(s[i]);
    free(s);
    return 0;
}
```
# Output:
<img width="834" height="395" alt="image" src="https://github.com/user-attachments/assets/cb0a4f1c-90b2-4917-a21c-53cbf3f7fe01" />

# Result:
Thus, the program is verified successfully
 
# EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
# Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
# Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
# Program:
```
# include<stdio.h>
void printpattern(int n){
    int size=2*n-1;
    int pattern[size][size];
    for(int i=0;i<n;i++){
        for(int j=i;j<size-i;j++){
            pattern[i][j]=n-i;
            pattern[j][i]=n-i;
            pattern[size-i-1][j]=n-i;
            pattern[j][size-i-1]=n-i;
        }
    }
    for(int i=0;i<size;i++){
        for(int j=0;j<size;j++){
            printf("%d ",pattern[i][j]);
        }
        printf("\n");
    }
        
}
int main(){
    int n;
    scanf("%d",&n);
    printpattern(n);
    return 0;
}
```
# Output:
<img width="814" height="594" alt="Screenshot 2025-11-28 135919" src="https://github.com/user-attachments/assets/64903791-c93e-45a4-99a8-c2ab5e906364" />

# Result:
Thus, the program is verified successfully

# EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE
# Aim:
To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

# Algorithm:
1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

# Program:
```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}
int main() {
    int result = square();
    printf("Square: %d\n", result);
    return 0;
}
```

# Output:
<img width="367" height="152" alt="image" src="https://github.com/user-attachments/assets/6fbfe6c8-29e2-4c24-83b2-b850ff831fc8" />

# Result:
Thus, the program is verified successfully
