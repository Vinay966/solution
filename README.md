*****Sum of Slope of all the number between given range*****
*****
You are given range of number (A to B) and you have to tell the sum of slope of all the number between A and B.

Now we define the term slope of a number N. Slope of a number N is the number of digits (excluding the first and the last digit) which
is either maxima or minima in that number.

Consider a number N. A digit in number N is called minima if it is smaller than both of its neighbour and a digit is called maxima if it is larger than both of its neighbour.

In case of wrong ranges or unexpected ranges, please return  output as -1

Example 1 : Consider the range 1-100 in this range all the numbers are either one digit or 2 digit so the slope value of all the number is zero and hence the sum is zero.
Similarly, consider the range 100-150 the sum of slope of all the number in this range is 19

Example 2 : Consider the number 54698 in range 54698-54800. In this number 4 is a minima because it is smaller than it both neighbor i.e. 5 and 6. similarly digit 9 is a maxima because it is grater than both of its neighbor i.e. 6 and 8.

Slope of 54698 is 2 because it has 4 as minima and 9 as maxima and there is no other minima or maxima.

Similarly we check next numbers in the range 54698-54800 and sum of slope of all the numbers will be the output.*********

Solution:


#include<stdio.h>

int sumofslope(int ,int );

int main()

{
    int a,b,result=0;
    
    scanf("%d %d",&a,&b);
    
    result= sumofslope(a,b);
     
    printf("%d", result);
    
    return 0;
    
}
 
int sumofslope(int a,int b)

{
   int i=0, sum=0,prev=0,cu=0,ne=0;
   
   for(i=a;i<=b;i++)
   
   {
       int n=i;
       
       prev=n%10;
       
       n=n/10;
       
       cu=n%10;
       
       n=n/10;
       
       if(n<=0)
        return 0;
        
        while(n>0)
        {
        
            ne=n%10;
            
            n=n/10;
            
            if((cu<prev&&cu<ne)||(cu>prev&&cu>ne))
            {
                sum++;
            }
            prev=cu;
            
            cu=ne;
           
        }
    }
       return sum; 
}
