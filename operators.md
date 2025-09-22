## 1.program to find the factorial of a number
```c
#include<stdio.h>
int main()
{
        int fact,num;
        printf("enter");
        scanf("%d",&num);
        if(num<0)
        {
                printf("enter only positive numbers");
        }
        else
        {
                fact=1;
                for(int i=1;i<=num;i++)
                {
                        fact*=i;
                        printf("factorial value is %d\t",i);
                }
                printf("\n");
                printf("enter factorial is %d\n",fact);
        }
        return 0;
}
```
## 2.find the biggest number
```c
#include<stdio.h>
int main()
{
        int a,b,c;
        printf("enter the numbers");
        scanf("%d%d%d",&a,&b,&c);
        if(a>b)
        {
                if(a>c)
                        printf("a is greater than b and c");
                else
                        printf("c is greater than a and c");
        }
        else if(b>a)
        {
                if(b>c)
                        printf("b is greater than a and c");
                else
                        printf("c is greater tha b and c");
        }
}
```
## 3. program which is greater number
```c
#include<stdio.h>
int main()
{
        int a=20,b=30;
        (a>b)?printf("a is greater than b\n"):printf("b is greater than c\n");
}
```
## 4. program to print numbers in decrement
```c
#include<stdio.h>
int main()
{
        int i=10;
        while(i-->0)
                printf("%d\t",i);
}
```
## 5.program to print prime number or not
```c
#include<stdio.h>
int main()
{
        int n;
        printf("enter:");
        scanf("%d",&n);
        if(n<=0)
                printf("it is not prime number");
        else
        {
                for(int i=1;i<n;i++)
                {
                        n%i==0;
                }
                printf("%d\n",n);
        }
        return 0;
}
```
## 7.Find the maximum average of all contiguous subarrays of size 4 in a given array.
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number");
        scanf("%d",&num);
        int arr[num];
        for(int i=0;i<num;i++)
        {
                scanf("%d",&arr[i]);
        }
        float k=4;
        float max=0;
        float avg;
        for(int i=0;i<=num-k;i++)
        {
                int sum=0;
                int count=0;
                for(int j=i;j<i+k;j++)
                {
                        sum=sum+arr[j];
                        count++;
                }
                if(count==k)
                {
                        printf("sum=%d\n",sum);
                        avg=sum/k;
                }
                if(avg>max)
                {
                        max=avg;
                }
        }
        printf("%f",max);
}
```
## 8. print the given number is set or not
```c
#include<stdio.h>
int main()
{
        int num,i;
        printf("enter the number:");
        scanf("%d %d",&num,&i);
        if(num&(1<<i))
                printf("%d number is set",num);
        else
                printf("%d number is not set",num);
}
```
## 9.given char is alphabet or not
```c
#include<stdio.h>
void main(){
        char ch;
        printf("enter the ch value");
        scanf("%c",&ch);
        if(ch>='A'&&ch<='Z')
                printf("the given alphabet is  between AtoZ");
        else
                printf("the given alphabet is  not between AtoZ");
}
```
## 10.Write a C program to print numbers from 0 to 80, displaying 8 numbers per line
```c
#include<stdio.h>
int main()
{
        int  n=80;
        for(int i=0;i<=n;i++)
        {
                if(i%8==0)
                {
                        printf("\n");
                }
                printf("%d\t",i);
        }
        return 0;
}
```
## 11.Write a C program to print a pyramid of stars with a given number of rows
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number:");
        scanf("%d",&num);
        for(int i=1;i<num;i++)
        {
                for(int k=1;k<=num-i;k++)
                {
                        printf(" ");
                }
                for(int j=1;j<=(2*i-1);j++)
                {
                                printf(" * ");
                }
                printf("\n");
        }

}
```
## 12.write c progran to print number pattern
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number");
        scanf("%d",&num);
        for(int i=1;i<=num;i++)
        {
                for(int j=1;j<=i;j++)
                {
                        printf("%d\t",j);
                }
                printf("\n");
        }
        return 0;
}
```
## 13.Write a C program to find and display all Pythagorean triplets (x, y, z) where x² + y² = z² and x, y, z < 50.
```c
include<stdio.h>
int main()
{
        int x,y,z;
        for(x=1;x<50;x++)
        {
                for(y=x+1;y<50;y++)
                {
                        for(z=y+1;z<50;z++)
                        {
                                if(x*x+y*y==z*z)
                                {
                                        printf("%d**+%d**=%d**\n",x,y,z);
                                }
                        }
                }
        }
}
```
## 14 fibnacci series
```c
#include<stdio.h>
int main()
{
        int n,next,first=0,sec=1;
        printf("enter the value");
        scanf("%d",&n);
        for(int i=0;i<=n;i++)
        {
                next=first+sec;
                first=sec;
                sec=next;
                printf("%d\t",next);
        }
        printf("\n");
}
```
## 15. hardcoded program for number in binary form find it is palindrome or not
```c
#include<stdio.h>
int main()
{
        int num=21;
        int arg[100];
        int a=0,k=0;
        for(int i=4;i>=0;i--)
        {
                arg[k++]=((num>>i)&1);
        }
        printf("\n");

        int flag=0;
        for(int i=0;i<k/2;i++)
        {
                if(arg[i]!=arg[k-i-1])
                {
                        printf("it is not palindrome\n");
                        flag=1;
                        break;
                }
        }
        if(flag==0)
        {
                printf("it is palindrome\n");
        }
}
```
## 17.program to write given number is palindrome or not in inary form
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number");
        scanf("%d",&num);
        int arr[10];
        int k=0;
        while(num>0)
        {
                arr[k++]=num%2;
                num=num/2;
        }
        int flag=0;
        for(int i=0,j=k-1;i<j;i++,j--)
        {
                if(arr[i]!=arr[j])
                {
                        flag=1;
                        printf("it is not palindrome\n");
                        break;
                }

        }
        if(flag==0)
        {
                printf("it is palindrome\n");
        }
}
```
## 18.Write a C program to find the GCD (Greatest Common Divisor) of two numbers using the Euclidean algorithm.
```c
#include <stdio.h>

int main() {
    int a, b, r;
    printf("Enter 2 numbers: ");
    scanf("%d %d", &a, &b);

    while (b) {
        r = a % b;
        a = b;
        b = r;
    }

    printf("GCD of 2 numbers is %d\n", a);
    return 0;
}
```
## 19.Write a C program to find the LCM (Least Common Multiple) of two numbers.
```c
#include <stdio.h>

int main() {
    int a, b, i;
    printf("Enter 2 numbers: ");
    scanf("%d %d", &a, &b);

    for (i = 1; i <= (a * b); i++) {
        if ((a * i) % b == 0) {
            printf("LCM is %d\n", (a * i));
            break;
        }
    }
    return 0;
}
```
## 20.Write a C program to print the multiplication table of a given number up to 10.
```c
#include <stdio.h>

int main() {
    int n, i;
    printf("Enter a number: ");
    scanf("%d", &n);

    for (i = 1; i <= 10; i++) {
        printf("%d * %d = %d\n", n, i, n * i);
    }

    return 0;
}
```
## 21.Write a C program to print all Armstrong numbers between 1 and 1000.
```c
#include <stdio.h>
#include <math.h>

int main() {
    int num, n, res, d, i;

    for (i = 1; i <= 1000; i++) {
        num = i;
        d = 0;
        res = 0;

        while (num) {
            num = num / 10;
            d++;
        }

        num = i;
        while (num) {
            n = num % 10;
            res += pow(n, d);
            num = num / 10;
        }

        if (i == res) {
            printf("%d is an Armstrong number\n", i);
        }
    }

    return 0;
}
```
## 22.Write a C program to implement a simple calculator using switch case for +, -, *, /, %.
```c
#include <stdio.h>

int main() {
    int a, b, res;
    char opt;

    printf("Enter values: ");
    scanf("%d %d", &a, &b);

    printf("Choose operation (+ - * / %): ");
    scanf(" %c", &opt);

    switch (opt) {
        case '+': res = a + b; break;
        case '-': res = a - b; break;
        case '*': res = a * b; break;
        case '/': 
            if (b != 0) res = a / b; 
            else { printf("Can't divide by 0\n"); return 1; }
            break;
        case '%': 
            if (b != 0) res = a % b; 
            else { printf("Can't divide by 0\n"); return 1; }
            break;
        default: printf("Invalid input\n"); return 1;
    }

    printf("Result is %d\n", res);
    return 0;
}
```
## 23.Write a C program to check whether a given number is a Palindrome or not.
```c
#include <stdio.h>

int main() {
    int num, res = 0, n, org;
    printf("Enter a number: ");
    scanf("%d", &num);

    org = num;
    while (num != 0) {
        n = num % 10;
        res = (res * 10) + n;
        num = num / 10;
    }

    if (org == res)
        printf("Palindrome\n");
    else
        printf("Not a palindrome\n");

    return 0;
}
```
## 24.Write a C program to find the sum of elements in the lower triangular part of an m x m matrix.
```c
#include <stdio.h>

int main() {
    int i, j, m, sum = 0;
    printf("Enter m for m*m matrix: ");
    scanf("%d", &m);

    int mat[m][m];
    printf("Enter matrix values:\n");
    for (i = 0; i < m; i++)
        for (j = 0; j < m; j++)
            scanf("%d", &mat[i][j]);

    for (i = 0; i < m; i++)
        for (j = 0; j < m; j++)
            if (i >= j)
                sum += mat[i][j];

    printf("Sum of lower triangular matrix = %d\n", sum);
    return 0;
}
```
## 25 Write a C program to find the sum of elements in the upper triangular part of an m x m matrix.
```c
#include <stdio.h>

int main() {
    int i, j, m, sum = 0;
    printf("Enter m for m*m matrix: ");
    scanf("%d", &m);

    int mat[m][m];
    printf("Enter matrix values:\n");
    for (i = 0; i < m; i++)
        for (j = 0; j < m; j++)
            scanf("%d", &mat[i][j]);

    for (i = 0; i < m; i++)
        for (j = 0; j < m; j++)
            if (i <= j)
                sum += mat[i][j];

    printf("Sum of upper triangular matrix = %d\n", sum);
    return 0;
}
```
## 26.Write a C program to remove duplicate elements from an array and print the resulting array.
```c
#include <stdio.h>

int main() {
    int n, i, j, k;
    printf("Enter array size: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter array elements:\n");
    for (i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    for (i = 0; i < n; i++) {
        for (j = i + 1; j < n; j++) {
            if (arr[i] == arr[j]) {
                for (k = j; k < n - 1; k++)
                    arr[k] = arr[k + 1];
                n--;
                j--;
            }
        }
    }

    printf("Resulting array: ");
    for (i = 0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");

    return 0;
}
```
## 27.Write a C program to print the day of the week for a given week number using switch case.
```c
#include <stdio.h>

int main() {
    int x;
    printf("Enter the week number: ");
    scanf("%d", &x);

    switch(x) {
        case 1: printf("Sunday"); break;
        case 2: printf("Monday"); break;
        case 3: printf("Tuesday"); break;
        case 4: printf("Wednesday"); break;
        case 5: printf("Thursday"); break;
        case 6: printf("Friday"); break;
        case 7: printf("Saturday"); break;
        default: printf("Invalid week number"); break;
    }

    return 0;
}
```
## 28.Write a C program to check whether a character is uppercase or lowercase.
```c
#include <stdio.h>

int main() {
    char ch;
    printf("Enter a character: ");
    scanf(" %c", &ch);

    if(ch >= 'A' && ch <= 'Z')
        printf("Uppercase\n");
    else if(ch >= 'a' && ch <= 'z')
        printf("Lowercase\n");
    else
        printf("Not an alphabet character\n");

    return 0;
}
```
## 29.Write a C program to print the number of days in a month, considering leap years for February.
```c
#include <stdio.h>

int main() {
    int month, year;
    printf("Enter month (1-12): ");
    scanf("%d", &month);

    switch(month) {
        case 1: case 3: case 5: case 7: case 8: case 10: case 12:
            printf("31 days\n"); break;
        case 4: case 6: case 9: case 11:
            printf("30 days\n"); break;
        case 2:
            printf("Enter year: ");
            scanf("%d", &year);
            if((year % 400 == 0) || (year % 4 == 0 && year % 100 != 0))
                printf("29 days\n");
            else
                printf("28 days\n");
            break;
        default:
            printf("Invalid month\n");
    }

    return 0;
}
```
## 30.Write a C program to find the maximum of two numbers using switch case.
```c
#include <stdio.h>

int main() {
    int n1, n2, x;
    printf("Enter 2 numbers: ");
    scanf("%d %d", &n1, &n2);

    x = (n1 > n2) ? 1 : 2;

    switch(x) {
        case 1: printf("Maximum is n1: %d\n", n1); break;
        case 2: printf("Maximum is n2: %d\n", n2); break;
        default: printf("Both numbers are equal\n"); break;
    }

    return 0;
}
```
## 31.Write a C program to print even numbers from 1 to 19.
```c
#include <stdio.h>

int main() {
    int i;
    printf("Even numbers:\n");
    for(i = 1; i < 20; i++) {
        if(i % 2 == 0)
            printf("%d\n", i);
    }
    return 0;
}
```
## 32.Write a C program to calculate the sum of first 100 natural numbers using a while loop.
```c
#include <stdio.h>

int main() {
    int i = 1, sum = 0;
    while(i <= 100) {
        sum += i;
        i++;
    }
    printf("Sum = %d\n", sum);
    return 0;
}
```
## 33.Write a C program to calculate the factorial of a number using a for loop.
```c
#include <stdio.h>

int main() {
    int x, fact = 1, i;
    printf("Enter a number: ");
    scanf("%d", &x);

    if(x == 0)
        fact = 1;
    else {
        for(i = 1; i <= x; i++)
            fact *= i;
    }

    printf("Factorial = %d\n", fact);
    return 0;
}
```
## 34.Write a C program to check whether a number is prime.
```c
#include <stdio.h>

int main() {
    int x, count = 0, i = 1;
    printf("Enter a number: ");
    scanf("%d", &x);

    while(i <= x / 2) {
        if(x % i == 0) count++;
        i++;
    }

    if(count > 1)
        printf("Not a prime\n");
    else
        printf("Prime\n");

    return 0;
}
```
## 35.Write a C program to calculate the sum of digits of a number.
```c
#include <stdio.h>

int main() {
    int num, r, sum = 0;
    printf("Enter a number: ");
    scanf("%d", &num);

    while(num) {
        r = num % 10;
        sum += r;
        num /= 10;
    }

    printf("Sum of digits = %d\n", sum);
    return 0;
}
```
## 36.Write a C program to print the Fibonacci series up to n terms.
```c
#include <stdio.h>

int main() {
    int a = 0, b = 1, fab, n, i;
    printf("Enter number of terms: ");
    scanf("%d", &n);

    printf("%d %d ", a, b);
    for(i = 1; i <= n-2; i++) {
        fab = a + b;
        a = b;
        b = fab;
        printf("%d ", fab);
    }
    printf("\n");
    return 0;
}
```
## 37.Write a C program to reverse a number.
```c
#include <stdio.h>

int main() {
    int num, rev = 0, r;
    printf("Enter a number: ");
    scanf("%d", &num);

    while(num) {
        r = num % 10;
        rev = rev * 10 + r;
        num /= 10;
    }

    printf("Reversed number = %d\n", rev);
    return 0;
}
```
## 38 Write a C program to find the largest element in an array.
```c
#include <stdio.h>

int main() {
    int arr[] = {9, 4, 54, 21, 6};
    int i, lar = arr[0];

    for(i = 1; i < 5; i++) {
        if(arr[i] > lar)
            lar = arr[i];
    }

    printf("Largest element = %d\n", lar);
    return 0;
}
```
## 39.Write a C program to find the smallest element in an array.
```c
#include <stdio.h>

int main() {
    int arr[6] = {9, 34, 6, 8, 19, 12};
    int i = 1, small = arr[0];

    while(i < 6) {
        if(arr[i] < small)
            small = arr[i];
        i++;
    }

    printf("Smallest element = %d\n", small);
    return 0;
}
```
## 40.Write a C program to print all elements of an array.
```c
#include <stdio.h>

int main() {
    int arr[] = {1, 2, 3, 3, 4, 5, 8, 9};
    int i;

    for(i = 0; i < 8; i++) {
        printf("%d\t", arr[i]);
    }
    printf("\n");
    return 0;
}
```
## 41.Write a C program to calculate the sum of array elements.
```c
#include <stdio.h>

int main() {
    int arr[8], i, sum = 0;

    printf("Enter 8 array elements: ");
    for(i = 0; i < 8; i++)
        scanf("%d", &arr[i]);

    for(i = 0; i < 8; i++)
        sum += arr[i];

    printf("Sum of array elements = %d\n", sum);
    return 0;
}
```
## 42.Write a C program to count the number of vowels in a string.
```c
#include <stdio.h>

int main() {
    char str[] = "hello everyone";
    char vowels[] = "aeiouAEIOU";
    int i, j, count = 0;

    for(i = 0; str[i] != '\0'; i++) {
        for(j = 0; vowels[j] != '\0'; j++) {
            if(str[i] == vowels[j])
                count++;
        }
    }

    printf("Number of vowels = %d\n", count);
    return 0;
}
```
## 43.Write a C program to count the number of words in a string.
```c
#include <stdio.h>

int main() {
    char str[100];
    int i = 0, count = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin); // safer than scanf

    while(str[i] != '\0') {
        if(str[i] == ' ' || str[i] == '\n' || str[i] == '\t')
            count++;
        i++;
    }

    printf("Number of words = %d\n", count + 1); // add 1 for last word
    return 0;
}
```
