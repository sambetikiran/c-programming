## 1.program to insert nodes in linked list 
```c
#include<stdio.h>
#include<stdlib.h>
struct node
{
        int data;
        struct node *nxt;
};
struct node *phead=NULL;
void addnode(int d)
{
        struct node *ptrav,*pnew;
        pnew=(struct node *)malloc(sizeof(struct node));
        if(pnew==NULL)
        {
                printf("malloc error");
                return;
        }
        pnew->data=d;
        pnew->nxt=NULL;
        if(phead==NULL)
        {
                phead=pnew;
        }
        else
        {
                ptrav=phead;
                while(ptrav->nxt!=NULL)
                {
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
                return;
        }
}
void display()
{
        struct node *ptrav;
        ptrav=phead;
        if(ptrav==NULL)
        {
                printf("the list is empty \n");
        }
        else
        {
                while(ptrav!=NULL)
                {
                        printf("%d->",ptrav->data);
                        ptrav=ptrav->nxt;
                }
                return;
        }
}
int main()
{
        int node,d;
        printf("enter the node");
        scanf("%d",&node);
        for(int i=0;i<node;i++)
        {
                printf("node:");
                scanf("%d",&d);
                addnode(d);
        }
        display();
}
```
