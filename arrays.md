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
## 4.program to rotate left an array of K positions
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
## 5.program to rotate right an array of K positions
```c
#include<stdio.h>
int main()
{
        int n=5;
        int arr[5]={1,2,3,4,5};
        int k=3;
        for(int i=0;i<k;i++)
        {
                int temp=arr[n-1];
                for( int j=n-1;j>0;j--)
                {
                        arr[j]=arr[j-1];
                }
                arr[0]=temp;
        }
        for(int i=0;i<n;i++)
        {
                printf("%d",arr[i]);
        }
}
```
## 6.write a program to print the missing number in sorted array
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
        int flag;
        for(int i=0;i<num;i++)
        {
                flag=0;
                for(int j=0;j<num;j++)
                {
                        if(arr[j]==i)
                        {
                                //printf("%d\t",arr[i]);
                                flag=1;
                                break;
                        }
                }
                if(flag==0)
                {
                        printf("%d\t",i);
                }
        }
        printf("\n");
}
```
## 7.write a program print maximum sum of subarray k=4 using windowsliding method
```c
#include<stdio.h>
int main()
{
        int num;
        printf("enter the number:");
        scanf("%d",&num);
        int k=4;
        int arr[num];
        printf("enter the array elements:");
        for(int i=0;i<num;i++)
        {
                scanf("%d",&arr[i]);
        }
        int sum=0;
        for(int i=0;i<k;i++)
        {
                sum=sum+arr[i];
        }
        int ws=sum;
        int max=sum,max1;
        for(int i=k;i<num;i++)
        {
                ws=ws-arr[i-k]+arr[i];
                max1=ws;
                if(max>max1)
                {
                        max1=max;
                }
        }
        printf("maximum sum=%d\n",max1);
}
```
## 8.write a program to remove duplicate element in an array
```c
#include<stdio.h>
int duplicate(int[],int);
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
        int count=duplicate(arr,num);
        printf("%d\n",count);
}
int duplicate(int arr[],int num)
{
        int count=0;
        or(int i=0;i<num;i++)
        {
                for(int j=i+1;j<num;j++)
                {
                        if(arr[i]==arr[j])
                        {
                                count++;
                        }
                }
        }
        return count;
}
```
## 9.Convert a square matrix into its 2D prefix sum matrix and print the result
```c
#include<stdio.h>
#define size 100
void sum(int[][100],int);
int main()
{
        int num;
        printf("enter the number");
        scanf("%d",&num);
        int arr[size][size];
        for(int i=0;i<num;i++)
        {
                for(int j=0;j<num;j++)
                {
                        scanf("%d",&arr[i][j]);
                }
        }
        sum(arr,num);
}
void sum(int arr[][100],int num)
{
        int sum;
        for(int i=0;i<num;i++)
        {
                sum=0;
                for(int j=0;j<num;j++)
                {
                        sum+=arr[i][j];
                        arr[i][j]=sum;
                        printf("%d1\t",arr[i][j]);
                }
        }
        printf("\n");
        int k=0,r=0;
        for(int i=0;i<num;i++)
        {
                sum=0;
                for(int j=0;j<num;j++)
                {
                        sum+=arr[j][i];
                        arr[k++][r++]=sum;
                        printf("%d2\t",arr[k][r]);

                }
        }
        printf("\n");
        printf("\n");
        for(int i=0;i<num;i++)
        {
                for(int j=0;j<num;j++)
                {
                        printf("%d3\t",arr[i][j]);
                }
        }
        printf("\n");
}
```
