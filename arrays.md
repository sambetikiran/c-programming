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
## 10.Write a program to delete a position in an array
```c
#include<stdio.h>
void delete_pos(int [],int,int  );
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
        printf("enter the postion");
        int pos;
        scanf("%d",&pos);
        delete_pos(arr,num,pos);
}
void delete_pos(int arr[],int num,int pos)
{
        for(int i=pos;i<num;i++)
        {
                arr[i]=arr[i+1];
        }
        num--;
        for(int i=0;i<num;i++)
        {
                printf("%d\t",arr[i]);
        }
}
```
## 11.write a program to print sum of elements in 2D array
```c
#include<stdio.h>
int sum_matrix(int row,int col,int arr[row][col])
{
        int sum=0;
        for(int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
                {
                        sum=sum+arr[i][j];
                        printf("%d ",sum);
                }
        }
        return sum;
}
int main()
{
        int row;
        printf("enter the row");
        scanf("%d",&row);
        int col;
        printf("enter the column");
        scanf("%d",&col);
        int arr[row][col];
        for(int i=0;i<row;i++)
        {
                for(int j=0;j<col;j++)
                {
                        scanf("%d",&arr[i][j]);
                }
        }
        int sumi=sum_matrix(row,col,arr);
        printf("%d\n",sumi);
}
```
## 12. program to find sum of two matrices
```c
#include<stdio.h>
void two_sum(int row,int col,int first[row][col],int sec[row][col])
{
        int sum[row][col];
        for(int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
                {
                        sum[i][j]=first[i][j]+sec[i][j];
                }
        }
        for(int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
                {
                        printf("%d\t",sum[i][j]);
                }
                printf("\n");
        }
}
int main()
{
        int row,col;
        printf("enter the row");
        scanf("%d",&row);
        printf("enter the column");
        scanf("%d",&col);
        int first[row][col];
        for(int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
                {
                        scanf("%d",&first[i][j]);
                }
        }
        printf("enter the second ");
        int sec[row][col];
        for(int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
                {
                        scanf("%d",&sec[i][j]);
                }
        }
        two_sum(row,col,first,sec);
}
```
## 13.program to transpose matrix using two arrays
```c
#include<stdio.h>
#define max 100
int rotate(int,int,int first[][100],int sec[][100]);
int main()
{
        int row,col;
        printf("enter the row");
        scanf("%d",&row);
        printf("enter the col");
        scanf("%d",&col);
        int first[row][col],sec[row][col];
        for( int i=0;i<row;i++)
        {
                for(int j=0;j<col;j++)
                {
                        scanf("%d",&first[i][j]);
                }
        }
        rotate(row,col,first,sec);
        for( int i=0;i<row;i++)
        {
                for(int j=0;j<col;j++)
                {
                        printf("%d\t",sec[i][j]);
                }
                printf("\n");
        }

}
int  rotate(int row,int col,int first[row][col],int sec[row][col])
{
        for(int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
                {
                        sec[j][i]=first[i][j];
                }
        }
        return sec;
}
```
## 14.program to print transpose matrix within same array
```c
include<stdio.h>
#define max 100
int rotate(int,int,int first[][100]);
int main()
{
        int row,col;
        printf("enter the row");
        scanf("%d",&row);
        printf("enter the col");
        scanf("%d",&col);
        int first[row][col];
        for( int i=0;i<row;i++)
        {
                for(int j=0;j<col;j++)
                {
                        scanf("%d",&first[i][j]);
                }
        }
        rotate(row,col,first);
        for( int i=0;i<row;i++)
        {
                for(int j=0;j<col;j++)
                {
                        printf("%d\t",first[i][j]);
                }
                printf("\n");
        }

}
int  rotate(int row,int col,int first[row][col])
{
        for(int i=0;i<row;i++)
        {
                for( int j=i+1;j<col;j++)
                {
                        int temp=first[i][j];
                        first[i][j]=first[j][i];
                        first[j][i]=temp;
                }
        }
}
```
## 15 program to reverse an array using recurrsion function
```c
#include <stdio.h>
void reverse(int arr[], int i, int j)
{
    if (i >= j)
        return;
    int temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
    reverse(arr, i + 1, j - 1);
}

int main()
{
    int num;
    printf("enter number:");
    scanf("%d", &num);
    int arr[num];
    printf("enter the array:");
    for (int i = 0; i < num; i++)
    {
        scanf("%d", &arr[i]);
    }
    reverse(arr, 0, num - 1);
    for (int i = 0; i < num; i++)
    {
        printf("%d ", arr[i]);
    }
    return 0;
}
```
## 16.program to rotate matrix 90 clockwise 
```c
#include<stdio.h>
#define max 100
int rotate_clock(int ,int,int [][max]);
int main()
{
        int row;
        printf("enter the row");
        scanf("%d",&row);
        int col;
        printf("enter the col");
        scanf("%d",&col);
        int first[row][col];
        for( int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
        {
                        scanf("%d",&first[i][j]);
                }
        }
        rotate_clock(row,col,first);
        for( int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
                {
                        printf("%d\t",first[i][j]);
                }
                printf("\n");
        }
}
int rotate_clock(int row,int col,int first[row][col])
{
        for(int i=0;i<row;i++)
        {
                for( int j=i+1;j<col;j++)
                {
                        int temp=first[i][j];
                        first[i][j]=first[j][i];
                        first[j][i]=temp;
                }
        }
        for( int i=0;i<row;i++)
        {
                for( int j=0;j<col;j++)
                {
                        printf("%d\t",first[i][j]);
                }
                printf("\n");
        }

        for( int i=0;i<row;i++)
        {
                for( int j=0;j<col/2;j++)
                {
                        int temp=first[i][j];
                        first[i][j]=first[i][col-j-1];
                        first[i][col-j-1]=temp;
                }
        }
}
```
## 17. find given string is symmetric or not 
```c
#include<stdio.h>
#define max 100
int sym(int num,int arr[num][num])
{
        int found=0;
        for( int i=0;i<num;i++)
        {
                for( int j=i+1;j<num;j++)
                {
                        if( arr[i][j]!=arr[j][i])
                        {
                                return 0;
                        }
                }
        }
        return 1;
}


int main()
{
        int num;
        printf("enter the row");
        scanf("%d",&num);
        int arr[num][num];
        for(int i=0;i<num;i++)
        {
                for( int j=0;j<num;j++)
                {
                        scanf("%d",&arr[i][j]);
                }
        }
        for(int i=0;i<num;i++)
        {
                for( int j=0;j<num;j++)
                {
                        printf("%d\t",arr[i][j]);
                }
                printf("\n");
        }
        int s=sym(num,arr);
        if(s==1)
        {
                printf("it is a symtric");
        }
        else
        {
                printf("it is not symmetric");
        }
}
```
