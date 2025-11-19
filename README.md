# scientific-claculator


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
    double factorial(int a) {
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
    long  result = 1;

    if (b == 0) {
        return 1;  
    } else if (b > 0) {
        for (i = 1; i <= (int)b; i++) {
            result = a * result;
        }
    } else {  
        b = -b;
        for (i = 1; i <= (int)b; i++) {
            result = a * result;  
        }
        result = 1 / result;
    }

    return result;
}

float absolute_value(float a) {
    if (a < 0) {
        return -a;
    }
    return a;
}


    float square_root(float a ) {
       double r=a;
       double epsilon= 0.000001; // yeah its epsilon analyse 😀😀
       if (a==0){
        return 0 ; 
       }
           while (absolute_value(r * r - a)>epsilon ){
                r= (r + a / r) /2 ; // law of newten 
           }
           return r ; 
    }
float cosine(double x, int terms) {
    float result = 0.0;
    
    for (int n = 0; n < terms; n++) {
        double terms = power(x, 2 * n) / factorial(2 * n);
        
        // Alternate between positive and negative terms
        if (n % 2 == 0) {
            result += terms;
        } else {
            result -= terms;
        } 
   

    
    return result;
} }

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


