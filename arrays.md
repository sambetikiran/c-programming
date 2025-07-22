## 1.Array delete specific position
```c
#include<stdio.h>
void delete(int[],int,int);
int main()
{
        int num;
        printf("number");
        scanf("%d",&num);
        int arr[num];
        for(int i=0;i<num;i++)
        {
                scanf("%d",&arr[i]);
        }
        int pos;
        printf("enter the postion");
        scanf("%d",&pos);
        delete(arr,num,pos);
}
void delete(int arr[],int num,int pos)
{
        for(int i=pos-1;i<num;i++)
        {
                arr[i]=arr[i+1];
        }
        num--;
        for(int j=0;j<num;j++)
        {
                printf("%d",arr[j]);
        }
}
```
## 2.program to rotate an array to left by  using swaping
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter  the number:");
        scanf("%d",&num);
        int arr[num];
        for(int i=0;i<num;i++)
        {
                scanf("%d",&arr[i]);
        }
        for(int i=0;i<num-1;i++)
        {
                int temp=arr[i];
                arr[i]=arr[i+1];
                arr[i+1]=temp;
        }
        for(int i=0;i<num;i++)
        {
                printf("%d\t",arr[i]);
        }
}
```
## 3.program to rotate an array to left by  using shifting
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number:");
        scanf("%d",&num);
        int arr[num];
        for(int i=0;i<num;i++)
        {
                scanf("%d",&arr[i]);
        }
        int temp=arr[0];
        for(int i=0;i<num-1;i++)
        {
                arr[i]=arr[i+1];
        }
        arr[num-1]=temp;
        for(int i=0;i<num;i++)
        {
                printf("%d\t",arr[i]);
        }
        printf("\n");
}
```
## 4.program to rotate an array to right shifting
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
        int temp=arr[num-1];
        for(int i=num-1;i>0;i--)
        {
                arr[i]=arr[i-1];
        }
        arr[0]=temp;
        for(int i=0;i<num;i++)
        {
                printf("%d\t",arr[i]);
        }
}
```
## 4.program to rotate left to an array of K positions
```c
#include<stdio.h>
int main()
{
        int num=5;
        int arr[5]={1,2,3,4,5};
        int k=3;
        for(int i=0;i<k;i++)
        {
                int temp=arr[0];
                for(int j=0;j<num-1;j++)
                {
                        arr[j]=arr[j+1];
                }
                arr[num-1]=temp;
        }
        for(int i=0;i<num;i++)
        {
                printf("%d",arr[i]);
        }
}
```
