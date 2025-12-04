# EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

# Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 18 years of age.

# Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 18
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
# Program:
```
#include<stdio.h>
struct eligible{
    int age;
    char name[50];
    
};
int main(){
    struct eligible e;
    
    scanf("%d",&e.age);
    scanf("%s",e.name);
    printf("Age:%d\n",e.age);
    printf("Name:%s",e.name);
    printf("vaccine:%d\n",e.age);
    if (e.age<=18)
    {
        printf("eligibility:no");
    }
    else{
        printf("eligibility:yes");
    }
    return 0;
}
```
# Output:
<img width="699" height="333" alt="image" src="https://github.com/user-attachments/assets/c209313b-e18c-4e12-93d8-49d3b2bcec9d" />

# Result:
Thus, the program is verified successfully. 



# EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
# Aim:
To write a C program for passing structure as function and returning a structure from a function

# Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
# Program:
```
#include <stdio.h>

struct Product {
    int id;
    char Product_name[20];
    float price;
    struct Date_Exp {
        int dd;
        int mm;
        int yyyy;
    } doj;
} e1;

int main() {
   
    scanf("%d", &e1.id);

    scanf(" %19s", e1.Product_name);  // Read string safely

    scanf("%f", &e1.price);

    
    scanf("%d %d %d", &e1.doj.dd, &e1.doj.mm, &e1.doj.yyyy);

    printf("product id : %d\n", e1.id);
    printf("product name : %s\n", e1.Product_name);
    printf("product name : %.2f\n", e1.price);
    printf("product date of expiry (dd/mm/yyyy) : %d/%d/%d\n", e1.doj.dd, e1.doj.mm, e1.doj.yyyy);

    return 0;
}
```
# Output:
<img width="1153" height="461" alt="image" src="https://github.com/user-attachments/assets/7f88b51a-9456-428d-862e-481e288553ae" />

# Result:
Thus, the program is verified successfully


 
# EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()
# Aim:
To write a C program to read a file name from user

# Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
# Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *file;

    file = fopen("Hospital.txt", "w");

    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }

    fprintf(file, "Hospital Name: City Hospital\n");
    fprintf(file, "Location: Main Street, Downtown\n");
    fprintf(file, "Total Beds: 200\n");
    fprintf(file, "Emergency Contact: 123-456-7890\n");

    fclose(file);
    
    printf("File Created Successfully\n");
    printf("File Opened\n");
    printf("File Closed");
    return 0;
}
```

# Output:
<img width="1149" height="225" alt="image" src="https://github.com/user-attachments/assets/2e6b292a-9775-4d1f-ba50-e80c132f2e49" />

# Result:
Thus, the program is verified successfully
 


# EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
# Aim:
To write a C program to read, a file and insert text in that file

# Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
# Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *file;
    char filename[100];
    char content[500];

    printf("Enter the filename: ");
    scanf("%99s", filename);
    getchar(); // Clear newline

    file = fopen(filename, "w");

    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }
    
    printf("Enter text to write into the file:\n");
    fgets(content, sizeof(content), stdin);

    fprintf(file, "%s", content);

    fclose(file);
    
    printf("File '%s' opened successfully.\n", filename);
    printf("Data added successfully.\n");
    
    return 0;
}

```
# Output:
<img width="1148" height="391" alt="image" src="https://github.com/user-attachments/assets/147d8a5f-77aa-40a1-b1ea-e9d14222f8a1" />

# Result:
Thus, the program is verified successfully



# Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE
# Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

# Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

# Program:
```
#include<stdio.h>
struct Student{
    int admission_no;  
    char student_name[20];
    char course_type[40];
    char course_name[100];
    int tution_fee;
    struct Date_of_admission
     {
        int dd;
         int mm;
          int yyyy;
          } doj;
    
} e1;
int main(){
    scanf("%d",&e1.admission_no);
    scanf("%s",e1.student_name);
    scanf("%s",e1.course_type);
    scanf("%s",e1.course_name);
    scanf("%d",&e1.tution_fee);
    scanf("%d",&e1.doj.dd);
    scanf("%d%d",&e1.doj.mm,&e1.doj.yyyy);
    printf("Admission Number : %d\n",e1.admission_no);
    printf("Student name : %s\n",e1.student_name);
    printf("Course Type : %s\n",e1.course_name);
    printf("Date of admission (dd/mm/yyyy) : %d/%d/%d\n",e1.doj.dd,e1.doj.mm,e1.doj.yyyy);
    printf("Course Name :%s\n",e1.course_type);
    printf("Tution Fee:%d",e1.tution_fee);
    
    return 0;
    
}
```
# Output:
<img width="1151" height="561" alt="image" src="https://github.com/user-attachments/assets/9e1d45c2-d991-47a9-be4c-3e7406dd8ea5" />

# Result:
Thus, the program is verified successfully
