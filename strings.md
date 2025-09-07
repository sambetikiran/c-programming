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
                else
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
## 14. program to write a repeated character in a string
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int count[256]={0};
        for( int i=0;str[i]!='\0';i++)
        {
                count[(unsigned char)(str[i])]++;
        }
        for( int i=0;i<256;i++)
        {
                if(count[i]>1)
                {
                        printf("%c : %d \n",i,count[i]);
                }
        }
}
```
## 15.program to convert vowels into uppercase letters in a string
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        for( int i=0;str[i];i++)
        {
                if(str[i]=='a'||str[i]=='e'||str[i]=='i'||str[i]=='o'||str[i]=='u')
                {
                        str[i]=str[i]-32;
                }
        }
        printf("%s\n",str);
}
```
## 16.program to remove white spaces in a string
```c
#include<string.h>
#include<stdio.h>
#include<ctype.h>
int main()
{
        char str[100]=" hello world";
        int i=0;
        while(!isalpha(str[i])&&!isdigit(str[i]))
        {
                for(int j=0;str[j]!='\0';j++)
                {
                        str[j]=str[j+1];
                }
        }
        printf("%s\n",str);
}
```
## 17.. Input a string and change it so that the characters are placed in alphabetical order. For example the string "Devanshi"should be changed to "aDehinsv".
```c
#include<stdio.h>
#include<string.h>
#define MAX 100
int main()
{
        char str[100]="Devanshi";
        int len=(strlen(str));
        char ch,sam;
        int found,flag;
        for( int i=0;i<len-1;i++)
        {
                for( int j=0;j<len-i-1;j++)
                {
                        found=0;
                        flag=0;
                        if(str[j]>='A' &&str[j]<='Z')
                        {
                                ch=str[j];
                                str[j]=str[j]+32;
                                found=1;
                        }
                        sam=str[j+1];
                        if(str[j+1]>='A' &&str[j+1]<='Z')
                        {
                                sam=str[j+1]+32;

                        }
                        if(str[j]>sam)
                        {
                                char temp=str[j];
                                str[j]=str[j+1];
                                str[j+1]=temp;
                                flag=1;
                        }
                        if(found)
                        {
                                if(flag)
                                {
                                        str[j+1]=ch;
                                }
                                else
                                {
                                        str[j]=ch;
                                }
                        }
                }
        }
        printf("%s",str);
}
```
## 18.Write a C program that takes a string as input and prints a staircase pattern using escape sequences.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        for(int i=0;str[i];i++)
        {
                for(int j=0;j<=i;j++)
                {
                        printf("%c\t",str[i]);
                }
                printf("\n");
        }
}
```
## 19.Write a C program to read a string and print all possible substrings of that string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int len=strlen(str);
        for(int i=0;i<len;i++)
        {
                for(int j=i;j<len;j++)
                {
                        for( int k=i;k<=j;k++)
                        {
                                printf("%c",str[k]);
                        }
                        printf("\n");
                }
        }
}
```
## 20 write a cprogram to to print given string is palindorme or not?
```c
#include<stdio.h>
#include<string.h>
#include<ctype.h>
void pal(char[]);
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        pal(str);
}
void pal(char str[])
{
        char alp[100];
        int k=0,flag;
        for( int i=0;str[i]!='\0';i++)
        {
                if(isalpha(str[i]))
                {
                str[i]=tolower(str[i]);
                //str[i]=ch;
                }
                if(str[i]>='a' &&str[i]<='z' ||str[i]>='A'&&str[i]<='Z')         //allowing only alphabets
                {
                        alp[k++]=str[i];                                           //alphabet character assgining to alp
                }
        }
        alp[k]='\0';
        printf("%s\n",alp);
        int l=0,j=strlen(alp)-1;                                             //finding length of the string
        while(j>0)
        {
                if(alp[l]!=alp[j])
                {
                        flag=1;
                }
                if(flag==1)
                {
                        printf("it is not a palindrome\n");
                        break;
                }
                l++;
                j--;
        }
                if(flag==0)
                {
                printf("it is a palindrome");
        }
}
```
## 21 .program to count maximum characters in string
```c
#include<stdio.h>
#include<string.h>
int main()
{
        printf("enter the string");
        char str[100];
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int count=0;
        for(int i=0;str[i];i++)
        {
                count++;
        }
        printf("%d",count);
}
```
## 22.write program to count the length of the string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int count=0;
        for(int i=0;str[i]!='\0';i++)
        {
                count++;
        }
        printf("%d",count);
}
```
## 23. program to trim leading white spaces in a string
```c
#include<string.h>
#include<stdio.h>
#include<ctype.h>
int main()
{
        char str[100]=" hello world";
        int i=0;
        while(!isalpha(str[i])&&!isdigit(str[i]))
        {
                for(int j=0;str[j]!='\0';j++)
                {
                        str[j]=str[j+1];
                }
        }
        printf("%s\n",str);
}
```
## 24 .program to remove  vowels in a string.
```c
 #include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        for(int i=0;str[i];i++)
        {
                if(str[i]>='A'&&str[i]<='Z')
                {
                        str[i]=str[i]+32;
                }
                if(str[i]=='a'||str[i]=='e'||str[i]=='i'||str[i]=='o'||str[i]=='u')
                {
                        str[i]=str[i]+1;
                }
        }
        printf("%s\n",str);
}
```
## 25.program to reverse the word using speacial function
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char word[100],reverse[100];
        printf("enter the value");
        fgets(word,sizeof(word),stdin);
        word[strcspn(word,"\n")]='\0';
        reverse=strrev(word);
        printf("%s\n",reverse);
}
```
## 26 program to use special charaters like strncat,strcpy.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        char str1[100];
        printf("enter the string");
        fgets(str1,sizeof(str1),stdin);
        str1[strcspn(str1,"\n")]='\0';
        strncat(str,str1,);
        //strcpy(str1,str);
        printf("%s\n",str);
}
```
## 27 .Write a C program to check whether any word in a given string contains the character 'a' or the substring "ram".
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the number");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        char *tok=strtok(str," ");
        int flag=0,found=0;
        while(tok!=NULL)
        {
                if(strchr(tok,'a')!=0)
                {
                        flag=1;
                }
                if(strstr(tok,"ram")!=0)
                {
                        found=1;
                 }
                tok=strtok(NULL," ");
        }
        if(flag==1)
        {
                printf("a is found");
        }
        if(found==1)
        {
                printf("ram is found");
        }
}
```
## 28 .Write a C program to reverse each word of a given string without changing the order of words.
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>

void reverse_word(char *sptr)
{
        int start=0, end=0;
        while(sptr[end]!='\0')
        {
                while(sptr[end]!=' '&&sptr[end]!='\0')
                {
                        end++;
                }
                int i=start, j=end-1;
                while(i<j)
                {
                        char temp=sptr[i];
                        sptr[i]=sptr[j];
                        sptr[j]=temp;
                        i++;
                        j--;
                }
                start=end+1;
                end=start;
        }
        return;
}

int main()
{
        char *sptr;
        sptr=(char *)malloc(sizeof(char)*100);
        printf("Enter the string\n");
        fgets(sptr,100,stdin);
        sptr[strlen(sptr)-1]='\0';
        printf("Entered string before reversing each word:\n%s\n",sptr);
        reverse_word(sptr);
        printf("Entered string after reversing each word:\n%s\n",sptr);
        return 0;
}
```
## 29.program to convert upper and lower case
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char sent[100];
        printf("enter the sentence:");
        fgets(sent,sizeof(sent),stdin);
        int len=strlen(sent);
        for(int i=0;i<=len;i++)
        {
                if(sent[i]>='a'&& sent[i]<='z')
                {
                        sent[i]=sent[i]-32;
                }
        }
        printf("%s",sent);
        for(int i=0;i<=len;i++)
        {
                if(sent[i]>='A'&& sent[i]<='Z')
                {
                        sent[i]=sent[i]+32;
                }
        }
        printf("%s",sent);


}
```
## 30 program to compare two strings either same or not
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str1[100];
        printf("ente the first string");
        fgets(str1,sizeof(str1),stdin);
        str1[strlen(str1)-1]='\0';
        char str2[100];
        printf("enter the second string");
        fgets(str2,sizeof(str2),stdin);
        str2[strlen(str1)-1]='\0';
        int flag=0;
        for(int i=0;str1[i]!='\0'||str2[i]!='\0';i++)
        {
                if(str1[i]!=str2[i])
                {
                        flag=1;
                        break;
                }
        }
                if(flag==1)
                {
                        printf("the are not same");
                }
                else
                {
                        printf("those are same");
                }
}
```
##  31. Write a program to abbreviate input text. For example if the input is "World Health Organization'', then the output should be WHO 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        if(str[0]!=' ')
        {
                printf("%c",str[0]);
        }
        for(int i=0;str[i]!='\0';i++)
        {
                if(str[i]==' ')
                {
                        printf("%c",str[i+1]);
                }
        }
}
```
## 32 .Write a function to extract a substring from a string. Assume that the substring starts at the i character(start counting from 0 character) and is n characters long.
```c
#include <stdio.h>
#include <string.h>

void substring(char source[], char target[], int start, int n)
{
    int i;
    for(i = 0; i < n && source[start + i] != '\0'; i++)
    {
        target[i] = source[start + i];
    }
    target[i] = '\0';
}

int main()
{
    char str[100], sub[100];
    int pos, len;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter starting position: ");
    scanf("%d", &pos);

    printf("Enter length of substring: ");
    scanf("%d", &len);

    substring(str, sub, pos, len);

    printf("Extracted substring: %s\n", sub);

    return 0;
}
```
## 35 program to print reorder the given sentence 
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        int len=strlen(str);
        int end=len,start;
        for(int i=len-1;i>=0;i--)
        {
                if(str[i]==' '||i==0)
                {
                        if(i==0)
                        {
                                start=0;
                        }
                        else if(str[i]==' ')
                        {
                                start=i+1;
                        }
                        for(int j=start;j<end;j++)
                        {
                                printf("%c",str[j]);
                        }
                        printf(" ");
                        end=i;
                }
        }
}
```
## 36. program to reverese from middle of the string.
```c
#include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strlen(str)-1]='\0';
        int len=strlen(str);
        int mid=len/2;
        for(int i=0;i<(len-mid)/2;i++)
        {
                int temp= str[mid+i];
                str[mid+i]=str[len-i-1];
                str[len-i-1]=temp;
        }
        printf("%s",str);
}
```
## 37. program to count the number of words in a string
```c
include<stdio.h>
#include<string.h>
int main()
{
        char str[100];
        int count=0;
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        for(int i=0;;i++)
        {
                if(str[i]==' '||str[i]=='\0')
                {
                        count++;
                }
                if(str[i]=='\0')
                {
                        break;
                }
        }
        printf("%d",count);
}
```
## 38.Write a C program to replace digits with their word equivalents.Example: "c2d5" → "ctwodfive" explain logic
```c
int main()
{
        //"c2d5" → "ctwodfive"
        char str[100];
        printf("enter the string");
        fgets(str,sizeof(str),stdin);
        str[strcspn(str,"\n")]='\0';
        for(int i=0;str[i]!='\0';i++)
        {
                if(str[i]>='0'&&str[i]<='9')
                {
                int a=str[i]-'0';
                switch(a)
                {
                        case 1:
                                printf("one");
                                break;
                        case 2:
                                printf("two");
                                break;
                        case 3:
                                printf("three");
                                break;
                        case 4:
                                printf("four");
                                break;
                        case 5:
                                printf("five");
                                break;
                        case 6:
                                printf("six");
                                break;
                        case 7:
                                printf("seven");
                                break;
                        case 8:
                                printf("eight");
                                break;
                        default:
                                printf("nine");
                                break;
                }
                }
                else
                {
                        printf("%c",str[i]);
                }
        }
        printf("\n");
}
```
```
