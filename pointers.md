## 1. Write a Program to print the address of variables using the address operator.
```c
#include<stdio.h>
int main()
{
        int x;
        printf("%p ",&x);
        printf("%d",x);

}
```
## 2. Write a program to print size of pointer variables.
```c
#include<stdio.h>
int main()
{
        int *intp;
        printf("size of int pointer is %zu\n",sizeof(intp));
        char *chp;
        printf("size of char pointer is %zu\n",sizeof(chp));
        float *ftp;
        printf("size of float pointer is %zu\n",sizeof(ftp));
        double *dbp;
        printf("size of double pointer is %zu\n",sizeof(dbp));

}
```
## 3. Write a program to print size of pointer variables and size of values Dereferenced by them. 
```c
#include<stdio.h>
int main()
{
        int x=4,*intp;
        char w='a',*chp;
        float y=1.7,*ftp;
        double z=2.56, *dbp;

        intp =&x;
        chp= &w;
        ftp = &y;
        dbp = &z;

        printf("size of pointer variables & size of values dereferenced by them:\n size of int pointer is %zu & size of value is %zu \n size of char pointer is %zu & size of value is %zu \n size of float pointer is %zu & size of value is %zu \n  size of double pointer is %zu & size of value is %zu \n ",sizeof(intp),sizeof(x),sizeof(chp),sizeof(w),sizeof(ftp),sizeof(y),sizeof(dbp),sizeof(z));

}
```
## 6. Write a program to declare an integer variable a, assign it a value, then declare a pointer variable, assign it the address of a, and finally print the value of a using the pointer variable. 
```c
#include<stdio.h>
int main()
{
        int a;
        a=21;
        int *ptr;
        ptr = &a;
        printf("value of a is %d",*ptr);
}
```

## 7. Write a program to print postfix/prefix increment/decrement in a pointer variable of base type int*. 
```c
#include<stdio.h>
int main()
{
        int x=21;
        int *p;
        p=&x;
        printf("value of p: %p \n",p);
        printf("postfix increment : %p\n ",p++);
        printf("Prefix increment : %p\n",++p);
        printf("value of p: %p\n",p);
        printf("postfix decrement : %p\n ",p--);
        printf("prefix decrement : %p\n",--p);
        printf("value of p: %p",p);
return 0;
}
```
## 8.  Write a Program to print the value and address of  elements of an array using pointers notation
```c
#include<stdio.h>
int main()
{
        int arr[]={10,20,30};
        printf("value of 1st element: %d, address : %p\n",*(arr),arr);
        printf("value of 2nd element: %d, address : %p\n",*(arr+1),(arr+1));
        printf("value of 3rd element: %d, address : %p\n",*(arr+2),(arr+2));  
  return 0;
}
```

## 9. Write a program to print the value of array elements  using pointer and subscript notation.
```c
#include<stdio.h>
int main()
{
        int arr[]={10,20,30};
        for(int i=0;i<3;i++)
                printf("value of %d th element is %d\n",i,arr[i]);
//arr[i] or *(arr+i) or *(i+arr) or i[arr]
return 0;
}
```

## 14. Program to print  elements of a 2-D array by subscripting a pointer to an array variable. 
```c
#include<stdio.h>
int main()
{
        int a[2][3]={{1,2,3},{4,5,6}};
        printf("array is: \n");
        for(int i=0;i<2;i++)
        {
                for(int j=0;j<3;j++)
                        printf("%d",a[i][j]);
                printf("\n");
        }

        int (*ptr)[3]=a;
        for(int i=0;i<2;i++)
                for(int j=0;j<3;j++)
                        printf("value of %dth row, %dth col element is: %d\n",i,j,*(*(ptr+i)+j));
// *(*(ptr+i)+j)  is same as ptr[i][j]  which gives values as o/p.
// ptr+i  or ptr
return 0;
}
```

## 15. Program to print  elements of a 3-D array using    pointer notation.
```c
#include<stdio.h>
int main()
{
        int a[2][3][4]={
                {
                        { 1, 2, 3, 4},
                        { 5, 6, 7, 8},
                        { 9, 10, 11, 12}
                },
                {
                        { 13, 14, 15, 16},
                        { 17, 18, 19, 20},
                        { 21, 22, 23, 24}
                }
        };

        for(int i=0;i<2;i++){
                for(int j=0;j<3;j++){
                        for(int k=0;k<4;k++){
                                printf("%d ",a[i][j][k]);
                        }printf("\n");
                }printf("\n");
        }

        for(int i=0;i<2;i++)
                for(int j=0;j<3;j++)
                        for(int k=0;k<4;k++)
                                printf("value of a[%d][%d][%d] is %d\n",i,j,k,*(*(*(a+i)+j)+k));
 return 0;
}
```

## 16. Write a  simple program for call by value.
```c
#include<stdio.h>
int modify(int a,int b)
{
        a++;
        b--;
}

int main()
{
        int a=10,b=8;
        printf("before modifying a is %d, b is %d\n",a,b);
        modify(a,b);
        printf("after modifying a is %d, b is %d\n",a,b);
}
```

## 17. Write a simple program for call by reference.
```c
#include<stdio.h>
int modify(int *xptr, int *yptr)
{
        (*xptr)++;
        (*yptr)--;
}

int main()
{
        int a=10,b=8;
        printf("before modifying a is %d, b is %d\n",a,b);
        modify(&a,&b);
        printf("after modifying a is %d, b is %d\n",a,b);
        return 0;
}
```


## 18. Program to return more than one value from a function using call by    reference.
```
#include<stdio.h>
void func(int x, int y,int *ps,int *pd,int *pm)
{
        *ps=x+y;
        *pd=x-y;
        *pm=x*y;

}

int main()
{
        int a, b,sum ,diff,mul;
        a=7;b=9;
        printf("value of a is %d, b is %d\n",a,b);
        func(a,b,&sum,&diff,&mul);
        printf(" sum is %d\n difference is %d\n product id %d\n",sum,diff,mul);
        return 0;
}
```

## 19. Write a program to pass a 1D array to a function.
```c
#include<stdio.h>
int func(int a[]);
int main()
{
        int i,arr[5]={1,2,3,4,5};
        printf("array is:\n");
        for(i=0;i<5;i++)
                printf("%d ",arr[i]);
        printf("\n");
        func(arr);
        printf("inside main() after func()\n");
        for(i=0;i<5;i++)                                                    printf("%d ",arr[i]);                               printf("\n");
        return 0;
}
int func(int a[])
{
        int i;
        printf("inside func():\n");
        for(i=0;i<5;i++)
                printf("%d ",a[i]+=2);
        printf("\n");

}
```

## 20. Create a function that swaps two numbers using   pointers.
```c
#include<stdio.h>
int swap(int *pa,int *pb)
{
        int temp;
        temp= *pa;
        *pa = *pb;
        *pb =temp;
}

int main()
{
        int a=10,b=21;
        printf("value of a is %d ,b is %d\n",a,b);
        swap(&a,&b);
        printf("After swapping value of a is %d , b is %d\n",a,b);
        return 0;
}
```
## 21. Implement a function that returns the length of a string using pointers 
```c
#include<stdio.h>
int len(char *str);
int main()
{
        char str[30];
        printf("enter string: ");
        fgets(str,30,stdin);
        int length=len(str);
        printf("length of the string is %d",length);
}
int len(char *st)
{
        int i=0;
        while(*st != '\0')
        {
                i++;
                st++;
        }
        return i;
}

```
## 22. Write a program to find the maximum and minimum elements in an array using pointers.
```c
#include<stdio.h>
int larandsma(int *p,int n,int *max,int *min)
{
        int i;
        *min=*p;
        *max=*p;
        for(i=1;i<n;i++){
                if(*(p+i)<*min)
                        *min=*(p+i);
                if(*(p+i)>*max)
                        *max=*(p+i);
        }
}
int main()
{
        int arr[]={8,2,58,83,5,46,33,72,21,10};
        int min,max;
        int size = sizeof(arr) / sizeof(arr[0]);
        larandsma(arr,size,&max,&min);
        printf("largest : %d, smallest : %d\n",max,min);
        return 0;
}

```
## 23. Develop a function to reverse a string in place using pointers. 
```c
#include<stdio.h>
#include<string.h>
void reverse(char *st);
int main()
{
        char str[20];
        printf("enter string: ");
        fgets(str,20,stdin);
        reverse(str);
        printf("string after reverse: %s\n",str);
        return 0;
}
void reverse(char *st)
{
        int i,j;
        char temp;
        for(i=0,j=strlen(st)-1;i<j;i++,j--)
        {
                temp=*(st+i);
                *(st+i)=*(st+j);
                *(st+j)= temp;
        }
}
```
## 24. Write a program that calculates the sum of all elements in an integer array using pointer arithmetic.
```c
#include<stdio.h>
int main()
{
        int n,i;
        printf("enter n: ");
        scanf("%d",&n);
        int arr[n];
        for(i=0;i<n;i++)
                scanf("%d",&arr[i]);
        int sum=0;
        i=0;
        while(i<n)
        {
                sum=*(arr+i)+sum;
                i++;
        }
        printf("sum is: %d",sum);
        return 0;
}

```
## 25. Implement a function to copy one string into another using pointers, without using any standard library functions 
```c
#include<stdio.h>
int main()
{
        char str1[20],str2[20];
        printf("enter string: ");
        fgets(str1,20,stdin);
        fgets(str2,20,stdin);
        printf("before copying: str1: %s str2: %s",str1,str2);
        for(int i=0;i<20;i++)
        {
                *(str1+i) = *(str2+i);
        }
        printf("after copying: str1: %s str2: %s",str1,str2);
        return 0;
}
```
## 26.  Write a program to compare two strings lexicographically (like the strcmp function) using pointers.
```c
#include<stdio.h>
int main()
{
        char str1[20],str2[20];
        int flag,i=0;
        printf("enter strings:\n");
        fgets(str1,20,stdin);
        fgets(str2,20,stdin);
        while(i<20)
        {
                if(*(str1+i) == *(str2+i))
                        flag=0;
                else if(*(str1+i) > *(str2+i))
                {
                        flag=1;
                        break;
                }
                else
                {
                        flag= -1;
                        break;
                }
                i++;
        }
        if(flag==0)
                printf("strings are same \n");
        else
                printf("strings are not same.\n");
        return 0;
}
```
```
## 27.  Develop a function to reverse an array of integers in place using pointers. 
```c
#include<stdio.h>
int reverse(int n,int arr[n]);
int main()
{
        int n;
        printf("enter n: ");
        scanf("%d",&n);
        int arr[n];
        for(int i=0;i<n;i++)
                scanf("%d",&arr[i]);
        reverse(n,arr);
        printf("reversed array is: ");
        for(int i=0;i<n;i++)
                printf("%d ",arr[i]);
        return 0;
}
int reverse(int n,int *arr)
{
        int i,j,temp;
        for(i=0,j= n-1;i<j;i++,j--)
        {
                temp = *(arr+i);
                *(arr+i) = *(arr+j);
                *(arr+j) = temp;
        }
}
```

## 28.  Write a program to find the largest element using Dynamic Memory Allocation.
```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
        int *p,n,i;
        printf("enter no. of elements: ");
        scanf("%d",&n);
        p=(int *)malloc(n*sizeof(int));
        if(p==NULL)
        {
                printf("memory not avalable.\n");
                exit(1);
        }
        printf("enter elements:\n");
        for(i=0;i<n;i++)
        {
                scanf("%d",&p[i]);
        }
        int lar=p[0];
        for(i=1;i<n;i++)
        {
                if(p[i]>lar)
                {
                        lar=p[i];
                }
        }
        printf("largest element is %d",lar);
        return 0;
}
```
## 29. Write a program in C to calculate the length of a string using a pointer.
```c
#include<stdio.h>
int main()
{
        char str[100];
        int len=0;char *ptr;
        printf("enter string: ");
        fgets(str,100,stdin);
        ptr=str;
        while(*ptr !='\0')
        {
                len++;
                ptr++;
        }
        printf("length of string is %d\n",len);
return 0;
}

```
## 30. Write a program  to swap elements using call by reference. 
```c
#include<stdio.h>
int swap(int *x,int *y);
int main()
{
        int a,b;
        printf("enter a, b values: ");
        scanf("%d%d",&a ,&b);
        swap(&a,&b);
        printf("swapped values a=%d, b=%d",a,b);
        return 0;
}
int swap(int *x,int *y)
{
        int temp=*x;
        *x = *y;
        *y = temp;
}
```
## 31. Write a program to find the factorial of a given number using pointers. 
```c
#include<stdio.h>
void findFactorial(int num, int *fact)
{
        *fact = 1;
        for (int i = 1; i <= num; i++) {
                *fact *= i;
    }
}
int main()
{
        int n,res;
        printf("enter n value: ");
        scanf("%d",&n);
        findFactorial(n,&res);
        printf("factorial of %d is %d",n,res);
        return 0;
}
```

## 32. Write a program to count the number of vowels and consonants in a string using a pointer.
```c
#include<stdio.h>
#include<ctype.h>
int main()
{
        char str[100];
        printf("enter string: ");
        fgets(str,100,stdin);
        int vowel=0,cons=0;
        char *p;
        p = str;
        while(*p != '\0')
        {
                if(isalpha(*p))
                {
                        char ch=tolower(*p);
                        if(ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u')
                                vowel++;
                        else
                                cons++;
                }
                *p++;
        }
        printf("In the string, vowels: %d, consonants: %d",vowel,cons);
        return 0;
}
```

## 33.  Write a program  to sort an array using a pointer
```c
#include<stdio.h>
int main()
{
        int n;
        printf("enter array size: ");
        scanf("%d",&n);
        int arr[n];
        for(int i=0;i<n;i++)
                scanf("%d",&arr[i]);
        int *p;
        p=arr;
        for(int i=0;i<n-1;i++)
        {
                for(int j=i+1;j<n;j++)
                {
                        if(*(p+j) >*(p+i))
                        {
                                int temp= *(p+i);
                                *(p+i) = *(p+j);
                                *(p+j) = temp;
                        }
                }
        }
        printf("sorted array is: ");
        for(int i=0;i<n;i++)
                printf("%d ",arr[i]);
        return 0;
}
```
## 34. Write a  program to demonstrate how a function returns a pointer.
```c
#include<stdio.h>
int* findLarger(int *a, int *b) {
    if (*a > *b)
        return a;
    else
        return b;
}

int main()
{
    int x = 10, y = 20;
    int *larger = findLarger(&x, &y);
    printf("The larger number is: %d\n", *larger);
    return 0;
}
```

## 35. Write a program  to compute the sum of all elements in an array using pointers 
```c
#include<stdio.h>
int main()
{
        int n,i;
        printf("enter array size: ");
        scanf("%d",&n);
        printf("enter elements:");
        int arr[n];
        for(i=0;i<n;i++)
                scanf("%d",&arr[i]);

        int sum=0,*ptr;
ptr=arr;
        for(i=0;i<n;i++)
        {
                sum=sum+(*(ptr+i));
        }
        printf("sum is %d",sum);
        return 0;

}
```
## 36. Write a program  to print the elements of an array in reverse order.
```c
#include<stdio.h>
int main()
{
        int n,i;
        printf("enter size : ");
        scanf("%d",&n);
        int a[n];
        printf("enter ele: ");
        for(i=0;i<n;i++)
                scanf("%d",&a[i]);
        int *ptr;
        ptr=a;
        printf("reverse order: \n");
        for(i= n-1;i>=0;i--)
                printf("%d ",*(ptr+i));
        return 0;
}
```
## 37. Write a program to show a pointer to an array whose contents are pointers to structures. 
```c
#include <stdio.h>
#include <stdlib.h>

struct Student {
    int roll;
    char name[20];
};                                                                                                                      int main() {                                                    // Create structure pointers                                struct Student *s1 = (struct Student *)malloc(sizeof(struct Student));
    struct Student *s2 = (struct Student *)malloc(sizeof(struct Student));

    // Initialize structure data
    s1->roll = 101;
    snprintf(s1->name, sizeof(s1->name), "Alice");

    s2->roll = 102;
    snprintf(s2->name, sizeof(s2->name), "Bob");

    // Array of pointers to structures
    struct Student *arr[2];
    arr[0] = s1;
    arr[1] = s2;
    
    // Pointer to the array
    struct Student **ptr = arr;

    // Accessing data using pointer to array
    for (int i = 0; i < 2; i++) {
        printf("Student %d: Roll = %d, Name = %s\n", i + 1, ptr[i]->roll, ptr[i]->name);
    }

    // Free memory
    free(s1);
    free(s2);

    return 0;
}
```
## 39. Logic to search an element in an array using pointers. 
```c
#include<stdio.h>
int main()
{
        int n,i;
        printf("enter size: ");
        scanf("%d",&n);
        int a[n];
        printf("enter ele: ");
        for(i=0;i<n;i++)
                scanf("%d",&a[i]);
        int *p,x,flag=0;
        printf("enter ele to search: ");
        scanf("%d",&x);
        p=a;
        for(i=0;i<n;i++)
        {
                if((*(p+i)) ==x)
                {
                        printf("found\n");
                        flag=1;
                }
        }
        if(flag==0)
                printf("not found\n");
}
```

## 40. Write a  program to add two matrices using pointers.
```c
#include<stdio.h>
int main()
{
        int i,j;
        int a[3][3],b[3][3];
        int s[3][3];
        printf("Enter elements of a-Matrix :\n");
        for(i=0;i<3;i++)
        {
                for(j=0;j<3;j++)
                {
                        scanf("%d",(*(a+i)+j));
                }
        }

        printf("Enter elements of b-Matrix :\n");
        for(i=0;i<3;i++)
        {
                for(j=0;j<3;j++)
                {
                        scanf("%d",(*(b+i)+j));
                }
        }

        printf("sum of matrices:\n");
        for(i=0;i<3;i++)
        {
                for(j=0;j<3;j++)
                {
*(*(s+i)+j) = *(*(a+i)+j) + *(*(b+i)+j);
                        printf("%d\t ",*(*(s+i)+j));
                }
                printf("\n");
        }

        return 0;
}
```

## 41. Write a program to multiply two matrix using pointers
```c
#include<stdio.h>
int main()
{
        int a[3][3],b[3][3];
        int m[3][3];
        int i,j,sum;

        printf("enter a-matrix elements:\n");
        for(i=0;i<3;i++) {
                for(j=0;j<3;j++) {
                        scanf("%d",*(a+i)+j);
                }
        }

        printf("enter b- matrix elements:\n");
        for(i=0;i<3;i++) {
                for(j=0;j<3;j++) {
                        scanf("%d",*(b+i)+j);
                }
        }

        for(i=0;i<3;i++) {
                for(j=0;j<3;j++) {
                        for(int k=0;k<3;k++) {
                                sum = sum + ( (*(*(a+i)+k)) * (*(*(b+k)+j)) );
                        }
                        *(*(m+i)+j) = sum;
                        sum=0;
}
        }

        printf("multiplication matrix is: \n");
        for(i=0;i<3;i++) {
                for(j=0;j<3;j++) {
                        printf("%d\t",*(*(m+i)+j));
                }
                printf("\n");
        }

        return 0;
}

```
## 44. Program to access dynamically allocated memory as a 1d array
```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
        int i,n;
        printf("array size: ");
        scanf("%d",&n);
        int *p;
        p=(int *)malloc(n*sizeof(int));
        if(p==NULL)
        {
                printf("memory not available\n");
                exit(0);
        }
        printf("enter eleemnts:\n");
        for(i=0;i<n;i++)
        {
                scanf("%d",&p[i]);
        }
        printf("array is : ");
        for(i=0;i<n;i++)
        {
                printf("%d ",p[i]);
        }
        return 0;
}
```

## 45. Program to access dynamically allocate a 2-D array using a pointer to an array
```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
        int rows,i,j;
        printf("enter rows value: ");
        scanf("%d",&rows);
        int (*p)[3];
        p=(int (*)[3])malloc(rows*3* sizeof(int));
        if(p==NULL)
        {
                printf("memory not available\n");
                exit(0);
        }
        printf("enter elements: \n");
        for(i=0;i<rows;i++){
                for(j=0;j<3;j++){
                        scanf("%d",(*(p+i)+j));
                }
        }

        printf("the array is:\n");
        for(i=0;i<rows;i++){
                for(j=0;j<3;j++){
                        printf("%d ",*(*(p+i)+j));
                }
                printf("\n");
        }
        free(p);
 return 0;
}
```

## 46. Write a program to print array of pointer 
```c
#include<stdio.h>
int main()
{
        int n,i,j;
        int var1=10,var2=20,var3=30;
        int *arr[3];
        arr[0]=&var1;
        arr[1]=&var2;
        arr[2]=&var3;
        printf("array of pointers:\n");
        for(i=0;i<3;i++)
                printf("value of var%d: %d\taddress: %p\n",i+1,*arr[i],arr[i]);
        return 0;
}
```
## 47. Write a program to print pointer to an array
```c
#include<stdio.h>
int main()
{
        int p[3]={12,21,24};
        int (*ptr)[3];
ptr = &p;
        for(int i=0;i<3;i++)
        {
                printf("%4d",(*ptr)[i]);
        }
        return 0;
}
```

## 48. Program to dynamically allocate a 2-D array using array of pointers
```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
        int i,j,cols;
        printf("enter cols: ");
        scanf("%d",&cols);
        int *a[3];
        for(i=0;i<3;i++)
                a[i]=(int *)malloc(cols*sizeof(int));
        printf("enter elements:\n");
        for(i=0;i<3;i++) {
                for(j=0;j<cols;j++) {
                        scanf("%d",&a[i][j]);
                }
        }
        printf("the matrix is: \n");
        for(i=0;i<3;i++) {
                for(j=0;j<cols;j++) {
                        printf("%5d",a[i][j]);
                }
                printf("\n");
        }
        for(i=0;i<3;i++)
                free(a[i]);
        return 0;
}
```
## 48. Program to dynamically allocate a 2-D array using array of pointers
```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
        int i,j,cols;
        printf("enter cols: ");
        scanf("%d",&cols);
        int *a[3];
        for(i=0;i<3;i++)
                a[i]=(int *)malloc(cols*sizeof(int));
        printf("enter elements:\n");
        for(i=0;i<3;i++) {
                for(j=0;j<cols;j++) {
                        scanf("%d",&a[i][j]);
                }
        }
        printf("the matrix is: \n");
        for(i=0;i<3;i++) {
                for(j=0;j<cols;j++) {
                        printf("%5d",a[i][j]);
                }
                printf("\n");
        }
        for(i=0;i<3;i++)
                free(a[i]);
        return 0;
}
```

## 49. Program to invoke a function using function pointer
```c
#include<stdio.h>
int mul(int, int);
int main()
{
        int (*fp)(int, int);
        int result,a,b;
        scanf("%d%d",&a,&b);
        fp=mul;
        result=(*fp)(a,b);
        printf("product of a,b is %d\n",result);
        return 0;

}
int mul(int x,int y)
{
        return x*y;
}
```

## 50. Program to send a function ‘s address as an argument to other function
```c
#include<stdio.h>
int max(int,int);
int large(int ,int,int (*ptr)(int, int));
int main()
{
        int a,b;
        scanf("%d%d",&a,&b);

        int lar=large(a,b,max);
        printf(" maximum number is %d",lar);
}
int max(int x,int y)
{
        if(x>y)
                return x;
        else
                return y;
}
int large(int u,int v,int (*ptr)(int, int))
{
        return ptr(u,v);
}

```
