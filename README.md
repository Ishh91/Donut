Nikunj loves donuts, but he also likes to stay fit. He eats n donuts in one sitting, and each donut has a calorie count, ci. After eating a donut with k calories, he must walk at least 2^j x k(where j is the number donuts he has already eaten) miles to maintain his weight.
Given the individual calorie counts for each of the n donuts, find and print a long integer denoting the minimum number of miles Nikunj must walk to maintain his weight. Note that he can eat the donuts in any order.
Input
The first line contains an integer, n, denoting the number of donuts. 
The second line contains n space-separated integers describing the respective calorie counts of each donut I, i.e ci.
Output
Print a long integer denoting the minimum number of miles Nikunj must walk to maintain his weight.
Constraints
1 ≤ n ≤ 40
1 ≤ ci ≤ 1000
Sample Input
3
1 3 2
Sample Output
11


Java Code
import java.util.Scanner;
public class Main {

	
	public static void main(String[] args) {
		// Write your code here
      Scanner sc  = new Scanner(System.in) ;
      
      int n = sc.nextInt() ;
      int input[] = new int[n] ;
      int i = 0 ;
      while(i < n)
      {
        input[i] = sc.nextInt() ;
        i++ ;
      }
      insertionSort(input) ;
      System.out.print(findMinWeight(input)) ;
	}

  
  static long findMinWeight(int input[])
  {
    int factorValue = input.length - 1 ;
    long w = 0 ;
    while(factorValue >= 0)
    {
      w = w + (((long)Math.pow(2, factorValue)) * input[factorValue] );
      factorValue-- ;
    }
   return w ; 
  }
  
  
  
 static void insertionSort(int input[]){
    
    for(int i = 1 ; i < input.length; i++)
    {
      int j = i - 1 ;
      int k = input[i] ;
     while(j >= 0)
     {
       if(input[j] <= k)
       {
         int temp = input[j] ;
         input[j] = input[j + 1] ;
         input[j + 1] = temp ;
       }
       j--  ;
      }
      
    }
    
    
    
  }
  
}
