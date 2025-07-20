## DAY 1
```c
#include<stdio.h>
/*int main()
{
	int x=10;
	printf("%d %d",x++,++x);  //output =11 12
	return 0;      
			  //based on chat gpt undefined
}

int main()
{
	char str[100]="C\0inDepth";
	printf("%s",str);        //my guess-> C
	return 0;
}
int main()
{
	int a=5;
	printf("%d %d %d",a,a++,++a);    ouytput 7 6 7
				       //chatgpt undefined
}
int main()
{
	int a=5;
	printf("%d",sizeof(a++));         //4 bytes output =same
}
int main()
{
	int arr[3]={1,2,3};
	printf("%d",*(arr+2));         //3    equal
}
void fun(int a[])
{
	printf("%d",sizeof(a));             //4
}
int main()                           //when we call a function variable must be a pointer 
				     //the pointer memory is 8bytes
				     //out 8 bytes
{
	int arr[10];
	fun(arr);
}
int main()
{
	char *p="C in Depth";
	p[0]='D';
	printf("%s",p);               
				      //output is segmentation fault because string pointer is only read only memory we cant modify
				      //array can used to modify
}
int main()
{
int x = 0;
if (x = 5)
    printf("Yes");                       
					  //output is "yes" because if statment is not there  non zero value  will always true 
else
    printf("No");
}
int main()
{
	int a = 2;
	switch(a) {
    	case 1: printf("One");
    	case 2: printf("Two");                    //two,three because break statement id not there
    	case 3: printf("Three");
}
}
int main()
{
	int i = 0;
    	for(i=0; i<5; i++);
       	printf("%d", i);               //5 because for loop ending has (";") it means it is like  a statment the loop will move to ending and terminate
				       //
}
//theory & output mixed

//1 what is the difference between malloc() and calloc()?

//(A) malloc() is used for dynamic memory allocation with unintialized memory which contains garbage of total memory size.
//    calloc() is used for dynamic memory allocation with intialised memory which contains zeros of each size  of memory array.

//2.what is the use of volatile keyword in C ?

//(A) the volatile is  used to prevent the compiler optimization of specific variable because the vraible value might be change from outside the program

//3. define the dangling pointer?

//(A) dangling pointer is defined as "a specific pointer when  usage had completed we can free the pointer memory but address of memory will there we can use for other memory"
int fun(int a);
int main()
{
	int a = 10;
	printf("%d", a+++a);
	fun(a);
}
int fun(int a)
{
    return;
}
    //Is it valid in C:  "yes ,it is valid "
    //Output?            "the output is 21 because (a++ + a)=11+11=21"
int main()
{
	int a = 0;
	while(a++ < 5)
    		printf("%d", a);
}//output?                       1,2,3,4,5
int main()
{
	int i = 0;
	do {
    	  printf("%d ", i);     //output is "0" because in do_while one time loop will done after predec occurs then it will be "non zero" value then loop while break in one iteration.
	} while(i--);
}
int main()
{
	int a = 5, b = 10;
	printf("%d", a+++b);         //a=5 because preinc +b->5+10=15;
}
int main()
{
	int a = 5;
	printf("%d %d", a, a--);              //a=4,a--=5 because the first right most will calculate and after left will done
}
int main()
{
	int arr[] = {1,2,3};
	printf("%d", *(arr + 1));             //2  (*axoo1+4*1)=ax004->2
}
int main()
{
	printf("%d", 5 + 'A');               //output=70 because the asciivalue'A'=65>>65+5=70
}*/
int main()
{
	int i = 1;
	printf("%d", i++ + ++i);
	//What is the output of:            i++ + ++i==> 1+3=4
}
//describe the segumentation fault and give typical cause in c?

//(A) the segumentationn fault may occurs when it try to access the memory location without permission . 
       //causes->1. dereferncing of pointers,2.stack overflow,3.in array out of bound acessing,4.dangling pointer.
//what is the difference between extern and static variable
//(A) static variable is used to restrict the access of specific file to main file or another.
      //extern  will used to for giving acces to the variable or function to another filr.
```
