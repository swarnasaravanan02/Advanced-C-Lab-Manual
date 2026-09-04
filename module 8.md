EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
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
 
Program:
```
#include <stdio.h>

int main() {
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    return 0;
}
```




Output:


<img width="644" height="292" alt="image" src="https://github.com/user-attachments/assets/4c60985a-6474-4a36-be7d-098b7bf1aaae" />







Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```
#include <stdio.h>

int main() {
    char a[50];
    int h = 0, c, i;
    
    printf("Enter a string of digits: ");
    scanf("%s", a);
    
    while(h < 10) {
        c = 0;
        for(i = 0; a[i] != '\0'; i++) {
            if(a[i] - '0' == h)
                c++;
        }
        printf("%d ", c);
        h++;
    }
    
    return 0;
}
```



Output:


<img width="637" height="231" alt="image" src="https://github.com/user-attachments/assets/72d2e3cb-37a8-43fb-88af-42ada9bc9b50" />







Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
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
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void swap(char *x, char *y) {
    char temp[100];
    strcpy(temp, x);
    strcpy(x, y);
    strcpy(y, temp);
}

void sort(char **s, int n) {
    int i, j;
    for (i = 0; i < n - 1; i++) {
        for (j = i + 1; j < n; j++) {
            if (strcmp(s[i], s[j]) > 0) {
                swap(s[i], s[j]);
            }
        }
    }
}

void permute(char **s, int l, int r) {
    int i;
    if (l == r) {
        for (i = 0; i <= r; i++) {
            printf("%s ", s[i]);
        }
        printf("\n");
    } else {
        for (i = l; i <= r; i++) {
            swap(s[l], s[i]);
            permute(s, l + 1, r);
            swap(s[l], s[i]);
        }
    }
}

int main() {
    int n, i;
    char **s;

    printf("Enter number of strings: ");
    scanf("%d", &n);

    s = (char **)malloc(n * sizeof(char *));
    for (i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char));
    }

    printf("Enter the strings:\n");
    for (i = 0; i < n; i++) {
        scanf("%s", s[i]);
    }

    sort(s, n);
    permute(s, 0, n - 1);

    for (i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);

    return 0;
}
```




Output:



<img width="590" height="466" alt="image" src="https://github.com/user-attachments/assets/6af36db9-7f38-497a-a9b4-509b359c88a2" />







Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include <stdio.h>

int main() {
    int n, i, j, min, len;
    
    printf("Enter the value of n: ");
    scanf("%d", &n);
    
    len = n * 2 - 1;
    
    for(i = 0; i < len; i++) {
        for(j = 0; j < len; j++) {
            min = i < j ? i : j;
            min = min < len - i ? min : len - i - 1;
            min = min < len - j - 1 ? min : len - j - 1;
            printf("%d ", n - min);
        }
        printf("\n");
    }
    
    return 0;
}

```



Output:


<img width="564" height="343" alt="image" src="https://github.com/user-attachments/assets/cce4545b-0f6f-45c9-bd27-5661863a7377" />







Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

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

Program:
```
#include <stdio.h>

int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result;
    result = square();
    printf("Square of the number = %d\n", result);
    return 0;
}
```




Output:



<img width="587" height="278" alt="image" src="https://github.com/user-attachments/assets/42bca293-28aa-46dd-ba04-ad28ee66c1a6" />







Result:
Thus, the program is verified successfully



























