do-while

#include <stdio.h>

void printDigitInWords(int digit) {
    switch (digit) {
        case 0: printf("Zero "); break;
        case 1: printf("One "); break;
        case 2: printf("Two "); break;
        case 3: printf("Three "); break;
        case 4: printf("Four "); break;
        case 5: printf("Five "); break;
        case 6: printf("Six "); break;
        case 7: printf("Seven "); break;
        case 8: printf("Eight "); break;
        case 9: printf("Nine "); break;
    }
}

int main() {
    int num, reversed = 0, digit;

    printf("Enter a number: ");
    scanf("%d", &num);

    // Reverse the number
    int temp = num;
    while (temp > 0) {
        reversed = reversed * 10 + temp % 10;
        temp /= 10;
    }

    // Print digits in words
    while (reversed > 0) {
        digit = reversed % 10;
        printDigitInWords(digit);
        reversed /= 10;
    }

    printf("\n");
    return 0;
}
-------------------------------------------------
#include <stdio.h>
#include <stdbool.h>

bool isPrime(int num) {
    if (num <= 1) return false;
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) return false;
    }
    return true;
}

int main() {
    int num, digitSum = 0, temp;

    printf("Enter a number: ");
    scanf("%d", &num);

    // Check if prime
    if (isPrime(num)) {
        printf("%d is a prime number.\n", num);
    } else {
        printf("%d is not a prime number.\n", num);
    }

    // Calculate sum of digits
    temp = num;
    while (temp > 0) {
        digitSum += temp % 10;
        temp /= 10;
    }

    printf("Sum of digits: %d\n", digitSum);
    return 0;
}
-----------------------------------------
#include <stdio.h>

int main() {
    int num, reversed = 0, temp, original;

    printf("Enter a number: ");
    scanf("%d", &num);

    original = num;
    temp = num;

    // Reverse the number
    while (temp > 0) {
        reversed = reversed * 10 + temp % 10;
        temp /= 10;
    }

    // Check if palindrome
    if (reversed == original) {
        printf("%d is a palindrome.\n", num);
    } else {
        printf("%d is not a palindrome.\n", num);
    }

    return 0;
}
-----------------------------------------
#include <stdio.h>

int main() {
    int rows, num = 1;

    printf("Enter the number of rows: ");
    scanf("%d", &rows);

    for (int i = 1; i <= rows; i++) {
        for (int j = 1; j <= i; j++) {
            printf("%d ", num++);
        }
        printf("\n");
    }

    return 0;
}
------------------------------------
#include <stdio.h>

int main() {
    int start, end;

    printf("Enter the start and end numbers for the tables: ");
    scanf("%d %d", &start, &end);

    for (int i = 1; i <= 10; i++) {
        for (int j = start; j <= end; j++) {
            printf("%d x %d = %d\t", j, i, j * i);
        }
        printf("\n");
    }

    return 0;
}
-----------------------------------------------
#include <stdio.h>
#include <stdbool.h>

bool isPrime(int num) {
    if (num <= 1) return false;
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) return false;
    }
    return true;
}

int main() {
    int n, num;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    printf("Prime numbers: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &num);
        if (isPrime(num)) {
            printf("%d ", num);
        }
    }
    printf("\n");

    return 0;
}
------------------------------------------------
#include <stdio.h>

long factorial(int num) {
    long fact = 1;
    for (int i = 1; i <= num; i++) {
        fact *= i;
    }
    return fact;
}

int main() {
    int n;
    double sum = 0.0;

    printf("Enter the value of n: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        sum += (double)i / factorial(i);
    }

    printf("Sum of the series: %.2f\n", sum);
    return 0;
}
---------------------------------------------
#include <stdio.h>

int main() {
    printf("Perfect numbers below 500: ");
    for (int num = 1; num < 500; num++) {
        int sum = 0;
        for (int i = 1; i <= num / 2; i++) {
            if (num % i == 0) sum += i;
        }
        if (sum == num) printf("%d ", num);
    }
    printf("\n");
    return 0;
}
-------------------------------------------------
#include <stdio.h>

int main() {
    int lines, ch = 'A';

    printf("Enter the number of lines: ");
    scanf("%d", &lines);

    for (int i = 1; i <= lines; i++) {
        for (int j = 1; j <= i; j++) {
            printf("%c ", ch++);
        }
        printf("\n");
    }

    return 0;
}
------------------------------------------------
#include <stdio.h>

int main() {
    int num, lastDigit, digitSum = 0;

    printf("Enter a number: ");
    scanf("%d", &num);

    // Extract last digit
    lastDigit = num % 10;

    // Calculate sum of digits
    while (num > 0) {
        digitSum += num % 10;  // Add the last digit to sum
        num /= 10;             // Remove the last digit
    }

    printf("Last digit: %d\n", lastDigit);
    printf("Sum of digits: %d\n", digitSum);

    return 0;
}
------------------------------------------------------
function:
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch;
    int choice;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    do {
        printf("\nMenu:\n");
        printf("1. Check if it is an alphabet\n");
        printf("2. Check if it is a digit\n");
        printf("3. Check if it is lowercase\n");
        printf("4. Check if it is uppercase\n");
        printf("5. Convert to uppercase\n");
        printf("6. Convert to lowercase\n");
        printf("7. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                if (isalpha(ch))
                    printf("'%c' is an alphabet.\n", ch);
                else
                    printf("'%c' is not an alphabet.\n", ch);
                break;
            case 2:
                if (isdigit(ch))
                    printf("'%c' is a digit.\n", ch);
                else
                    printf("'%c' is not a digit.\n", ch);
                break;
            case 3:
                if (islower(ch))
                    printf("'%c' is lowercase.\n", ch);
                else
                    printf("'%c' is not lowercase.\n", ch);
                break;
            case 4:
                if (isupper(ch))
                    printf("'%c' is uppercase.\n", ch);
                else
                    printf("'%c' is not uppercase.\n", ch);
                break;
            case 5:
                printf("Uppercase: %c\n", toupper(ch));
                break;
            case 6:
                printf("Lowercase: %c\n", tolower(ch));
                break;
            case 7:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice.\n");
        }
    } while (choice != 7);

    return 0;
}
-------------------------------------------------------------
#include <stdio.h>
#include <math.h>

int main() {
    float x1, y1, x2, y2;
    int choice;

    printf("Enter coordinates of first point (x1, y1): ");
    scanf("%f %f", &x1, &y1);
    printf("Enter coordinates of second point (x2, y2): ");
    scanf("%f %f", &x2, &y2);

    do {
        printf("\nMenu:\n");
        printf("1. Distance between points\n");
        printf("2. Slope of line between points\n");
        printf("3. Check if they lie in the same quadrant\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1: {
                float distance = sqrt(pow(x2 - x1, 2) + pow(y2 - y1, 2));
                printf("Distance between points: %.2f\n", distance);
                break;
            }
            case 2: {
                if (x2 == x1)
                    printf("Slope is undefined (vertical line).\n");
                else {
                    float slope = (y2 - y1) / (x2 - x1);
                    printf("Slope of the line: %.2f\n", slope);
                }
                break;
            }
            case 3: {
                if ((x1 > 0 && y1 > 0 && x2 > 0 && y2 > 0) ||
                    (x1 < 0 && y1 > 0 && x2 < 0 && y2 > 0) ||
                    (x1 < 0 && y1 < 0 && x2 < 0 && y2 < 0) ||
                    (x1 > 0 && y1 < 0 && x2 > 0 && y2 < 0))
                    printf("Both points lie in the same quadrant.\n");
                else
                    printf("Points do not lie in the same quadrant.\n");
                break;
            }
            case 4:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice.\n");
        }
    } while (choice != 4);

    return 0;
}
--------------------------------------
#include <stdio.h>

int isEven(int num) {
    return num % 2 == 0;
}

int main() {
    int n, num;

    printf("Enter the number of integers: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter a number: ");
        scanf("%d", &num);
        if (isEven(num))
            printf("%d is even.\n", num);
        else
            printf("%d is odd.\n", num);
    }

    return 0;
}
-----------------------------------------------
Problem 4: Function to display the next n characters.
Code:
c
Copy code
#include <stdio.h>

void displayNextChars(char ch, int n) {
    for (int i = 0; i < n; i++) {
        printf("%c ", ch + i);
    }
    printf("\n");
}

int main() {
    char ch;
    int n;

    printf("Enter a character: ");
    scanf(" %c", &ch);
    printf("Enter the number of next characters to display: ");
    scanf("%d", &n);

    displayNextChars(ch, n);
    return 0;
}
---------------------------------------------
roblem 1: Function to check if a number is prime.
Code:
c
Copy code
#include <stdio.h>
#include <stdbool.h>

bool isPrime(int num) {
    if (num <= 1) return false;
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) return false;
    }
    return true;
}

int main() {
    int count = 0, num = 2;

    printf("First 10 prime numbers:\n");
    while (count < 10) {
        if (isPrime(num)) {
            printf("%d ", num);
            count++;
        }
        num++;
    }
    printf("\n");

    return 0;
}
--------------------------
Problem 2: Function to classify characters and count them.
Code:
c
Copy code
#include <stdio.h>
#include <ctype.h>

int classifyChar(char ch) {
    if (isalpha(ch)) return 1;
    if (isdigit(ch)) return 2;
    return 3;  // Special symbol
}

int main() {
    char ch;
    int alphabets = 0, digits = 0, special = 0;

    printf("Enter characters (press EOF to stop):\n");
    while ((ch = getchar()) != EOF) {
        int type = classifyChar(ch);
        if (type == 1) alphabets++;
        else if (type == 2) digits++;
        else special++;
    }

    printf("Alphabets: %d\n", alphabets);
    printf("Digits: %d\n", digits);
    printf("Special symbols: %d\n", special);

    return 0;
}
----------------------------------------------
Problem 3: Calculate 
𝑥
𝑛
x 
n
  and factorial, then use to calculate series.
Code:
c
Copy code
#include <stdio.h>
#include <math.h>

double power(double x, int n) {
    double result = 1.0;
    for (int i = 1; i <= n; i++) {
        result *= x;
    }
    return result;
}

long factorial(int n) {
    long fact = 1;
    for (int i = 1; i <= n; i++) {
        fact *= i;
    }
    return fact;
}

int main() {
    double x, sinx = 0.0;
    int terms;

    printf("Enter the value of x (in radians): ");
    scanf("%lf", &x);
    printf("Enter the number of terms: ");
    scanf("%d", &terms);

    for (int i = 1; i <= terms; i += 2) {
        double term = power(x, i) / factorial(i);
        if ((i / 2) % 2 == 0)
            sinx += term;
        else
            sinx -= term;
    }

    printf("Approximation of sin(%lf) = %lf\n", x, sinx);
    return 0;
}
---------------------------------------------
recursion:
#include <stdio.h>

int gcd(int a, int b) {
    if (b == 0)
        return a; // Base case
    return gcd(b, a % b); // Recursive call
}

int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    printf("GCD of %d and %d is %d\n", a, b, gcd(a, b));
    return 0;
}
----------------------------------------------

Let's work through the problems step by step and provide solutions in C.

Set A
1. Write a recursive function to calculate the GCD of two numbers.
The GCD (Greatest Common Divisor) is calculated using the Euclidean algorithm:

If b = 0, GCD is a.
Otherwise, GCD is gcd(b, a % b).
Code:
c
Copy code
#include <stdio.h>

int gcd(int a, int b) {
    if (b == 0)
        return a; // Base case
    return gcd(b, a % b); // Recursive call
}

int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    printf("GCD of %d and %d is %d\n", a, b, gcd(a, b));
    return 0;
}
2. Write a recursive function to calculate 
𝑥
𝑛
x 
n
 .
Power calculation is done recursively:

If n = 0, 
𝑥
𝑛
=
1
x 
n
 =1.
Otherwise, 
𝑥
𝑛
=
𝑥
×
𝑥
𝑛
−
1
x 
n
 =x×x 
n−1
 .
Code:
c
Copy code
#include <stdio.h>

double power(double x, int n) {
    if (n == 0)
        return 1; // Base case
    return x * power(x, n - 1); // Recursive call
}

int main() {
    double x;
    int n;
    printf("Enter the base (x) and exponent (n): ");
    scanf("%lf %d", &x, &n);
    printf("%lf raised to the power %d is %lf\n", x, n, power(x, n));
    return 0;
}
----------------------------------------
3. Write a recursive function to calculate the factorial of a number.
Factorial is calculated as:

If n = 0 or n = 1, factorial is 1.
Otherwise, 
𝑛
!
=
𝑛
×
(
𝑛
−
1
)
!
n!=n×(n−1)!.
Code:
c
Copy code
#include <stdio.h>

long long factorial(int n) {
    if (n == 0 || n == 1)
        return 1; // Base case
    return n * factorial(n - 1); // Recursive call
}

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    printf("Factorial of %d is %lld\n", n, factorial(n));
    return 0;
}
-----------------------------------------------
#include <stdio.h>

int fibonacci(int n) {
    if (n == 1 || n == 2)
        return 1; // Base cases
    return fibonacci(n - 1) + fibonacci(n - 2); // Recursive call
}

int main() {
    int n;
    printf("Enter the number of terms: ");
    scanf("%d", &n);
    for (int i = 1; i <= n; i++) {
        printf("%d ", fibonacci(i));
    }
    printf("\n");
    return 0;
}
--------------------------------------
. Write a recursive function to calculate the sum of digits until a single digit is obtained.
This is done recursively:

If the number has only one digit, return it.
Otherwise, compute the sum of digits and recurse.
Code:
c
Copy code
#include <stdio.h>

int sumOfDigits(int n) {
    if (n < 10)
        return n; // Base case
    return sumOfDigits(n % 10 + sumOfDigits(n / 10)); // Recursive call
}

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    printf("The single-digit sum is %d\n", sumOfDigits(n));
    return 0;
}
-----------------------------------------------
 Write a recursive function to print digits of a number in reverse order.
Reverse printing:

Print the last digit.
Recurse with the remaining digits.
Code:
c
Copy code
#include <stdio.h>

void reversePrint(int n) {
    if (n < 10) {
        printf("%d ", n); // Base case
        return;
    }
    printf("%d ", n % 10); // Print last digit
    reversePrint(n / 10);  // Recursive call
}

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    printf("Digits in reverse order: ");
    reversePrint(n);
    printf("\n");
    return 0;
}
------------------------------------
 Write a recursive function for the Towers of Hanoi problem.
Towers of Hanoi is solved by:

Moving 
𝑛
−
1
n−1 disks from source to auxiliary.
Moving the nth disk from source to destination.
Moving 
𝑛
−
1
n−1 disks from auxiliary to destination.
Code:
c
Copy code
#include <stdio.h>

void towersOfHanoi(int n, char source, char destination, char auxiliary) {
    if (n == 1) {
        printf("Move disk 1 from %c to %c\n", source, destination);
        return;
    }
    towersOfHanoi(n - 1, source, auxiliary, destination); // Move n-1 disks to auxiliary
    printf("Move disk %d from %c to %c\n", n, source, destination); // Move nth disk
    towersOfHanoi(n - 1, auxiliary, destination, source); // Move n-1 disks to destination
}

int main() {
    int n;
    printf("Enter the number of disks: ");
    scanf("%d", &n);
    towersOfHanoi(n, 'A', 'C', 'B'); // A: source, C: destination, B: auxiliary
    return 0;
}
----------------------------------
Arrays:
 Write a function to sort an array of n integers.
Steps:

Input: Accept n integers from the user into an array.
Sorting: Use a sorting algorithm (like Bubble Sort).
Output: Display the sorted array.
Code:

c
Copy code
#include <stdio.h>

void sortArray(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main() {
    int n;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    sortArray(arr, n);

    printf("Sorted array: ");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");
    return 0;
}
---------------------------------------------
Write a program to accept a decimal number and convert it to binary, octal, and hexadecimal.
Steps:

Input: Accept a decimal number.
Conversion: Use % and / to convert to binary and octal. Use %x for hexadecimal in printf.
Code:

c
Copy code
#include <stdio.h>

void convert(int num) {
    printf("Binary: ");
    for (int i = 31; i >= 0; i--) {
        printf("%d", (num >> i) & 1);
    }
    printf("\n");

    printf("Octal: %o\n", num);
    printf("Hexadecimal: %X\n", num);
}

int main() {
    int num;
    printf("Enter a decimal number: ");
    scanf("%d", &num);

    convert(num);

    return 0;
}
-----------------------------------------------
Write a function for Linear Search.
Steps:

Input: Accept an array of n elements and a key to search for.
Search: Iterate through the array and check if the key is found.
Output: Display the position or -1 if not found.
Code:

c
Copy code
#include <stdio.h>

int linearSearch(int arr[], int n, int key) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == key)
            return i; // Return position
    }
    return -1; // Not found
}

int main() {
    int n, key;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    printf("Enter the key to search: ");
    scanf("%d", &key);

    int result = linearSearch(arr, n, key);
    if (result == -1)
        printf("Key not found.\n");
    else
        printf("Key found at position %d\n", result + 1);

    return 0;
}
-----------------------------------------------
Separate positive and negative numbers into two arrays.
Steps:

Input: Accept 10 numbers.
Segregation: Separate positives and negatives into two arrays.
Output: Display both arrays.
Code:

c
Copy code
#include <stdio.h>

int main() {
    int arr[10], positives[10], negatives[10];
    int posCount = 0, negCount = 0;

    printf("Enter 10 integers:\n");
    for (int i = 0; i < 10; i++) {
        scanf("%d", &arr[i]);
        if (arr[i] >= 0)
            positives[posCount++] = arr[i];
        else
            negatives[negCount++] = arr[i];
    }

    printf("Positive numbers: ");
    for (int i = 0; i < posCount; i++)
        printf("%d ", positives[i]);

    printf("\nNegative numbers: ");
    for (int i = 0; i < negCount; i++)
        printf("%d ", negatives[i]);

    printf("\n");
    return 0;
}
--------------------------------------------
 Sort a matrix row-wise and column-wise.
Steps:

Input: Accept an 
𝑀
𝑥
𝑁
MxN matrix.
Row-wise sorting: Sort each row individually.
Column-wise sorting: Transpose the matrix, sort rows, and transpose again.
Code:

c
Copy code
#include <stdio.h>

void sortRow(int row[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (row[j] > row[j + 1]) {
                int temp = row[j];
                row[j] = row[j + 1];
                row[j + 1] = temp;
            }
        }
    }
}

void sortMatrix(int mat[3][3], int m, int n) {
    // Row-wise sorting
    for (int i = 0; i < m; i++) {
        sortRow(mat[i], n);
    }

    // Column-wise sorting
    for (int j = 0; j < n; j++) {
        for (int i = 0; i < m - 1; i++) {
            for (int k = i + 1; k < m; k++) {
                if (mat[i][j] > mat[k][j]) {
                    int temp = mat[i][j];
                    mat[i][j] = mat[k][j];
                    mat[k][j] = temp;
                }
            }
        }
    }
}

int main() {
    int mat[3][3] = {{5, 2, 9}, {1, 4, 6}, {8, 3, 7}};
    printf("Original matrix:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", mat[i][j]);
        }
        printf("\n");
    }

    sortMatrix(mat, 3, 3);

    printf("Sorted matrix:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", mat[i][j]);
        }
        printf("\n");
    }
    return 0;
}
----------------------------------------------------
 Merge two sorted arrays into a third sorted array.
This involves:

Compare elements of two arrays one by one.
Merge into a third array maintaining order.
Code:

c
Copy code
#include <stdio.h>

void mergeSortedArrays(int a[], int n1, int b[], int n2, int c[]) {
    int i = 0, j = 0, k = 0;
    while (i < n1 && j < n2) {
        if (a[i] < b[j])
            c[k++] = a[i++];
        else
            c[k++] = b[j++];
    }
    while (i < n1)
        c[k++] = a[i++];
    while (j < n2)
        c[k++] = b[j++];
}

int main() {
    int a[] = {10, 25, 90};
    int b[] = {9, 16, 22, 26};
    int c[7]; // Result array

    mergeSortedArrays(a, 3, b, 4, c);

    printf("Merged array: ");
    for (int i = 0; i < 7; i++)
        printf("%d ", c[i]);
    printf("\n");

    return 0;
}
---------------------------------------------------
Write a program to add and multiply two matrices.
Steps:

Addition: Ensure the matrices are of the same dimensions and sum corresponding elements.
Multiplication: Ensure the number of columns of the first matrix matches the number of rows of the second matrix.
Code:

c
Copy code
#include <stdio.h>

void addMatrices(int a[3][3], int b[3][3], int result[3][3]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            result[i][j] = a[i][j] + b[i][j];
        }
    }
}

void multiplyMatrices(int a[3][3], int b[3][3], int result[3][3]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            result[i][j] = 0;
            for (int k = 0; k < 3; k++) {
                result[i][j] += a[i][k] * b[k][j];
            }
        }
    }
}

int main() {
    int a[3][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    int b[3][3] = {{9, 8, 7}, {6, 5, 4}, {3, 2, 1}};
    int result[3][3];

    addMatrices(a, b, result);
    printf("Matrix after addition:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", result[i][j]);
        }
        printf("\n");
    }

    multiplyMatrices(a, b, result);
    printf("Matrix after multiplication:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}
-----------------------------------------------------
Write a menu-driven program to perform operations on a square matrix.
Steps:

Input: Accept a square matrix of size 
𝑛
×
𝑛
n×n.
Symmetry Check: Compare elements at positions 
(
𝑖
,
𝑗
)
(i,j) and 
(
𝑗
,
𝑖
)
(j,i).
Trace: Sum the diagonal elements.
Upper Triangular Matrix Check: Ensure elements below the main diagonal are zero.
Lower Triangular Matrix Check: Ensure elements above the main diagonal are zero.
Identity Matrix Check: Ensure diagonal elements are 1, and others are 0.
Code:

c
Copy code
#include <stdio.h>

int isSymmetric(int mat[3][3], int n) {
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if (mat[i][j] != mat[j][i])
                return 0;
        }
    }
    return 1;
}

int calculateTrace(int mat[3][3], int n) {
    int trace = 0;
    for (int i = 0; i < n; i++) {
        trace += mat[i][i];
    }
    return trace;
}

int isUpperTriangular(int mat[3][3], int n) {
    for (int i = 1; i < n; i++) {
        for (int j = 0; j < i; j++) {
            if (mat[i][j] != 0)
                return 0;
        }
    }
    return 1;
}

int isLowerTriangular(int mat[3][3], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (mat[i][j] != 0)
                return 0;
        }
    }
    return 1;
}

int isIdentityMatrix(int mat[3][3], int n) {
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if ((i == j && mat[i][j] != 1) || (i != j && mat[i][j] != 0))
                return 0;
        }
    }
    return 1;
}

int main() {
    int mat[3][3];
    int n = 3;

    printf("Enter the elements of the matrix:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            scanf("%d", &mat[i][j]);
        }
    }

    printf("1. Check if symmetric\n2. Display trace\n3. Check if upper triangular\n4. Check if lower triangular\n5. Check if identity matrix\n");
    int choice;
    printf("Enter choice: ");
    scanf("%d", &choice);

    switch (choice) {
        case 1:
            if (isSymmetric(mat, n))
                printf("Matrix is symmetric\n");
            else
                printf("Matrix is not symmetric\n");
            break;
        case 2:
            printf("Trace: %d\n", calculateTrace(mat, n));
            break;
        case 3:
            if (isUpperTriangular(mat, n))
                printf("Matrix is upper triangular\n");
            else
                printf("Matrix is not upper triangular\n");
            break;
        case 4:
            if (isLowerTriangular(mat, n))
                printf("Matrix is lower triangular\n");
            else
                printf("Matrix is not lower triangular\n");
            break;
        case 5:
            if (isIdentityMatrix(mat, n))
                printf("Matrix is identity matrix\n");
            else
                printf("Matrix is not identity matrix\n");
            break;
        default:
            printf("Invalid choice\n");
            break;
    }

    return 0;
}
-------------------------------------------------
pointers:
Write a program that initializes two arrays of pointers. Then, by using pointers, interchange the elements of the arrays (Don't use [] anywhere in the program).
ChatGPT said:
ChatGPT
Here’s a program that initializes two arrays of pointers and interchanges their elements using only pointers (no [] operator is used):

Steps:
Initialize two arrays as arrays of pointers.
Use pointer arithmetic to access and interchange the elements.
Swap the elements by dereferencing the pointers.
Code:
c
Copy code
#include <stdio.h>

void interchange(int *arr1[], int *arr2[], int size) {
    for (int i = 0; i < size; i++) {
        int *temp = *(arr1 + i); // Access element of arr1 using pointer arithmetic
        *(arr1 + i) = *(arr2 + i); // Swap element of arr1 with arr2
        *(arr2 + i) = temp; // Assign temp to arr2
    }
}

int main() {
    int a = 1, b = 2, c = 3, d = 4, e = 5; // Example values
    int f = 6, g = 7, h = 8, i = 9, j = 10;

    // Initialize arrays of pointers
    int *arr1[] = {&a, &b, &c, &d, &e};
    int *arr2[] = {&f, &g, &h, &i, &j};

    // Print arrays before interchanging
    printf("Before interchanging:\n");
    printf("Array 1: ");
    for (int k = 0; k < 5; k++) {
        printf("%d ", **(arr1 + k)); // Access element using pointer arithmetic
    }
    printf("\nArray 2: ");
    for (int k = 0; k < 5; k++) {
        printf("%d ", **(arr2 + k)); // Access element using pointer arithmetic
    }
    printf("\n");

    // Interchange elements of the arrays
    interchange(arr1, arr2, 5);

    // Print arrays after interchanging
    printf("\nAfter interchanging:\n");
    printf("Array 1: ");
    for (int k = 0; k < 5; k++) {
        printf("%d ", **(arr1 + k));
    }
    printf("\nArray 2: ");
    for (int k = 0; k < 5; k++) {
        printf("%d ", **(arr2 + k));
    }
    printf("\n");

    return 0;
}
----------------------------------------------
Write a program to allocate memory dynamically for n integers such that the memory is initialized to 0. Accept the data from the user and find the range of the data elements.

#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, i;
    int *arr;
    int min, max, range;

    // Accept the number of elements
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    // Dynamically allocate memory and initialize it to 0
    arr = (int *)calloc(n, sizeof(int));
    if (arr == NULL) {
        printf("Memory allocation failed!\n");
        return 1; // Exit if memory allocation fails
    }

    // Accept data from the user
    printf("Enter %d integers:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", arr + i); // Store the value at dynamically allocated memory
    }

    // Find the minimum and maximum values
    min = max = arr[0]; // Initialize min and max with the first element
    for (i = 1; i < n; i++) {
        if (*(arr + i) < min) {
            min = *(arr + i); // Update minimum
        }
        if (*(arr + i) > max) {
            max = *(arr + i); // Update maximum
        }
    }

    // Calculate the range
    range = max - min;

    // Display the range
    
    printf("The range of the data elements is: %d\n", range);

    // Free the allocated memory
    free(arr);

    return 0;
}
-------------------------------------------------------;
Accept n integers in array A. Pass this array and two counter variables to a function, which will set the first counter to the total number of even values in the array and the other to the total number of odd values

#include <stdio.h>

// Function to count even and odd numbers
void countEvenOdd(int arr[], int n, int *evenCount, int *oddCount) {
    int i;
    *evenCount = 0; // Initialize even count
    *oddCount = 0;  // Initialize odd count

    for (i = 0; i < n; i++) {
        if (arr[i] % 2 == 0) {
            (*evenCount)++; // Increment even count
        } else {
            (*oddCount)++;  // Increment odd count
        }
    }
}

int main() {
    int n, i;
    int evenCount, oddCount;

    // Accept the size of the array
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int arr[n]; // Declare the array

    // Accept the elements of the array
    printf("Enter %d integers:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    // Call the function to count even and odd numbers
    countEvenOdd(arr, n, &evenCount, &oddCount);

    // Display the counts
    printf("Total even numbers: %d\n", evenCount);
    printf("Total odd numbers: %d\n", oddCount);

    return 0;
}
=========================================================
Write a function that accepts a number and three flags as parameters. If the number is even, set the first flag to 1. If the number is prime, set the second flag to 1. If the number is divisible by 3 or 7, set the third flag to 1. In main, accept an integer and use this function to check if it is even, prime, and divisible by 3 or 7. (Hint: pass the addresses of the flags to the function)

#include <stdio.h>
#include <math.h>

// Function to check conditions on the number
void checkNumber(int num, int *isEven, int *isPrime, int *isDivBy3or7) {
    // Check if the number is even
    *isEven = (num % 2 == 0) ? 1 : 0;

    // Check if the number is prime
    if (num < 2) {
        *isPrime = 0;
    } else {
        *isPrime = 1;
        for (int i = 2; i <= sqrt(num); i++) {
            if (num % i == 0) {
                *isPrime = 0;
                break;
            }
        }
    }

    // Check if the number is divisible by 3 or 7
    *isDivBy3or7 = (num % 3 == 0 || num % 7 == 0) ? 1 : 0;
}

int main() {
    int num;
    int isEven = 0, isPrime = 0, isDivBy3or7 = 0;

    // Accept the number from the user
    printf("Enter an integer: ");
    scanf("%d", &num);

    // Call the function with the number and flag addresses
    checkNumber(num, &isEven, &isPrime, &isDivBy3or7);

    // Display the results
    printf("Results for the number %d:\n", num);
    printf("Is Even: %d\n", isEven);
    printf("Is Prime: %d\n", isPrime);
    printf("Is Divisible by 3 or 7: %d\n", isDivBy3or7);

    return 0;
}
----------------------------------------

Accept the number of rows (m) and columns (n) for a matrix and dynamically allocate memory for the matrix. Accept and display the matrix using pointers. (Hint: Use an array of pointers)

#include <stdio.h>
#include <stdlib.h>

int main() {
    int m, n, i, j;
    int **matrix;

    // Accept the number of rows and columns
    printf("Enter the number of rows (m): ");
    scanf("%d", &m);
    printf("Enter the number of columns (n): ");
    scanf("%d", &n);

    // Dynamically allocate memory for the matrix (array of pointers)
    matrix = (int **)malloc(m * sizeof(int *));
    if (matrix == NULL) {
        printf("Memory allocation failed for rows.\n");
        return 1;
    }

    // Allocate memory for each row
    for (i = 0; i < m; i++) {
        matrix[i] = (int *)malloc(n * sizeof(int));
        if (matrix[i] == NULL) {
            printf("Memory allocation failed for row %d.\n", i + 1);
            return 1;
        }
    }

    // Accept the elements of the matrix
    printf("Enter the elements of the matrix:\n");
    for (i = 0; i < m; i++) {
        for (j = 0; j < n; j++) {
            printf("Element [%d][%d]: ", i + 1, j + 1);
            scanf("%d", &matrix[i][j]);
        }
    }

    // Display the matrix
    printf("The matrix is:\n");
    for (i = 0; i < m; i++) {
        for (j = 0; j < n; j++) {
            printf("%d ", *(*(matrix + i) + j));
        }
        printf("\n");
    }

    // Free the dynamically allocated memory
    for (i = 0; i < m; i++) {
        free(matrix[i]);
    }
    free(matrix);

    return 0;
}
---------------------------------
string:
Write a program to accept the string and select one character from user which is may/may not be in that string. If it is present in the string deletes that character from the given string. Print the number of occurrences of that character and the remaining string. (Use array/pointer and accept string from user). Example: "I'm fine, how r u?" char *h; o/p="I'm fine, ow r u?"
#include <stdio.h>
#include <string.h>

void removeCharacter(char *str, char ch) {
    char *src = str, *dest = str; // Pointers for traversal
    int count = 0;               // Counter for occurrences of the character

    // Traverse through the string
    while (*src != '\0') {
        if (*src != ch) {
            *dest = *src; // Copy the character if it's not the one to be removed
            dest++;
        } else {
            count++; // Increment count if the character matches
        }
        src++;
    }

    *dest = '\0'; // Null-terminate the resulting string

    // Print results
    printf("Number of occurrences of '%c': %d\n", ch, count);
    printf("Updated string: \"%s\"\n", str);
}

int main() {
    char str[100], ch;

    // Accept the string from the user
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Remove trailing newline if present
    size_t len = strlen(str);
    if (len > 0 && str[len - 1] == '\n') {
        str[len - 1] = '\0';
    }

    // Accept the character to be removed
    printf("Enter the character to remove: ");
    scanf("%c", &ch);

    // Call the function to remove the character
    removeCharacter(str, ch);

    return 0;
}
--------------------------------------------
Write a program that accepts a sentence and splits the sentence into words. Sort each word and reconstruct the sentence. Input – this is a string Output – hist is a ginrst

#include <stdio.h>
#include <string.h>
#include <stdlib.h>

// Function to sort characters of a word
void sortWord(char *word) {
    int len = strlen(word);
    for (int i = 0; i < len - 1; i++) {
        for (int j = i + 1; j < len; j++) {
            if (word[i] > word[j]) {
                // Swap characters if out of order
                char temp = word[i];
                word[i] = word[j];
                word[j] = temp;
            }
        }
    }
}

// Function to split, sort, and reconstruct the sentence
void processSentence(char *sentence) {
    char *word = strtok(sentence, " "); // Split sentence into words
    char result[1000] = ""; // To store the reconstructed sentence

    while (word != NULL) {
        sortWord(word);               // Sort the current word
        strcat(result, word);         // Append sorted word to result
        strcat(result, " ");          // Add a space after the word
        word = strtok(NULL, " ");     // Move to the next word
    }

    // Remove the trailing space from the result
    result[strlen(result) - 1] = '\0';

    printf("Reconstructed sentence: %s\n", result);
}

int main() {
    char sentence[1000];

    // Accept the input sentence
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    // Remove trailing newline if present
    size_t len = strlen(sentence);
    if (len > 0 && sentence[len - 1] == '\n') {
        sentence[len - 1] = '\0';
    }

    // Process the sentence
    processSentence(sentence);

    return 0;
}
-----------------------------------------------
Write a C program that will replace a substring of a given string by another string of length less than (or might be equal to) the length of the existing substring. Use pointers for this operation.
#include <stdio.h>
#include <string.h>

// Function to replace a substring with another string
void replaceSubstring(char *str, const char *oldSub, const char *newSub) {
    char result[1000]; // Temporary result string
    char *pos = str;   // Pointer to the current position in the string
    char *found;       // Pointer to the found substring

    int oldLen = strlen(oldSub);
    int newLen = strlen(newSub);
    int index = 0;

    result[0] = '\0'; // Initialize result as an empty string

    while ((found = strstr(pos, oldSub)) != NULL) { // Locate substring
        // Copy characters before the substring
        while (pos < found) {
            result[index++] = *pos++;
        }

        // Copy the replacement string
        for (int i = 0; i < newLen; i++) {
            result[index++] = newSub[i];
        }

        // Move past the old substring
        pos += oldLen;
    }

    // Copy the remaining part of the string
    while (*pos != '\0') {
        result[index++] = *pos++;
    }

    result[index] = '\0'; // Null-terminate the result

    // Copy result back to the original string
    strcpy(str, result);
}

int main() {
    char str[1000], oldSub[100], newSub[100];

    // Accept the original string
    printf("Enter the original string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0'; // Remove trailing newline

    // Accept the substring to replace
    printf("Enter the substring to replace: ");
    fgets(oldSub, sizeof(oldSub), stdin);
    oldSub[strcspn(oldSub, "\n")] = '\0'; // Remove trailing newline

    // Accept the replacement string
    printf("Enter the replacement string: ");
    fgets(newSub, sizeof(newSub), stdin);
    newSub[strcspn(newSub, "\n")] = '\0'; // Remove trailing newline

    // Perform the replacement
    replaceSubstring(str, oldSub, newSub);

    // Display the modified string
    printf("Modified string: %s\n", str);

    return 0;
}
-------------------------------------------
Write a program which accepts a string and checks whether it is palindrome or not. Example: input: madam output: Given string is palindrome

#include <stdio.h>
#include <string.h>
#include <ctype.h>

// Function to check if a string is a palindrome
int isPalindrome(const char *str) {
    const char *start = str;                  // Pointer to the start of the string
    const char *end = str + strlen(str) - 1;  // Pointer to the end of the string

    while (start < end) {
        if (*start != *end) {
            return 0; // Return false if characters don't match
        }
        start++;
        end--;
    }
    return 1; // Return true if the entire string is checked
}

int main() {
    char str[1000];

    // Accept the input string
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Remove trailing newline character
    str[strcspn(str, "\n")] = '\0';

    // Check if the string is a palindrome
    if (isPalindrome(str)) {
        printf("Given string is a palindrome.\n");
    } else {
        printf("Given string is not a palindrome.\n");
    }

    return 0;
}
-----------------------------------------------------
Write a program that accepts names of n cities and write functions for the following: a. Search for a city b. Displays the longest string c. Sorts the names

#include <stdio.h>
#include <string.h>
#include <stdlib.h>

// Function to search for a city
int searchCity(char cities[][100], int n, const char *cityName) {
    for (int i = 0; i < n; i++) {
        if (strcmp(cities[i], cityName) == 0) {
            return i; // Return index if city is found
        }
    }
    return -1; // Return -1 if city is not found
}

// Function to find and display the longest city name
void displayLongestCity(char cities[][100], int n) {
    int maxLength = 0;
    int longestIndex = 0;

    for (int i = 0; i < n; i++) {
        if (strlen(cities[i]) > maxLength) {
            maxLength = strlen(cities[i]);
            longestIndex = i;
        }
    }

    printf("The longest city name is: %s\n", cities[longestIndex]);
}

// Function to sort city names alphabetically
void sortCities(char cities[][100], int n) {
    char temp[100];

    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (strcmp(cities[i], cities[j]) > 0) {
                // Swap cities[i] and cities[j]
                strcpy(temp, cities[i]);
                strcpy(cities[i], cities[j]);
                strcpy(cities[j], temp);
            }
        }
    }
}

// Main function
int main() {
    int n;

    // Accept the number of cities
    printf("Enter the number of cities: ");
    scanf("%d", &n);
    getchar();  // Consume the newline character left by scanf

    char cities[n][100];  // Array to store city names

    // Accept the names of the cities
    printf("Enter the names of %d cities:\n", n);
    for (int i = 0; i < n; i++) {
        fgets(cities[i], sizeof(cities[i]), stdin);
        cities[i][strcspn(cities[i], "\n")] = '\0'; // Remove newline character
    }

    // Search for a city
    char search[100];
    printf("Enter the city name to search: ");
    fgets(search, sizeof(search), stdin);
    search[strcspn(search, "\n")] = '\0'; // Remove newline character

    int index = searchCity(cities, n, search);
    if (index != -1) {
        printf("City '%s' found at index %d.\n", search, index);
    } else {
        printf("City '%s' not found.\n", search);
    }

    // Display the longest city name
    displayLongestCity(cities, n);

    // Sort the cities and display the sorted list
    sortCities(cities, n);
    printf("Cities sorted in alphabetical order:\n");
    for (int i = 0; i < n; i++) {
        printf("%s\n", cities[i]);
    }

    return 0;
}
------------------------------------------------
Write a menu-driven program which performs the following operations on strings. Write a separate function for each option. Use pointers: i. Copy one string to another ii. Concatenate two strings iii. Count number of occurrences of a character in the string. iv. Replace all occurrences of a character by another

#include <stdio.h>
#include <string.h>

// Function to copy one string to another
void copyString(char *source, char *destination) {
    while (*source != '\0') {
        *destination = *source;
        source++;
        destination++;
    }
    *destination = '\0'; // Null-terminate the destination string
}

// Function to concatenate two strings
void concatenateStrings(char *str1, char *str2, char *result) {
    while (*str1 != '\0') { // Copy first string to result
        *result = *str1;
        result++;
        str1++;
    }
    while (*str2 != '\0') { // Copy second string to result
        *result = *str2;
        result++;
        str2++;
    }
    *result = '\0'; // Null-terminate the result string
}

// Function to count the occurrences of a character in a string
int countOccurrences(char *str, char ch) {
    int count = 0;
    while (*str != '\0') {
        if (*str == ch) {
            count++;
        }
        str++;
    }
    return count;
}

// Function to replace all occurrences of a character with another
void replaceCharacter(char *str, char oldChar, char newChar) {
    while (*str != '\0') {
        if (*str == oldChar) {
            *str = newChar;
        }
        str++;
    }
}

int main() {
    char str1[100], str2[100], result[200];
    char ch, oldChar, newChar;
    int choice, count;

    // Accept input strings
    printf("Enter the first string: ");
    fgets(str1, sizeof(str1), stdin);
    str1[strcspn(str1, "\n")] = '\0'; // Remove newline character

    printf("Enter the second string: ");
    fgets(str2, sizeof(str2), stdin);
    str2[strcspn(str2, "\n")] = '\0'; // Remove newline character

    do {
        // Display menu
        printf("\nMenu:\n");
        printf("1. Copy one string to another\n");
        printf("2. Concatenate two strings\n");
        printf("3. Count number of occurrences of a character in a string\n");
        printf("4. Replace all occurrences of a character by another\n");
        printf("5. Exit\n");

        // Accept user choice
        printf("Enter your choice (1-5): ");
        scanf("%d", &choice);
        getchar(); // Consume the newline character left by scanf

        switch (choice) {
            case 1:
                // Copy str1 to str2
                copyString(str1, str2);
                printf("String after copy: %s\n", str2);
                break;

            case 2:
                // Concatenate str1 and str2
                concatenateStrings(str1, str2, result);
                printf("Concatenated string: %s\n", result);
                break;

            case 3:
                // Count occurrences of a character in str1
                printf("Enter the character to count occurrences: ");
                scanf("%c", &ch);
                getchar(); // Consume the newline character
                count = countOccurrences(str1, ch);
                printf("Character '%c' occurred %d times in the string.\n", ch, count);
                break;

            case 4:
                // Replace all occurrences of a character by another
                printf("Enter the character to replace: ");
                scanf("%c", &oldChar);
                getchar(); // Consume the newline character
                printf("Enter the new character: ");
                scanf("%c", &newChar);
                getchar(); // Consume the newline character
                replaceCharacter(str1, oldChar, newChar);
                printf("String after replacement: %s\n", str1);
                break;

            case 5:
                // Exit
                printf("Exiting program...\n");
                break;

            default:
                printf("Invalid choice! Please try again.\n");
        }
    } while (choice != 5);

    return 0;
}

