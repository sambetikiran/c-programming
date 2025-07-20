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
