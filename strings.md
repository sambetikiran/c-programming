## 1.program to COUNT no.of words in a string
```c
#include<stdio.h>
#include<string.h>
void stri(char[]);
int main()
{
        char str[100];  //creating char string array
        printf("enter the sentence");
        fgets(str,sizeof(str),stdin); //assigning the sentence str= i am groot
        str[strcspn(str,"\n")]='\0';              //removal of \n
        stri(str);
}
void stri(char str[])
{
        char out[100];
        int k=0,count=0,i=0;
        while(1)        //due to last word entrance we use infinite loop
        {
                if(str[i]!=' '&&str[i]!='\0')   //checking space for dividing words     
                {
                        out[k++]=str[i];        //assigning character to out[k]
                }
                else
                {
                        out[k]='\0';           //every word will divide by applying '\0'
                        count++;               // to count the number ofword are there in the sentence
                        printf("%s\n",out);
                        k=0;
                }
                if(str[i]=='\0')                //here the condition for breaking the loop
                {
                        break;
                }
                i++;
        }
        printf("the number of words is =%d",count);
}
```
## 2.program to replace ' 'with ',' in a sentence
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the sentence");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        for(int i=0; ;i++)
        {
                if(str[i]==' ')
                {
                        str[i]=',';
                }
                if(str[i]=='\0')
                {
                        str[i]='.';
                        str[i+1]='\0';
                        break;
                }
        }
        printf("%s\n",str);
}
```
## 3.program to find maximum character in sentence
```c
#include<stdio.h>
int main()
{
        char str[100];
        printf("enter the string name");
        fgets(str,sizeof(str),stdin);
        int max=1;
        for(int i=0;str[i]!='\0';i++)
        {
                int count=1;
                int arr[i];
                for(int j=i+1;str[j]!='\0';j++)
                {
                        if(str[i]==str[j])
                        {
                                count++;
                        }
                }
                if(count>max)
                {
                        max=count;
                        printf("%d is maximum=%c\n",,str[i]);
                }
        }
        printf("%d is maximum=%c",max,);
}
```
