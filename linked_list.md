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
## 2.program to delete last node in given list 
```c
void deletelastnode()
{
    struct node *ptrav, *prev;
    ptrav = phead;

    if (ptrav == NULL)
    {
        printf("The list is empty\n");
        return;
    }
    else if (ptrav->nxt == NULL)
    {
        // Only one node in the list
        free(ptrav);
        phead = NULL;
    }
    else
    {
        // More than one node
        while (ptrav->nxt != NULL)
        {
            prev = ptrav;
            ptrav = ptrav->nxt;
        }
        prev->nxt = NULL;
        free(ptrav);
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
        deletelastnode();*/
        display();
        return 0;
}
```
## 3.program to add node in middle in the list
```c
#include<stdio.h>
#include<stdlib.h>
struct node
{
        int data;
        struct node *nxt;
};
struct node *phead=NULL;
void create(int d)
{
        struct node *ptrav, *pnew;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL)
        {
                printf("malloc error");
        }
        pnew->data=d;
        pnew->nxt=NULL;
        if(phead==NULL)
        {
                phead=pnew;
                printf("node aded");
        }
        else
        {
                ptrav=phead;
                while(ptrav->nxt!=NULL)
                {
                        ptrav=ptrav->nxt;
                }
                ptrav->nxt=pnew;
        }
}
void display()
{
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL)
        {
                printf("%d\t",ptrav->data);
                ptrav=ptrav->nxt;
        }
        printf("\n");

}
void insert_node(int n,struct node *ptemp)
{
        struct node *ptrav,*pnew,*prev=NULL;
        pnew=(struct node*)malloc(sizeof(struct  node));
        if(pnew==NULL)
        {
                printf("malloc error:");
                return;
        }
        pnew->data=n;
        pnew->nxt=NULL;
        ptrav=phead;
        while(ptrav->nxt!=NULL)
        {
                prev=ptrav;
                if(ptrav==ptemp)
                {
                        pnew->nxt=ptrav->nxt;
                        ptrav->nxt=pnew;
                }
                ptrav=ptrav->nxt;
        }
}
int main()
{
        int nodes;
        printf("enter the node");
        scanf("%d",&nodes);
        int d;
        for(int i=0;i<nodes;i++)
        {
                scanf("%d",&d);
                create(d);
        }
        display();
        int n;
        printf("n");
        scanf("%d",&n);
        struct node *ptemp;
        ptemp=phead->nxt;
        insert_node(n,ptemp);
        display();
}
```
