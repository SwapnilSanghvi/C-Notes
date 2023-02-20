## Factorial of a Number Using Recursion

```c
#include<stdio.h>
int fact(int n);
int main(){
    int n=10;
    printf("factorial of %d is %d",n,fact(n));
    return 0;
}
int fact(int n){
    if(n>=1){
        return n*fact(n-1);
    }
    else{
        return 1;
    }
}
```

---

## Swapping numbers using call by reference in C

```c
#include<stdio.h>
int swap(int *x, int *y);
int main(){
    int a=10,b=30;
    printf("initial value of a is %d and b is %d",a,b);
    swap(&a, &b);
    printf("Now value of a is %d and b is %d",a,b);
}
int swap(int *x, int *y){
    int temp;
    temp=*x;
    *x=*y;
    *y=temp;

}
```

---

## swap two numbers without third variable

```c
#include<stdio.h>
int main(){
    int a=10,b=20;
    printf("initial value of a is %d and b is %d \n",a,b);
    a=a+b; //30
    b=a-b; //10
    a=a-b; //20
    printf("current value of a is %d and b is %d",a,b);
}
```

---

## Program to Check Prime Number

```c
#include<stdio.h>
int main(){
   int n, count=0,i=0;
   printf("enter a number");
   scanf("%d",&n);
   for(i=1;i<=n;i++){
       if(n%i==0){
         count++;
       }
   }
   if(count==2){
           printf("number is prime");
       }
       else{
           printf("number is not prime");
       }
}
```

---

## Program to Check palindrome number

```c
#include<stdio.h>
int main(){
int n=131,temp,sum=0,r;
temp=n;
while(n>0){
r=n%10;
sum=(sum*10)+r;
n=n/10;}
if(temp==sum){
    printf("it is palidrome number");
}
else{
    printf("number is not palidrome");
}
}
```

---

## Sum of First and Last Digits of a Four-Digit number in C

```c
#include<stdio.h>
int main(){
int num =1234, sum,second, last;
second =(num/100)%10;
sum=second;
last=num%10;
sum=sum+last;
printf("sum is %d", sum);

}
```

---

## Program to Check Vowel or consonant

```c
#include<stdio.h>
int main(){
char c;
int v1,v2;
printf("enter any character");
scanf("%c",&c);
if(c=='a'||c=='e'||c=='i'||c=='o'||c=='u'){
     printf("%c is a vowel.", c);
}
 else
        printf("%c is a consonant.", c);
}
```

---

## Display Fibonacci Sequence

```c
#include<stdio.h>
int main(){
int i,n,n1=0, n2=1;
int nextterm=n1+n2;
// get no. of terms from user
  printf("Enter the number of terms: ");
  scanf("%d", &n);

// print the first two terms t1 and t2
  printf("Fibonacci Series: %d, %d, ", n1, n2);
for(i=3;i<=n;i++){
    printf("%d, ", nextterm);
      n1=n2;
      n2=nextterm;
      nextterm=n1+n2;
  }
}
```

---

## full pyramid of star

```c
#include <stdio.h>
#include <conio.h>
void main()
{

    int i, j, rows, k = 0;
    printf (" Enter a number to define the rows: \n");
    scanf ("%d", &rows);

    for ( i =1; i <= rows; i++)
    {
        for ( j = 1; j <= rows - i; j++)
        {
            printf ("  ");
        }
        // use for loop where k is less than equal to (2 * i -1)
        for ( k = 1; k <=2*i-1; k++)
        {
            printf ("* "); // print the Star
        }
        printf ("\n");
    }
    getch();
}

```

---

# check a leaf year

```c
#include <stdio.h>
#include <conio.h>
void main()
{

    int year;
    printf (" Enter year \n");
    scanf ("%d", &year);

    if(year%400==0){
        printf("%d is a leaf year",year);
    }
    else if(year%4==0){
        printf("%d is a leaf year",year);
    }
    else{
       printf("%d is not a leaf year",year);
    }
    getch();
}

```
