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
## to print the current date and time
```c
#include<stdio.h>
#include<time.h>
struct datetime
{
        int day;
        int year;
        int month;
        int second;
        int hour;
        int minute;
};
int main()
{
        time_t now;
        struct tm *local;
        struct datetime dt;
        time(&now);
        local=localtime(&now);
        dt.day=local->tm_mday;
        dt.year=local->tm_year+1900;
        dt.month=local->tm_mon+1;
        dt.second=local->tm_sec;
        dt.hour=local->tm_hour;
        dt.minute=local->tm_min;
        printf("current date is--%d/%d/%d\n",dt.day,dt.month,dt.year);
        printf("current time is--%d:%d:%d\n",dt.hour,dt.minute,dt.second);
}
```
