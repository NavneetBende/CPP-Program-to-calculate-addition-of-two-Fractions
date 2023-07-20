# CPP-Program-to-calculate-addition-of-two-Fractions

Add two fractions in C++
In this article we will discuss the program for add two fractions in C++. For this purpose we need to ask the user to enter two fractional values where each fraction must consist a Numerator and a Denominator.

Program to add two fractions
Addtion of two fractions in C++
Concept
 For understanding this in a better way lets suppose an example :

 Suppose, First fraction consist of 1 as numerator and 3 as denominator, and Second fraction consist of 3 as numerator and 9 as denominator.

 (1 / 3) + (3 / 9) = (6 / 9) = (2 / 3)

Find LCM of 3 and 9 and the result will be 9.
Multiply 3 in first fraction : (3 / 9) + (3 / 9)
Add both fractions and then the result will be : (6 / 9)
Now simplify it by finding the HCF of 6 and 9 and the result will be 3.
So divide 6 and 9 by 3 and then the result will be : (2 / 3)
This will be your simplified answer for the given problem.
Algorithm
Initialize variables of numerator and denominator
Take user input of two fraction
Find numerator using this condition (n1*d2) +(d1*n2 ) where n1,n2 are numerator and d1 and d2 are denominator
Find denominator using this condition (d1*d2) for lcm
Calculate GCD of a this new numerator and denominator
Display a two value of this condition x / gcd, y/gcd
Related Pages
Permutations in which n people can occupy r seats in a classroom
 
Maximum number of handshakes
 
Replace all 0’s with 1 in a given integer

Can a number be expressed as a sum of two prime numbers

Count possible decoding of a given digit sequence

While loop in C
C++ code
Run
#include<iostream>
using namespace std;

// GCD function
int findGCD(int n1, int n2)
{
    int gcd;
    for(int i=1; i <= n1 && i <= n2; i++)
    {
        if(n1%i==0 && n2%i==0)
            gcd = i;
    }
    return gcd;
}

// Main Program
int main()
{
    int num1,den1;
    
    //user input first fraction
    cout << "Enter numerator and denominator of first number : "; cin >> num1 >> den1;
    
    int num2,den2;
	
    //user input second fraction
    cout << "Enter numerator and denominator of second number: "; cin >> num2 >> den2;
    
    //finding lcm of the denominators
    int lcm = (den1*den2)/findGCD(den1,den2);
    
    //finding the sum of the numbers
    int sum=(num1*lcm/den1) + (num2*lcm/den2);
    
    //normalizing numerator and denominator of result
    int num3=sum/findGCD(sum,lcm);
    
    lcm=lcm/findGCD(sum,lcm);
    
    //printing output
    cout<<num1<<"/"<<den1<<" + "<<num2<<"/"<<den2<<" = "<<num3<<"/"<<lcm;
    
    return 0;
}
Output
Enter numerator and denominator of first number : 3 4
Enter numerator and denominator of second number: 5 6
3/4 + 5/6 = 19/12
