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
