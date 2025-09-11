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
