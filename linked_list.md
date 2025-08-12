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
## 3.program to delete first node in the list
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
        struct node *pnew,*ptrav;
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
                printf("node is added:");
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
        return;
        printf("\n");
}
void deleteHead()
{
        struct node *ptrav;
        ptrav=phead;
        if(ptrav==NULL)
        {
                printf("the list is empty");
                return;
        }
        else
        {
                phead=ptrav->nxt;
                free(ptrav);
        }
        return;
}
void display()
{
        struct node *ptrav;
        ptrav=phead;
        if(ptrav==NULL)
        {
                printf("the list is empty");
                return;
        }
        else
        {
                while(ptrav!=NULL)
                {
                        printf("->%d",ptrav->data);
                        ptrav=ptrav->nxt;
                }
                printf("\n");
        }
}
int main()
{
        create(1);
        create(2);
        create(3);
        create(4);
        create(5);
        display();
        deleteHead();
        display();
}
```
## 4.program to insert head to the list
```c
#include<stdio.h>
#include<stdlib.h>
struct node
{
        int data;
        struct node*nxt;
};
struct node *phead=NULL;
void create(int d)
{
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL)
        {
                printf("malloc errror");
                return;
        }
        pnew->data=d;
        pnew->nxt=NULL;
        if(phead==NULL)
        {
                printf("node is created\n");
                phead=pnew;
                return;
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
        printf("\n");
}
void display()
{
        struct node *ptrav;
        ptrav=phead;
        if(ptrav==NULL)
        {
                printf("the list is empty");
                return;
        }
        else
        {
                while(ptrav!=NULL)
                {
                        printf("->%d",ptrav->data);
                        ptrav=ptrav->nxt;
                }
                printf("\n");
        }
}

void insertnode(int d)
{
        struct node *pnew;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL)
        {
                printf("malloc error");
                return;
        }
        pnew->data=d;
        pnew->nxt=NULL;
        if(phead==NULL)
        {
                printf("the new node added");
                phead=pnew;
        }
        else
        {
                pnew->nxt=phead;
                phead=pnew;
        }
        return;
}
int main()
{
        create(1);
        create(2);
        create(3);
        create(4);
        create(5);
        create(6);
        create(7);
        display();
        insertnode(10);
        display();
}
```
## 5.program to right rotate left in list
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
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL)
        {
                printf("malloc errror");
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
       }
}
void rotate_left(int pos)
{
        struct node *ptrav,*ptemp,*pt;
        ptrav=phead;
        ptemp=phead;
        phead=ptrav->nxt;
        while(ptrav->nxt!=NULL)
        {
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=ptemp;
        ptemp->nxt=NULL;
}
void display()
{
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL)
        {
                printf("%d->",ptrav->data);
                ptrav=ptrav->nxt;
        }
        printf("\n");
}
int main()
{
        int node,d;
        printf("enter the node");
        scanf("%d",&node);
        printf("enter the values");
        for( int i=0;i<node;i++)
        {
                scanf("%d",&d);
                create(d);
        }
        display();
        rotate_left(pos);
        display();
}
```
## 6.Loop Creation and Detection in Linked List
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
        struct node *pnew,*ptrav;
        pnew=(struct node*)malloc(sizeof(struct node));
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
                printf("node added");
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
        if(ptrav==NULL)
        {
                printf("the list is empty");
                return;
        }
        else
        {
                while(ptrav!=NULL)
                {
                        printf("%p\t",ptrav);
                        printf("%d\t",ptrav->data);
                        ptrav=ptrav->nxt;
                }
        }
}
void loopcreate(int target)
{
        struct node *ptrav,*ptemp;
        ptemp=phead;
        ptrav=phead;
        while(ptrav->nxt!=NULL)
        {
                if(ptrav->data==target)
                {
                        ptemp=ptrav;
                }
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=ptemp;
}
void addrloop(struct node *pp)
{
        struct node *ptrav,*ptemp;
        ptrav=phead;
        while( ptrav->nxt!=NULL)
        {
                ptrav=ptrav->nxt;
        }
        ptrav->nxt=pp;
}



int main()
{
        int node,d;
        printf("enter the node count");
        scanf("%d",&node);
        for(int i=0;i<node;i++)
        {
                scanf("%d",&d);
                create(d);
        }
        display();
        //loopcreate(target);
        //display();
        addrloop(phead->nxt);
        display();

}
```
## 7.Write a C program to sort a singly linked list in ascending order and remove duplicate nodes.
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
        struct node *ptrav,*pnew;
        pnew=(struct node*)malloc(sizeof(struct node));
        if(pnew==NULL)
        {
                printf("malloc error");
                return;
        }
        pnew->data=d;
        pnew->nxt=NULL;
        if( phead==NULL)
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
        }
}
void sort()
{
        if (phead == NULL)
        {
                return;
        }
        struct node *ptrav,*i,*prev=NULL,*j,*ptemp;
        ptrav=phead;
        for(i=ptrav;i!=NULL;i=i->nxt)
        {
                prev=ptrav;
                for( j=i->nxt;j!=NULL;j=j->nxt)
                {
                        if( i->data>j->data)
                        {
                                int temp=i->data;
                                i->data=j->data;
                                j->data=temp;
                        }
                        else if(i->data==j->data)
                        {
                                prev->nxt=i->nxt;
                        }
                }
        }
}
void display()
{
        struct node *ptrav;
        ptrav=phead;
        while(ptrav!=NULL)
        {
                printf("%d->",ptrav->data);
                ptrav=ptrav->nxt;
        }
}
int main()
{

        int node,d;
        printf("enter the nodes");
        scanf("%d",&node);
        for(int i=0;i<node;i++)
        {
                scanf("%d",&d);
                create(d);
        }
        display();
        sort();
        display();
}
```

```
