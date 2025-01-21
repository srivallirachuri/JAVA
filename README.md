Palindrome program

In this method we’ll use loops to break down the number into individual digits and the reassemble them in reverse order. We’ll use the modulo operator to extract the digits and divide operator to shorten the number. Finally we’ll compare if the reversed number matches the original number.

For a given integer number variable, we perform the following operations,

Run a while loop until the condition temp variable is not 0.
Extract the digits using modulo operator.
Using the formula reverse = reverse * 10 + last digit, we’ll keep updating the reverse variable.
We’ll shorten the number using divide operator.
Check if the reversed number matches the original number.
Let’s implement the above mentioned logic in Java Language.


public class Main
 {
   public static void main (String[]args)
   {
     //variables initialization
     int num = 12021, reverse = 0, rem, temp;

       temp = num;
     //loop to find reverse number
     while (temp != 0)
       {
     	rem = temp % 10;
     	reverse = reverse * 10 + rem;
     	temp /= 10;
       };

     // palindrome if num and reverse are equal
     if (num == reverse)
       System.out.println (num + " is Palindrome");
     else
       System.out.println (num + " is not Palindrome");
   }
 }

 Output
12021 is Palindrome

Method 2: Using Recursion
Working
In this method we’ll use recursion to break down the number into individual digits and then reassemble them in reverse order. In the end we’ll check if the reversed number matches the original number.

For a given integer input as number, we perform the following,

Define a recursive function which takes the number as an argument.
Set the base case as number ==0.
Set the recursive step call as getReverse(num/10, rev).
Check if the returned value matches the original number.
Let’s implement the above mentioned logic in Java Language.

Java Code

public class Main
{
  public static void main (String[]args)
  {
    //variables initialization
    int num = 12021, reverse = 0, rem, temp;

    // palindrome if num and reverse are equal
    if (getReverse(num, reverse) == num)
     System.out.println (num + " is Palindrome");
    else
      System.out.println (num + " is not Palindrome");
  }
  
  static int getReverse(int num, int rev){
    if(num == 0)
        return rev;
    
    int rem = num % 10;
    rev = rev * 10 + rem;
    
    return getReverse(num / 10, rev);
}
}
Output
21021 is Palindrome
