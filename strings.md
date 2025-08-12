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
## 4.program to print all only alphabets in a string
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char sent[100];
        printf("enter the string:");
        fgets(sent,sizeof(sent),stdin);
        int len=strlen(sent);
        char alp[100];
        int k=0;
        for(int i=0;sent[i]!='\0';i++)
        {
                if(sent[i]>='a'&&sent[i]<='z'||sent[i]>='A'&&sent[i]<='Z')
                {
                        alp[k++]=sent[i];
                }
        }
        alp[k]='\0';
        printf("%s",alp);

}
```
## 5.program to find non repeating character
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int count[256]={0};
        for( int i=0;str[i]!='\0';i++)
        {
                count[(unsigned char)str[i]]++;
        }
        for( int i=0;str[i]!='\0';i++)
        {
                if(count[str[i]]==1)
                {
                        printf("%c",str[i]);
                }
        }
}
```
## 6.program to print the most repeating character
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int count[256]={0};
        for(int i=0;str[i]!='\0';i++)
        {
                count[(unsigned char)str[i]]++;
        }
        int max=0,k=0;
        for(int i=0;str[i]!='\0';i++)
        {
                if( count[(unsigned char)str[i]]>max)
                {
                        max=count[(unsigned char)str[i]];
                        printf("%c is max character of %d",str[i],max);
                }
        }
}
```
## 7. program to print longest non repeating character in a string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int count[256];
        for( int i=0;i<256;i++)
        {
                count[i]=-1;
        }
        int maxlen=0,start=0,maxstart=0;
        for( int i=0;str[i]!='\0';i++)
        {
                if(count[str[i]]>=start)
                {
                        start=count[str[i]]+1;
                }
                count[str[i]]=i;
                if( i-start+1>maxlen)
                {
                        maxlen=i-start+1;
                        maxstart=start;
                }
        }
        printf("longest no repeating are:");
        for( int i=maxstart;i<maxstart+maxlen;i++)
        {
                printf("%ci\n",str[i]);
        }
}
```
## 8.write a program to reverse a string using pointers without using library
```c
#include<stdio.h>
#include<string.h>
int reverse(char[]);
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        reverse(str);
        printf("%s\n",str);
}
int reverse(char *str)
{
        char *start=str;
        char *end=str;
        while(*end!='\0')
        {
                end++;
        }
        end--;
        while( start<end)
        {
                char temp=*start;
                *start=*end;
                *end=temp;
                start++;
                end--;
        }
}
```
## 9.Write a C program to count the number of vowels, consonants, digits, and special characters in a given
```c
#include<stdio.h>
#include<string.h>
void countt(char[]);
int main()
{
        char str[100];
        printf("enter the number");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        countt(str);
}
void countt(char str[])
{
        int digit_count=0;
        int char_count=0;
        int spl_count=0;
        for( int i=0;i<str[i]!='\0';i++)
        {
                if( str[i]>='0'&&str[i]<='9')
                {
                        digit_count++;
                }
                else if(str[i]>='a' &&str[i]<='z'|| str[i]>='A' &&str[i]<='Z')
                {
                        char_count++;
                }
                else
                {
                        spl_count++;
                }
        }
        printf("digit count=%d\n",digit_count);
        printf("character count=%d\n",char_count);
        printf("special count=%d\n",spl_count);

}
```
## 10. write a C program to sort string in an array
```c
#include<string.h>
#include<stdio.h>
#define MAX 100
int string(int ,char [][MAX]);
int main()
{
        int num;
        printf("enter the number");
        scanf("%d",&num);
        char str[num][MAX];
        printf("enter the string");
        for(int i=0;i<num;i++)
        {
                scanf("%s",str[i]);
        }
        string(num,str);
        for( int i=0;i<num;i++)
        {
                printf("%s\n",str[i]);
        }
}
int string(int num,char str[][MAX])
{
        for( int i=0;i<num-1;i++)
        {
                for( int j=0;j<num-i-1;j++)
                {
                        if(strcmp(str[j],str[j+1])>0)
                        {
                                char temp[100];
                                strcpy(temp,str[j]);
                                strcpy(str[j],str[j+1]);
                                strcpy(str[j+1],temp);
                        }
                }
        }
        for( int i=0;i<num;i++)
        {
                printf("%s\n",str[i]);
        }
}
```
## 11.program to print a string word every character in an ascending order
```c
#include<string.h>
#include<stdio.h>
void sort(char str[]);
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        sort(str);
}
void sort(char str[])
{
        int len=strlen(str);
        for( int i=0;i<len-1;i++)
        {
                for(int j=0;j<len-i-1;j++)
                {
                        if(str[j]>str[j+1])
                        {
                        int temp=str[j];
                        str[j]=str[j+1];
                        str[j+1]=temp;
                        }
                }
        }
        printf("%s\n",str);
}

```
## 12.Write a C program that reads two strings of equal length and modifies the first string so that each character is changed step-by-step (in ASCII order) until it matches the corresponding character in the second string. Finally, print the modified first string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter string:");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        char str1[100];
        printf("enter string:");
        fgets(str1,sizeof(str1),stdin);
        str1[strcspn(str1,"\n")]='\0';
        int j=0;
        for( int i=0;str[i]!='\0'&&str[j]!='\0';i++)
        {
                while(1)
                {
                        if(str[i]<str1[j])
                        {
                                str[i]=str[i]+1;
                        }
                        else if(str[i]>str1[j])
                        {
                                str[i]=str[i]-1;
                        }
                        if(str[i]==str1[j])
                        {
                                break;
                        }
                }
                j++;
        }
        printf("%s\n",str);
}
```
## 13.Question: Write a C program that takes a string as input and finds the longest and shortest words in the string. Print the lengths of the longest and shortest words and the words themselves.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char ch[100];
        printf("enter the string1:");
        fgets(ch,sizeof(ch),stdin);
        ch[strcspn(ch,"\n")]='\0';
        int count=0,k=0;
        char word[100];
        int min=1000,max=0;
        char max_word[100],min_word[100];
        for( int i=0;ch[i];i++)
        {
                if(ch[i]!=' '&& ch[i]!='\0')
                {
                        word[k++]=ch[i];
                        count++;
                }
                if(ch[i]==' '||ch[i]=='\0')
                {
                        word[k]='\0';
                        if(max<count)
                        {
                                max=count;
                                strcpy(max_word,word);
                        }
                        if(count<min)
                        {
                                min=count;
                                strcpy(min_word,word);
                        }
                k=0;
                count=0;
                }
        }
        printf("%d\n",max);
        printf("%d\n",min);
        printf("%s\n",max_word);
        printf("%s\n",min_word);
}
``` 
```
