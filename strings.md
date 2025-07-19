## 1.program to COUNT no.of words in a string
```c
include<stdio.h>
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
