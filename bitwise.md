## 1. program to find given number is even or odd using bitwise operator
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number:");
        scanf("%d",&num);
        if( num & 1)
        {
                printf("odd nummber\n");
        }
        else
        {
                printf("even\n");
        }
}
```
## 2.program to write an absolute number.
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number");
        scanf("%d",&num);
        int abs=(num^(num>>31))-(num>>31);
        printf("%d",abs);
}

```
## 3. program to perform bitwise operations XOR,OR,AND
```c
#include<stdio.h>
int main()
{
        int a,b;
        printf("enter the number");
        scanf("%d %d",&a,&b);
        int xor=a^b;
        int or=a|b;
        int and=a&b;
        printf("%d\n",xor);
        printf("%d\n",or);
        printf("%d\n",and);
}
```
## 4. program to perform left and right shift operations
```c
#include<stdio.h>
int main()
{
        int a,b;
        printf("enter the two numbers");
        scanf("%d %d",&a,&b);
        int right =a>>b;   \\divisible by 2
        int left=a<<b;     \\multiple by 2
        printf("right=%d",right);
        printf("left=%d",left);
}
```
## 5 find missing number
```c
#include<stdio.h>
int main()
{
        int arr[6];
        int n=6;
        printf("enter the array value");
        for( int i=0;i<n-1;i++)
        {
                scanf("%d",&arr[i]);
        }
        int all=0,part=0;
        for( int i=1;i<=n;i++)
        {
                all^=i;
        }
        for(int j=0;j<n-1;j++)
        {
                part^=arr[j];
        }
        int missing=all^part;
        printf("%d\n",missing);
}
```
## Count the number of set bits (1s) in a number.
```c
#include<stdio.h>
int main()
{
        int a;
        printf("enter the number");
        scanf("%d",&a);
        int count=0;
        while(a>0)
        {
                if(a&1)
                {
                        count++;
                }
                a=a>>1;
        }
        printf("%d\n",count);
}
```
