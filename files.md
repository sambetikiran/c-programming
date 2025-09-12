## 1.program to print the largest word and smallest word using files
```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
int main()
{
        FILE *fp=fopen("file1.txt","r");
        char buf[100];
        char qrr[100];
        int max=0;
        int min=10;
        char maxi[100];
        char mini[100];
        int len;
        while(fscanf(fp,"%s",buf)!=EOF)
        {
                len=strlen(buf);
                if(len>max)
                {
                        max=len;
                        strcpy(maxi,buf);
                }
                if(len<min)
                {
                        min=len;
                        strcpy(mini,buf);
                }
        }
        printf("%s\n",maxi);
        printf("%s\n",mini);
        fclose(fp);
}
```
## 2.program to print only vowel charcter starting word using files
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int main()
{
        FILE *fp;
        fp=fopen("file1.txt","r");
        char  buf[100];
        if(fp==NULL)
        {
                printf("open error");
                exit(0);
        }
        int count=0;
        while(fscanf(fp,"%s",buf)!=EOF)
        {
                if(buf[0]=='a'||buf[0]=='e'||buf[0]=='i'||buf[0]=='o'||buf[0]=='u')
                {
                        printf("%s\n",buf);
                        count++;
                }
        }
        fclose(fp);
}
```
## 3.Write a C program to read a file "file1.txt", replace all occurrences of the word "world" with "universe", and write the result to a new file "new.txt".
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int main()
{
        FILE *fp,*new;
        fp=fopen("file1.txt","r");
        new=fopen("new.txt","w");
        char word[100];
        if(fp==NULL)
        {
                printf("open error");
                exit(0);
        }
        while(fscanf(fp,"%s",word)!=EOF)
        {
                if(strcmp("world",word)==0)
                {
                        strcpy(word,"universe");
                }
                fprintf(new," %s",word);
        }
        fclose(fp);
}
```
## 4. program to read the file and print the palindrome words from the file 
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int main()
{
        FILE *fp=fopen("file1.txt","r");
        char buf[100];
        if(fp==NULL)
        {
                printf("open error");
                exit(0);
        }
        char word[100];
        int k=0;
        while(fscanf(fp,"%s",buf)!=EOF)
        {
                for(int i=strlen(buf)-1;i>=0;i--)
                {
                        word[k++]=buf[i];
                }
                word[k]='\0';
                if(strcmp(word,buf)==0)
                {
                        printf("%s\n",word);
                }
                k=0;
        }
        fclose(fp);
}
```
## 5. program to perform write,read,update(append) and finally delete the file
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
void create()
{
        FILE *fp;
        char new[100];
        fp=fopen("new1.txt","w");
        if(fp==NULL)
        {
                printf("open error in create");
                return;
        }
        printf("enter the string:");
        fgets(new,sizeof(new),stdin);
        fprintf(fp,"%s",new);
        new[strcspn(new,"\n")]='\0';
        fclose(fp);
}
void read()
{
        FILE *fp;
        char new[100];
        fp=fopen("new1.txt","r");
        if(fp==NULL)
        {
                printf("open error in read\n");
                return;
        }
        while(fgets(new,sizeof(new),fp)!=NULL)
        {
                printf("%s",new);
        }
        new[strcspn(new,"\n")]='\0';
        fclose(fp);
}
void update()
{
        FILE *fp;
        char new[100];
        fp=fopen("new1.txt","a");
        if(fp==NULL)
        {
                printf("open error in update\n");
                return;
        }
        fgets(new,sizeof(new),stdin);
        fprintf(fp,"%s",new);
        fclose(fp);
}
void deleteFile() {
    char filename[100];
    printf("Enter filename to delete: ");
    scanf("%s", filename);

    if (remove(filename) == 0)
        printf("File deleted successfully!\n");
    else
        printf("Error deleting file!\n");
}
int main()
{
        create();
        read();
        update();
        read();
        printf("enter the number='0' if file want to delete");
        int num;
        scanf("%d",&num);
        if(num==0)
        {
        deleteFile();
        }
}
```
