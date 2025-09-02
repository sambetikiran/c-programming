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
