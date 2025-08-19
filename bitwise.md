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
