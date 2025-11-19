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
    float firstNumber, secondNumber; 
    float   result;
    char operator,c;
    double pi = 3.14159265359 ; 
    printf("=========================================\n");
    printf("         TERMINAL CALCULATOR              \n");
    printf("=========================================\n");
    printf(" [+] Addition\n");
    printf(" [-] Subtraction\n");
    printf(" [*] Multiplication\n");
    printf(" [/] Division\n");
    printf(" [^] Power (x^y)\n");
    printf(" [j] Square of x  (x²)\n");
    printf(" [p] 10 power of x\n");
    printf(" [f] the factoorial  of x\n");
    printf(" [o] x power of mines one \n");
    printf(" [k] it's mean 10 power of x \n"); 
    printf(" [v] it's means absulte value of x \n"); 
    printf(" [s] it's means square root of x \n");
    printf("-----------------------------------------\n");
    printf(" [E] Exit\n");
    printf("=========================================\n");

    a: printf("\nSelect an option: ");
    scanf(" %c", &operator);

    if (operator == 'E') {
        printf("Exiting...\n");
        return 0;
    }
// if the user enter one of the operator that need an only number 
    if (operator != 'j' && operator != 'p' && operator != 'f' && operator != 'o' && operator != 'k' && operator != 'v' && operator != 's' && operator!= 'c') {
        printf("Enter first number: ");
        scanf("%f", &firstNumber);
        printf("Enter second number: ");
        scanf("%f", &secondNumber);
    } else {
        printf("Enter number: ");
        scanf("%f", &firstNumber);
    }

    switch (operator) {
        case '+': // addition 
            result = sum(firstNumber, secondNumber);
            break;

        case '-': // i think it's doesn't need a comment 
            result = subtract(firstNumber, secondNumber);
            break;

        case '*':  // multiply 
            result = multiply(firstNumber, secondNumber);
            break;

        case '/':
            if (secondNumber == 0) {
                printf("Error: Division by zero is not allowed.\n");
                return 1;
            } else {
                result = divide(firstNumber, secondNumber);
            }
            break;

        case '^': // first number power of the second number 
            result = power(firstNumber, secondNumber);
            break;

        case 'j': // sqrt
            result = squart(firstNumber);
            break;

        case 'p': // 10^x
            result = power_of_ten(firstNumber);
            break;
        case 'f' : //factorial of x 
            result = factorial(firstNumber); 
            break; 
        case 'o' :  // the o means the x power of mines one 
            result = power_of_mines_one(firstNumber); 
            break; 
        case 'k' : // the char k means ten power of x 
            result = power_of_ten(firstNumber);
            break; 
        case 'v':
            result = absolute_value(firstNumber);
            break;
        case 's':
            if (firstNumber<0){
                printf("tere is no a square root of an negative number "); 
            }
            result =  square_root(firstNumber);  
            break ; 
      /** case 'c' : 
            result = cosine(firstNumber); 
            break; */
        default:     // when the user enter undefine operator 
            printf("Invalid operator.\n");
            return 1;
    }

    printf("The result = %f \n", result); // write the result 

    printf("type y to do repeat :  ");  // if the user want to do another operation
    getchar(); // this instuction is to skip the null erorr 
    scanf("%c", &c); 
    
    if (c=='y') {
        
        goto a ; // this line make all the code run again 
    }

    

    return 0; // return 0 means all the code is succes excuting that what i think
}

}


