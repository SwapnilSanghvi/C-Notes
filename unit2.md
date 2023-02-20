## String

```c
#include<stdio.h>
int main(){
    char firstname[10]={'s','w','a','p','n','i','l'};
    char lastname[]="Sanghvi";
    printf("%c",firstname[0]);
    printf("%s",firstname);
}
```

```c
#include<stdio.h>
int main(){
    char name[10];
    printf("what is your name");
    scanf("%s",name);
    printf("your name is %s",name);
}

```

---

## Pointer expression

> data_type \* pointer_name;

```c
#include<stdio.h>
int main(){
  int a=100;
  printf("value of number is %d, address of number is %u",a,&a);
}

```

```c
#include<stdio.h>
int main(){
  int *p ;
  int b=100;
  p=&b;
  printf("%d",*p);
}

```

- Pointer Expression

  ```c
  #include<stdio.h>
  int main(){
  int a=10, b=20, add,sub,mul,mod;
  float div;
  int *ptr_a,*ptr_b;
  ptr_a = &a;
  ptr_b = &b;

  add = *ptr_a + *ptr_b;
  sub = *ptr_a - *ptr_b;
  mul = *ptr_a * *ptr_b;
  div = *ptr_a / *ptr_b;
  mod = *ptr_a % *ptr_b;

    // Printing values
    printf("Addition = %d\n", add);
    printf("Subtraction = %d\n", sub);
    printf("Multiplication = %d\n", mul);
    printf("Division = %d\n", div);
    printf("Modulo = %d\n", mod);
  }

  ```

---

## Pointer arithemetic

- Increment/Decrement of a Pointer
  ```c
  #include <stdio.h>
  int main() {
  int a=10;
  int \*p;
  p=&a;
  printf("address of p is %u",p);
  p++;
  printf("after increment address of p is %u",p);
  }
  ```
  > address of p is 2615705868
  > after increment address of p is 2615705872
  ```c
  #include <stdio.h>
  int main() {
  int a=10;
  int *p;
  p=&a;
  printf("address of p is %u",p);
  p--;
  printf("after increment address of p is %u",p);
  }
  ```
  > address of p is 292168364
  > after increment address of p is 292168360
- Addition

  ```c
  #include <stdio.h>
  int main() {
    int a=10;
    int *p;
    p=&a;
    printf("address of p is %u",p);
    p=p+2;
    printf("after increment address of p is %u",p);
  }
  ```

  > address of p is 1846742716
  > after increment address of p is 1846742716

- Substraction
  ```c
  #include <stdio.h>
  int main() {
    int a=10;
    int *p;
    p=&a;
    printf("address of p is %u",p);
    p=p-2;
    printf("after increment address of p is %u",p);
  }
  ```
  > address of p is 828647372
  > after increment address of p is 828647372

---

## Array of pointers

```c
#include <stdio.h>
int main() {
  int marks[]={10,20,30};
  int *point[3];
  int i;
  for(i=0;i<3;i++){
      printf("marks is %d, ",marks[i]);
      point[i]=&marks[i];
  }
  for(i=0;i<3;i++){
      printf("value of pointer is %d and address is %u, ",*point[i],point[i]);
  }
}
```

---

## function returning pointers

```c
  #include<stdio.h>
  int *fun(){
      static int a=10;
      return(&a);
  }
  int main(){
      int *p;
      p = fun();
      printf("value of pointer is %d",*p);
  }
```

---

## pointer to function

> `<function return type> (<*pointer_name>)(function argument type)`  
> pointer-name = function-name;  
> pointer-name = &function-name;

```c
#include<stdio.h>
void add (int x, int y){
printf("value of x is %d and value of y is %d",*&x,*&y);
printf("addition of x and y ius %d",x+y);
}
int main() {
   int a,  b;
   void (*ptr)(int,int);
   ptr=add;
   printf("enter first number");
   scanf("%d",&a);
   printf("enter second number");
   scanf("%d",&b);
   ptr(a,b);

}
```

---

## malloc()

> void* malloc(size-in-byte);  
> ptr = (cast_type*)malloc(size_in_byte);

```c
#include<stdio.h>
#include<stdlib.h>
int main(){
    int i,n,*ptr;
    printf("enter number of element");
    scanf("%d",&n);
    ptr=(int *)malloc(n*sizeof(int));
    for(i=0;i<n;i++){
        printf("enter element :");
        scanf("%d",ptr+i);
    }
    printf("all element :");
    for(i=0;i<n;i++){
        printf("%d",*(ptr+i));
    }
}
```

> enter number of element3  
> enter element :1  
> enter element :2  
> enter element :3  
> all element :123

---

## calloc()

> void _ calloc(number_of_element(N),sizeof(datatype));
> data_type ptr = (data_type _) calloc(N,sizeof(datatype));

```c
#include<stdio.h>
#include<stdlib.h>
int main(){
    int n,i,*ptr;
    printf("enter number of element");
    scanf("%d",&n);
    ptr=(int *) calloc(n,sizeof(int));
    for(i=0;i<n;i++){
        printf("enter number");
        scanf("%d",ptr+i);
    }
    printf("all element is");
    for(i=0;i<n;i++){
        printf("%d",*(ptr+i));
    }
}
```

---

## structures

`struct structure_name{
 data_type member1;
 data_type member2;
 }struct_var`

```c
#include <stdio.h>
#include <string.h>

// create struct with person1 variable
struct Person {
  char name[50];
  int citNo;
  float salary;
} person1;

int main() {

  // assign value to name of person1
  strcpy(person1.name, "George Orwell");

  // assign values to other person1 variables
  person1.citNo = 1984;
  person1. salary = 2500;

  // print struct variables
  printf("Name: %s\n", person1.name);
  printf("Citizenship No.: %d\n", person1.citNo);
  printf("Salary: %.2f", person1.salary);

  return 0;
}
```

## Union

`union union_name{
 data_type member1;
 data_type member2;
 }union_var`

```c
#include<stdio.h>
#include<string.h>
union person{
    int num;
    char name[20];
};
int main(){
    union person p;
    p.num=100;
    printf("%d",p.num);
    strcpy(p.name,"Swapnil Sanghvi");
    printf("%s",p.name);
    return 0;
}
```

## File Handling

- fopen() -open
- fclose() - close
- fgets() - read a file
- fprintf() - write block of data
- fscanf() - read block of data
- fgetc() - read single char form a file
- fputc() - write single char from a file

Create a file

> FILE \*ptr;  
> ptr = fopen("swapnil.txt","w");

Write a file

> FILE \*ptr;  
> ptr = fopen("swapnil.txt","w");  
> fprintf(ptr, "%s %d", "swapnil", 2017);

Reading a file

> FILE \*ptr;  
> ptr=fopen("swapnil.txt","r");  
> fscanf(ptr, "%s %d", name, &num);

Closing a file

> FILE \*ptr;  
> ptr=fopen("swapnil.txt","r");  
> fclose(ptr);

Example 1: Program to Open a File, Write in it, And Close the File

```c
#include<stdio.h>
int main(){
    FILE *fp;
    // Open a file
    fp=fopen("swapnil.txt","w");
    if(fp==NULL){
        printf("file is failed to open");
    }
    else{
        printf("file is opened");
    }
    // Write data
    fprintf(fp,"%s","Swapnil");

    // Read data
    fscanf(fp,"%s",name);

    // close file
    fclose(fp);


}
```
