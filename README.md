# scientific-claculator


// the library 
#ifndef MYLIB_H
#define MYLIB_H
         

    

    int power_of_ten(int a) {
         int result  ,  i;
         result = 1 ; 
         for (i=1;i<=a;i++){
            result*=10; 
         }

        return result ;
         }
    float squart( float a) {
        float result ; 
        result = a*a ; 

        return result ; 

    }
    int factorial(int a) {
         int i, result = 1;
    for (i = 1; i <= a; i++) {
        result *=   i;
    }
    return result;
    }
    float power_of_mines_one(float a) {
        float result ; 
        result = 1 / a ; 
        return result ; 
    }
    


float sum(float a, float b) {
    return a + b;
}

float subtract(float a, float b) {
    return a - b;
}

float multiply(float a, float b) {
    return a * b;
}

float divide(float a, float b) {
    return a / b;
}

float power(float a, float b) {
    int i;
    float result = 1;

    if (b > 0) {
        for (i = 1; i <= (int)b; i++) {
            result *= a;
        }
    } else if (b < 0) {
        b*=-1;
        for (i = 1; i <= (int)(b); i++) {
           result *=b; 
          
        } result=1/result;
        return result; }}
#endif



//thecode 


#include <stdio.h>
#include "MYLIB_H.h"




int main() {
    float firstNumber, secondNumber, result,c;
   
   


  
    char operator [] = {1,2,3,4,5,6,0}; 
    
   


  


    printf("=========================================\n");
    printf("         TERMINAL CALCULATOR              \n");
    printf("=========================================\n");
    printf(" [+] +  Addition\n");
    printf(" [-] -  Subtraction\n");
    printf(" [*] *  Multiplication\n");
    printf(" [/] /  Division\n");
    printf(" [^] ^  Power (x^y)\n");
    printf(" [√] sqrt  Square Root\n");
    printf(" [p] 10 power of x  \n");

    printf("-----------------------------------------\n");
    printf(" [E] Exit\n");
    printf("=========================================\n");

    printf("\nSelect an option: ");
    scanf("%d", &operator); 
 
   switch (operator) {
    case (operator ='+'):
         result= sum(firstNumber,secondNumber);
    break; 
    
    case (operator='-'):
        result= subtract(firstNumber,secondNumber); 
    break ; 
    case (operator='*'): 
        result = multiply(firstNumber,secondNumber); 
    break ; 
    case (operator ='/'):
        if (secondNumber==0) {
            printf("we cant devide by 0 ");

        } 
        else {
            result = divide(firstNumber,secondNumber); 

        }
    break ; 
    case (operator ='^') :
        result = Power(firstNumber,secondNumber); 
    break ; 
    case (operator='√'):

    break ; 
    case (operator = 'p'):
        result = power_of_ten(firstNumber) ; 
    break ; 
   0
    }
   
  
    printf ("the result = %d",result); 

   return 0 ; 
  
}


