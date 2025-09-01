## 1.program for single student data
```c
#include<stdio.h>
#include<string.h>
struct stud
{
        char name[10];
        int roll_number;
        float marks;
};
int main()
{
        struct stud list;
        strcpy(list.name,"kiran");
        list.roll_number=12;
        list.marks=23.5;
        printf("%s\n",list.name);
        printf("%d\n",list.roll_number);
        printf("%f\n",list.marks);
}
```
