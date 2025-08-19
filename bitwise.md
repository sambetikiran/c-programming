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
