## Structure of c Program

- Documentation Section

```c
/* Text is here */
// Text is here
```

- Link Section

```c
#include<stdio.h>
#include<conio.h>
#include<graphics.h>
#include<math.h>
```

- Defination Section

```c
#define MAX 50
```

- Global Declaration Section

  ```c
  int num = 18;
  ```

- Main() Function

  ```c
  void main(){
    printf("I'm a C Program");
  }
  ```

- Sub Programs

```c
int sum(int x, int y)
{
    return x+y;
}
```

---

> Program

```c
// C program to add two numbers
#include <stdio.h>

int main()
{
	int A, B, sum = 0;

	// Ask user to enter the two numbers
	printf("Enter two numbers A and B : \n");

	// Read two numbers from the user || A = 2, B = 3
	scanf("%d%d", &A, &B);

	// Calculate the addition of A and B
	// using '+' operator
	sum = A + B;

	// Print the sum
	printf("Sum of A and B is: %d", sum);

	return 0;
}


```

## Casting

- Implict conv - type conversion (auto)
- Explict conv - type cast (Forceful)

> int = int\*int  
> float = float\*float  
> float = float\*int

```c
#include<stdio.h>
int main(){
    int a=5, b=2;
    float c, d;
    c=a/b;
    printf("value of c %f",c);
    d=(float)a/b;
    printf("value of c %f", d);
   return 0;
}
```

## Scope of Variable

- Local Variable
- Global Variable

```c
#include<stdio.h>
void main()
{
   int x=23, y=4;
   printf(“x = %d and y=%d”,x,y);
}
```

```c
#include<conio.h>
int a=10,b;
void main()
{
  printf(“a = %d and b=%d”,a,b);
}
```

---

## Recursion

```c
#include<stdio.h>
int fact(int);
int main(){
    int num=5, ans;
    ans = fact(num);
    printf("factorial is %d",ans);
}
int fact(int x){
    int f;
    if(x==0){
        return 1;
    }
    f=x*fact(x-1);
}
```

---

## Storage Classes

- Automatic Storage Class
  ```c
  #include<stdio.h>
  int main(){
    int a;
    auto int b;
    // Inital Value Garbage
    //Scope and lifetime in under function.
  }
  ```
- Register Storage Class

```c
#include<stdio.h>
int main(){
    register int a=10;
    // Register value will stored in register. it will useful for quick access
}
```

- Static Storage Class

```c
#include<stdio.h>
int main(){
     functionadd();
     functionadd();
}
functionadd(){
    static int a =1;
    printf("%d",a);
    a++;
}
```

- External Storage Class

```c
#include<stdio.h>
int a =10;
// Global variable is a external variable. we can use it on all the program anywhere.
// when our variable is defined in other files and we need to access global variable data then we will use extern keyword.
// inital value 0, lifetime on program
int main(){
    printf("value of a is %d",a);
}
```
